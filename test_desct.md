# Чек-лист для внедрения изменений в Kwery

## 1. Frontend:

- [ ] Добавить новую форму в формате HTML и связать данные через `data-bind="value: variable"`
- [ ] Добавить в JS-файл для связывания переменных с пользовательским интерфейсом (ko.observable)
- [ ] Добавить новые данные в request body. Сверить с объектом Dto на API контроллере
- [ ] Использовать для хранения сообщений `messages.properties`
- [ ] Зарегистрировать новый компонент (new_page.html + new_page.js) в `startup.js` require: "components/path/to/new_page" (путь к js файлу)
- [ ] В js файле привязать путь к разметке html (define([..."text!components/broadcast/add.html"...])
- [ ] Зарегистировать url-маршрут к новой странице в `repo-dash.js` {url: "broadcast/add", auth: false, component: "broadcast-add"}

**Технологии:** Knockout.js

## 2. Backend:

- [ ] Разработать и создать модель сущности для БД с аннотацией @Entity
- [ ] Создать SQL-скрипт миграции
- [ ] Создать новый DAO класс
- [ ] Создать или обновить DTO для нового или обновленного endpoint

### Контроллеры:

- [ ] Зарегистировать маршрутизацию в файле `Routes.java` (пример: `router.POST().route(BROADCAST_JOB_SAVE_API).with(BroadcastApiController.class, "saveBroadcastJob")`)
- [ ] Обновить API-контроллеры

### Обработка отчетов (email sender)

- [ ] Обновить или создать новый `CsvToReportEmailSectionConverter` для приведения отчетов к нужному виду (создается через фабрику)
- [ ] Обновить или создать новый отправитель почты `BroadcastReportEmailSender`
- [ ] Обновить или создать в resources файл разметки письма `broadcastReport.html`, привязать к текущему контексту `kweryMail.setBodyHtml(templateEngine.process("broadcastReport", context));`

**Технологии:** ninja.Router

## 3. Database & Architecture:

- [ ] Рефакторинг базы данных (вынести логику БД из классов задач) - исследовать **User session limit**

## 4. Task Handling & Scheduling:

- [ ] Создать новый Task и Task Factory.
- [ ] Привязать Task Factory в конфигурации модуля (bind).
- [ ] Обновить проверки на task instance `SchedulerListenerImpl`.
- [ ] Обновить task instance `TaskExecutorListener`.
- [ ] Создать новый Service для планирования новой задачи в Cron4j
- [ ] Создать структуру данных для регистра нового типа задач чтобы отличать их от стандартных задач Kwery и управлять визуализацией.

## 5. Тестирование & Деплой (пока не знаю как делать):

- [ ] Написать юнит-тесты для новой функциональности.
- [ ] Провести интеграционное тестирование.
- [ ] Развернуть изменения на стейджинговой/продукционной среде и мониторить производительность.

## Изменения в существующий код Kwery:

### **TaskExecutorListenerImpl**:

Добавлено ветвление для отправки кастомного отчета:
```java
Boolean reportEmailSent = false;
// Broadcast section start
if (isBroadcastTask) {
    broadcastReportEmailSender.send(jobExecutionModel); // broadcast task always has email
    reportEmailSent = true; // flag for Broadcast service
    
};
// Broadcast section end
```

Добавлено ветвление для обработки завершения нового типа задачи Broadcast tasks
```java
// Broadcast section start
...} else if (task instanceof BroadcastTask) {
BroadcastTask broadcastTask = (BroadcastTask) task;
logger.info("Задача Broadcast завершилась. Next launch from cron expression");
// broadcastService.deschedule(broadcastTask.getJobId());
// logger.info("Задача Broadcast deschedule - for launch Broadcast needs recreate job");
//            
} // Broadcast section end
else {...}
```
В этом блоке можно управлять удалением или повторным запуском задачи, пока что на уровне хардкода.

### **SchedulerListenerImpl**:

дополнено ветвление для логирования запуска, успешного выполнения или ошибки нового типа задачи BroadcastTask
```java
} else if (task instanceof BroadcastTask) {
    logger.info("Запуск задачи рассылки SQL получателям");
}

} else if (task instanceof BroadcastTask) {
    logger.info("Задача рассылки SQL получателям успешно завершена");
} else {

} else if (task instanceof BroadcastTask) {
    logger.error("Ошибка при выполнении задачи рассылки SQL получателям", exception);
} 
```

### **JobApiController** в метод **listJobs**:

Убираем из общего списка задач, задачи на массовую рассылку, чтобы не "загромождать" просмотр существующих задач
```java
// Отфильтровываем задания, чтобы оставить только не-зарегистрированные Broadcast
jobs = jobs.stream()
    .filter(job -> !broadcastService.isBroadcastTaskRegistered(job.getId()))
    .collect(Collectors.toList());
// end Broadcast section
```

### **nav-bar.html**:

Добавлены выпадающие пункты Broadcast list и add

