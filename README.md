# Разработка Enterprise-приложений (Java)  
  
Репозиторий для фиксации артефактов знаний с курса [Разработка Enterprise-приложений без боли и сожалений](https://howto.stringconcat.com/enterprise) и учебного проекта курса.
  
Содержание:  
[Введение](#введение)  
[Разработка и управление требованиями](#блок-разработка-и-управление-требованиями)


📝 - пометки
🔗 - ссылки
📖 - описание
☑️ - чек листы

## Введение
Продолжение портфолио. Часть 2.  
Часть 1 [Система управления складом (WMS) - серверная часть (backend NodeJS/TS)](https://github.com/PortnovAlex80/node_js_pro#readme)

⚠️**Репозиторий в работе на начальной стадии. Плановый срок завершения - 09\2023** ⚠️  
  
## Блок Разработка и управление требованиями

### Введение
В проекте использовуется подход к разработке требований через Пользовательские истории.  
Пользовательские истории относятся к пользовательским требованиям. И являются входными данными для этапа проектирования.  
Результатом блока является User Story mapping, User story, Job story, Use cases (системные).</br>  

>_Однако стоит учесть, что критерии приемки в карточке User story относятся уже к функциональным требованиям. И в сложных пользовательских историях может понадобится применение use cases сценариев (например, чтобы понять как работают несколько пользовательских историй вместе)_

⚠️ Считаю важным ознакомится со следующими двумя заметками:
<details>
<summary> 📖 Концепция User Story </summary>

Концепция User story включает три аспекта:
1. **Текстовое описание (Written Description)**: User story начинается с текстового описания, которое включает в себя короткую, но информативную формулировку требования. Оно должно быть простым, понятным и конкретным, чтобы все заинтересованные стороны могли легко понять его суть.

2. **Устное обсуждение (Verbal Discussion)**: User story не ограничивается только текстовым описанием. Оно служит основой для устного обсуждения между разработчиками, заказчиками и другими заинтересованными сторонами. В ходе обсуждения дополняются детали, задаются вопросы и уточняются требования, чтобы все участники были на одной волне.

3. **Критерии приемки (Acceptance Criteria)**: Критерии приемки определяют условия, которые должны быть выполнены, чтобы считать User story завершенной и приемлемой. Это конкретные и измеримые условия, которые определяют ожидаемое поведение или функциональность. Критерии приемки помогают уточнить ожидания и обеспечить однозначность в определении готовности работы.

Вместе эти три аспекта - текстовое описание, устное обсуждение и критерии приемки - образуют основу User story и способствуют пониманию требований и достижению общего согласия между разработчиками и заинтересованными сторонами.

**Каковы преимущества устного обсуждения требований по сравнению с их определением в виде формальной документации?**
Письменная документация заставляет невольно предполагать исчерпывающую точность описания, чего в действительности может и не быть. Пользовательские истории, в которых карточки служат напоминаниями о том, что еще подлежит дальнейшему обсуждению, позволяют избежать создания ложной видимости того, что все определено очень точно. Одна лишь запись требований еще не является гарантией того, что заказчики получат то, чего они хотят; в лучшем случае они получат то, что записано. Частые обсуждения, особенно те, которые проводятся непосредственно перед разработкой обсуждаемой возможности или даже в процессе самой разработки, обеспечивают лучшее понимание предмета обсуждения и углубляют взаимопонимание между разработчиками и заказчиками.

Ниже приведены примеры.

| Наименование | Описание | Пример |
|--------------|----------|--------|
| Текстовое описание | Краткое описание требования или функциональности | `## Загрузка фотографий` |
| Устное обсуждение | Обсуждение требования между участниками | `- Разработчик: Какие форматы изображений поддерживаются?` |
| Критерии приемки | Условия для завершения User story | `- Изображение успешно загружается и отображается в галерее` |


| Наименование | Текстовое описание | Устное обсуждение | Критерии приемки |
|--------------|--------------------|------------------|------------------|
| Поиск товаров | Как покупатель, я хочу иметь возможность искать мебельные товары по категориям или ключевым словам, чтобы быстро найти нужный предмет мебели. | - Разработчик: Какие категории будут доступны для поиска? <br> - Заказчик: Можно ли искать товары по ценовому диапазону? | - Возможность поиска по категориям и ключевым словам работает корректно. <br> - Найденные товары соответствуют указанным категориям и ключевым словам. |
| Детальная информация о товаре | Как покупатель, я хочу видеть подробную информацию о каждом товаре, включая описание, характеристики, цену и наличие на складе, чтобы принять информированное решение о покупке. | - Разработчик: Какие характеристики должны быть доступны для каждого товара? <br> - Заказчик: Можно ли отображать скидки или акции для товаров? | - Подробная информация о товаре включает описание, характеристики, цену и наличие на складе. <br> - Скидки и акции отображаются для соответствующих товаров. |
| Добавление товаров в список желаний | Как покупатель, я хочу иметь возможность добавлять товары в список желаний, чтобы отложить покупку и вернуться к ней позже. | - Разработчик: Как пользователь будет иметь доступ к своему списку желаний? <br> - Заказчик: Можно ли добавлять комментарии или заметки к товарам в списке желаний? | - Товары успешно добавляются в список желаний пользователя. <br> - Пользователь может просматривать свой список желаний и редактировать его. |
</details>
<details>
<summary> 📖 Предисловие Марти Когана </summary>  
  
Фрагмент из книги "Пользовательские истории. Искусство гибкой разработки". Джефф Паттон  
  
Мне невероятно повезло – я имел возможность работать с представителями лучших в мире компаний и групп разработки разных технологий. Эти люди создают программы, которые вы любите и которыми пользуетесь каждый день. Люди, которые буквально меняют мир.  

Кроме этого, мне часто приходилось помогать компаниям, у которых дела идут не так здорово. Это были стартапы, пытающиеся запустить хоть что-то работающее, прежде чем кончатся деньги. Компании покрупнее, выбивающиеся из сил в попытке воплотить в жизнь свои последние разработки. Команды, безуспешно пытающиеся повысить эффективность бизнеса. Лидеры, раздраженные тем, как много времени занимает переход от идеи к воплощению. Инженеры, конфликтующие с владельцами своих продуктов.  

Из этого всего я вынес в первую очередь понимание того, насколько по-разному создают технологические продукты самые популярные компании на рынке и все остальные. И я не говорю сейчас о каких-то мелких различиях. Я имею в виду решительно все: подход руководителей к делегированию полномочий командам, способ взаимодействия команд, отношение организации к финансированию, комплектованию штата и выпуску продуктов, культуру, а также то, каким образом объединяют продукт, дизайн и технологии, чтобы разрабатывать самые эффективные решения для клиентов.  

Эта книга называется «Пользовательские истории. Искусство гибкой разработки ПО», но очень скоро вы заметите, что она повествует о чем-то большем, чем такая простая, но мощная техника, как построение пользовательских карт историй. С помощью книги можно проникнуть в самую суть того, как команды сотрудничают, общаются и в конце концов приходят к созданию великолепных продуктов.  

У многих из вас никогда не было возможности с близкого расстояния наблюдать за сильной командой в процессе работы над проектом. Возможно, опыт работы в компаниях, где вы трудились раньше или трудитесь сейчас, – все, что у вас есть. Поэтому я попытаюсь рассказать о том, насколько самые лучшие команды отличаются от всех остальных.  

С благодарностью в адрес Бена Хоровица и его книги «Хороший менеджер продукта, плохой менеджер продукта» я приведу здесь лишь важнейшие различия между сильными и слабыми командами.  

• У хороших команд есть четкое видение своего продукта, а каждый член команды страстно заинтересован в успехе. Плохие команды – просто наемники.

• Хорошие команды черпают идеи и вдохновение из системы ключевых показателей эффективности, наблюдения за клиентами, анализа полученных от клиентов сведений о результатах использования их продукта, а также из стремления постоянно применять новейшие технологии для эффективного решения проблем. Плохие команды получают требования из запросов заказчиков и отдела продаж.

• Хорошие команды понимают, кто их ключевые партнеры, им известны ограничения, которые вынужден учитывать бизнес клиентов, и поэтому они стараются находить решения, не только работающие для пользователей и заказчиков, но и учитывающие условия среды. Плохие команды просто выполняют требования партнеров.

• Хорошие команды компетентны во множестве техник, позволяющих быстро опробовать новые идеи для развития продукта и определить, какие из них следует воплощать в первую очередь. Плохие команды тратят часы на совещания, где пытаются составить списки приоритетов.

• В хороших командах обожают мозговые штурмы с участием лучших умов всей компании. Плохие команды ощетиниваются, если кто-то извне осмеливается внести какое-то предложение.

• В хороших командах инженеры, дизайнеры и менеджеры работают бок о бок, все время обмениваясь опытом и информацией о функционале, пользовательском опыте и технологических возможностях. В плохих командах эти специалисты разделены согласно своим обязанностям, а запросы одних к другим передаются через служебные записки и совещания, проводимые по расписанию.

• Хорошие команды постоянно пробуют новые идеи и вводят различные усовершенствования, но делают это осторожно, чтобы не навредить эффективности бизнеса. Плохие команды ждут разрешения что-то попробовать.

• У участников хороших команд непременно есть полный набор навыков для создания сильных продуктов, например, с хорошим дизайном взаимодействия. Плохие команды даже не знают, кто такие дизайнеры интерфейсов.

• В хороших командах заботятся о том, чтобы у инженеров ежедневно находилось время поработать с прототипом продукта для поиска идей по его улучшению. В плохих командах инженерам показывают прототипы на планировании спринта при оценке объема работы.

• Хорошие команды еженедельно напрямую общаются с конечными пользователями и заказчиками, чтобы лучше понять их и узнать их мнение о последних изменениях и идеях. Плохие команды считают, что достаточно собственного мнения.

• Хорошие команды знают, что не все их любимые идеи будут работать для заказчиков, но даже те, что будут, потребуют нескольких доработок, прежде чем приведут к получению желаемого результата. В плохих командах просто делают то, что записано в плане, довольствуясь датами совещаний и показателями качества.

• Хорошие команды понимают важность быстродействия и регулярных прогонов для успешного внедрения инноваций; им известно, что скорость обеспечивается правильной организацией работы, а вовсе не напряженным трудом. В плохих командах все жалуются на медленную работу, обвиняя в этом недостаточно усердно трудящихся коллег.

• После оценивания затрат на реализацию запроса хорошие команды берут на себя жесткие обязательства и стараются убедиться, что они трудятся над жизнеспособным решением, которое будет эффективно работать как для заказчиков, так и для бизнеса. Плохие команды жалуются, что им приходится работать на эффективность продаж.

• Хорошие команды выстраивают свою работу так, что могут немедленно оценить, как их продукт используется, и сделать выводы, базирующиеся на этих данных. Плохие команды считают аналитику чем-то, что хорошо бы иметь.

• Хорошие команды постепенно и непрерывно обновляют продукт, зная, что постоянный поток небольших обновлений означает стабильное и надежное решение для заказчиков. Плохие команды проводят ручное тестирование в конце огромной фазы разработки, а затем выкатывают сразу все обновления.

• Хорошие команды концентрируются на своей целевой аудитории. Плохие команды концентрируются на конкурентах.

• Хорошие команды устраивают вечеринку, когда достигают значительного улучшения ключевых показателей эффективности. Плохие команды празднуют финальный релиз чего-нибудь.

Я понимаю: вы, вероятно, хотите знать, что общего со всем этим имеют карты историй. Я уверен, вы удивитесь, поняв, в чем дело. По той же причине я преданный поклонник построения карт историй.

На моем пути встретилось не так уж много экспертов Agile, по моим меркам достаточно квалифицированных для того, чтобы оказать реальную помощь серьезной команде, разрабатывающей продукт, и поднять ее работу на тот уровень, в котором нуждается компания и которого она заслуживает. Джефф Паттон – один из них. Я наблюдал, как он в разгар разработки засучив рукава трудится вместе со всей командой. Я представлял его в компаниях, потому что он эффективен. Команды обожают его, так как при всей своей компетентности он совершенно лишен высокомерия.

Время, когда менеджеры день-деньской собирали и документировали требования, дизайнеры концентрировались на косметических улучшениях, а инженеры тонули в коде, для самых лучших команд давно ушло в прошлое. Настало время стремиться к будущему и вам.
</details>
</br>   

### Формирование беклога
Беклог продуктовой команды формируется из User Stories.  
Беклог команды разработки формируется после проектирования и декомпозиции тикетов для разработки. За проектирование отвечает команда разработки.  
  
```mermaid
%%{init: {"flowchart": {"htmlLabels": false}} }%%
flowchart LR
    POB["Product Owner Backlog:\n User stories"]
    DES["Design: transorming User stories to tasks \n(System analyst, Team-lead)"]
    DEV["Development team Backlog: \n Tasks"]
    POB --> DES
    DES --> DEV
```

### Флоу работы с требованиями на проекте

Флоу работы с требования выглядит примерно так:
```mermaid
%%{init: {"theme": "neutral"} }%%
flowchart LR
    A[Выявление целей] --> B[Discovery]
    B --> C[Inception]
    C --> D[Development]
    D --> E[Основная разработка]
    E --> F[Демонстрация результатов]
    F --> G[Подведение итогов]
    G --> H[Сбор обратной связи]

    style A shape:ellipse, ill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style B fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style C fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style D fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style E fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style F fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style G fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
    style H fill:#FFFFFF, stroke:#000000, stroke-width:1px, text-align:center, font-weight:bold, padding:8px, color:#000000
```
Описание каждого этапа приведено в таблице.
| Этап | Наименование |
|------|--------------|
| Выявление целей | Elevator pitch + Opportunity Canvas |
| Discovery | Марктинговые исследования, Скетчинг, Fakeware, Приоретизация, минимизируем работу, выявляем потребности и цели. </br> участники: тим лид, аналитик, прожект, продакт. </br>итог этапа: собираемся до тех пор, пока точно придут к единому пониманию что нужно сделать. |
| Inception | Приоретизация, построение карт историй, известна цель что нужно заказчика, первая итерация для разработки, </br>итог этапа: имеются задачи и расписаны user stories, можно оценить стоимость проекта, НФТ; |
| Development | Разработка (итерация 0): настройка инфраструктуры проекта, CI/CD и с выкатом на PROD. На выходе только hello world и тестовые кейсы. |
| Основная разработка | Проектирование технических решений, </br>итог этапа: задачи, реализация User story в коде, релизы и тп. |
| Демонстрация результатов | Показ резульатов работы |
| Подведение итогов | Обсуждение работы, что сделано хорошо, что можно улучшить, где болит? |
| Сбор обратной связи | Технические метрики, бизнес-метрики, опросы, разговоры с заказчиком, общение с пользователями |

#### Elevator pitch

> Краткая идея "Elevator pitch" заключается в представлении идеи, продукта или проекта таким образом, чтобы заинтересовать и привлечь внимание целевой аудитории в течение короткого времени, например, за время подъема на лифте (отсюда и название "Elevator pitch"). Основная цель "Elevator pitch" - захватить внимание и вызвать интерес, чтобы дальше продолжить дальнейшее обсуждение или получить поддержку.

> Для всех кто хочет выразить их идеи быстро и убедительно, то elevator pitch это инструмент, который прост, легок для понимания и выражает все важные аспекты идеи. В отличии от случайных, беспорядочных и не структурированных мыслей, elevetor pitch прост, краток и мощен.

Формула 
| Формула         |                  |
|--------------|------------------|
| Для          |         целевой аудитории         |
| Которая      |         что-то хочет или имеет определенный интерес         |
| То           |         наша идея или продукт         |
| Это          |      категория продукта            |
| Которая      |             имеет определенную пользу и причины на жизнь     |
| В отличии    |          от главного конкурента        |
| Наша идея    |       ключевой идентификатор           |

<details>
<summary> &#128736; Примеры Elevator pitch </summary>

Пример 1
| Формула         |                  | |
|--------------|------------------|---|
| Для          |         целевой аудитории         | для всех жителей Сингапура|
| Которая      |         что-то хочет или имеет определенный интерес         |планируют свадьбу, или расторжение брака (или хотят помешать браку), а также работников ЗАГСа|
| То           |         наша идея или продукт         | новый портал для операций с браками|
| Это          |      категория продукта            | |
| Которая      |             имеет определенную пользу и причины на жизнь     |станет единой точкой общения с государством|
| Которая      |             имеет определенную пользу и причины на жизнь     |снимает боловную боль с молодеженов|
| В отличии    |          от главного конкурента        |текущего портала, который вызывает гнев пользователей, </br> будет способствовать проведению торжества или расторжению брака, используя всю мощь новых каналов коммуникации и прочее |
| Наша идея    |       ключевой идентификатор           | |

Пример 2
| Формула         |                  | |
|--------------|------------------|---|
| Для          |         целевой аудитории         | бизнес-пользователей (менеджеров)|
| Которая      |         что-то хочет или имеет определенный интерес         |нужно быть продуктивным и в офисе и в поездках|
| То           |         наша идея или продукт         | Microsoft Surface|
| Это          |      категория продукта            | будет планшетом-трансформером |
| Которая      |             имеет определенную пользу и причины на жизнь     |легко носить и позволит быть таким же продуктивным, как и с компьютером|
| В отличии    |          от главного конкурента        | от ноутбуков, будет служить легче и удобнее в поездках |
| Наша идея    |       ключевой идентификатор           | |
</details>

<details>
<summary> ☑️ Чек-лист User story (INVEST)  </summary>
  
- [ ] Independent (Независимость): User Story может быть реализована в изоляции от других User Story.
- [ ] Negotiable (Договоренность): User Story представляет собой соглашение между командой разработчиков и заинтересованными сторонами.
- [ ] Valuable (Ценность): User Story имеет бизнес-ценность и представляет интерес для пользователей или заказчиков.
- [ ] Estimable (Оцениваемость): Команда может оценить сложность и объем работы для реализации User Story.
- [ ] Small (Маленькая): User Story достаточно маленькая, чтобы ее можно было реализовать за одну итерацию.
- [ ] Testable (Тестируемость): User Story может быть протестирована для проверки ее успешного выполнения.
      
</details>

<details>
<summary> ☑️ Чек-лист Антипаттерны работы с требованиями </summary>

| Антипаттерны         |                  |
|--------------|------------------|
|    анемичный аналитик       |         аналитик указывает разработке реализацию        | 
|    прямой доступ      |        заказчик имеет непосредственный доступ к команде  разработки         | 
|    All inclusive       |        подписываемся под всеми требованиями без анализа         |
|    свободный художник       |         разработчик меняет требования на свое усмотрения без обсуждения         | 
|    фича-задача      |        задача как "фича", нет трассировки к бизнес-требованиями и не пройдена по процессам         | 

</details>


<details>
<summary> 🔗 Полезные ссылки (примеры User Story mapping) </summary>
  https://www.atlassian.com/ru/agile/project-management/user-stories - User story
https://youtu.be/vy_60LFvRNA Требования в Agile: живой User Story Mapping  </br> 
https://youtu.be/qUTV5m7zk9Q User Story Mapping: вопросы и ответы по технике постановки задач
  https://habr.com/ru/companies/oleg-bunin/articles/537862/ DDD
  https://docs.google.com/presentation/d/1LctHq0gBBtWJpLXD3RDdnQ5pAOBUpiKK07tpTCsFRK0/edit#slide=id.gbf463c658_0_5 Conceptual Architecture of
DOOM 3
</details>

![your-UML-diagram-name](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/PortnovAlex80/node_js_pro/developer/api-warehouse/diagrams/apparchi.iuml)
