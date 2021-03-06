# Таск-трекеры

Таск-трекеры - это ПО для управления проектом, командой и постановки задач.

Любые таск-трекеры имеют базовый функционал по управлению задачами:

* Создание списков задач, назначение ответственных
* Отслеживание времени выполнения задач
* Группировка задач
* Обсуждения и комментарии к задачам

Продвинутые трекеры, заточенные именно на управление разработкой ПО, также могут:

* Иметь интеграцию с [системами контроля версий](sistemy-kontrolya-versii.md), например чтобы автоматически создавать ветки при начале работы над задачей, или показывать все изменения кода, сделанные в рамках работы над ней.
* Поддерживать различные статусы задач и бизнес-процессы, иметь встроенные средства автоматизации. Например, при назначении задаче статуса "в тестировании" таск-трекер может автоматом назначить на нее ответственного за тестирование человека, а также запустить сборку и выкладку на тестовый стенд версии программы из Git из ветки, привязанной к задаче.
* Иметь интеграции с системами документации, мессенджерами и прочим сторонним софтом, чтобы легко можно было делиться задачами, оповещать о задачах исполнителей, выгружать отчеты о производительности и т.п.

На данный момент все популярные таск-трекеры - это веб-приложения, часто имеющие также и клиенты для мобильных устройств. Как правило, у всех есть бесплатный план, подходящий для ознакомления, работы над личными проектами или в небольшой команде (до 5-10 человек).

Для разработки самым популярным, наверное, является [Atlassian Jira](https://www.atlassian.com/ru/software/jira). Я рекомендую завести там бесплатный аккаунт и попробовать вести задачи там одновременно с разработкой первого учебного проекта.&#x20;

![Задачи в текущем спринте, скриншот из документации Jira](<../../.gitbook/assets/image (9) (1).png>)

Начать там довольно просто, и базовый интерфейс там понятен. На выбор предлагается несколько методологий ведения проектов, и начать можно с самой простой, проектной. Но везде где я работал обычно используется вариант SCRUM (сама эта методология это отдельно большая тема, но обычно используют лишь какие-то отдельные ее фрагменты):

* Задачи в проекте изначально добавляются в общий список задач - _бэклог (backlog)_.
* Разработка ведется итерациями по 1-2 недели, называемыми _спринтами (sprint)_. В начале спринта в него накидываются задачи, которые затем можно отслеживать на отдельной странице с текущим спринтом.
* Изначально доступны три статуса задач - "надо сделать", "в процессе", "сделано". Этого достаточно для простых личных проектов, в более сложных ситуациях можно назначить любые дополнительные статусы и правила перехода между ними.&#x20;
* После того, как задачи в текущем спринте выполнены, он закрывается и создается новый. В конце каждого спринта должна получиться новая работоспособная версия ПО, которую можно показать заказчику.

На тему SCRUM и гибких методологий разработки написано много статей и книг, можете почитать что-то [https://biz.mann-ivanov-ferber.ru/2019/09/09/chto-takoe-agile-i-scrum-i-kak-s-nimi-rabotat/](https://biz.mann-ivanov-ferber.ru/2019/09/09/chto-takoe-agile-i-scrum-i-kak-s-nimi-rabotat/), чтобы столкнувшись с этими словами и терминами в реальной жизни понимать, что они значат.

Я крайне рекомендую использовать таск-трекеры даже в личных небольших проектах. Это во-первых позволит набрать опыт работы с ними, а во-вторых это просто удобно, даже если работаешь в одиночку. Проще заводить задачи, не забывать о них и не путаться в них, отслеживать статусы. Это удобнее, чем держать все в голове или в блокноте.



&#x20;
