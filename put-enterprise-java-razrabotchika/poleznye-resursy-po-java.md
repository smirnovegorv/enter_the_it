# Полезные ресурсы по Java

Как уже было сказано, эта книга - скорее список тем и ключевых слов для самостоятельного изучения. Невозможно в одной книге охватить все, от основ языка до деталей работы с БД и отдельными фреймворками.

Перечислю тут ресурсы, где можно найти более детальную информацию по конкретным темам.

### Сайты с полезными статьями

1. Хабр https://habr.com - крупнейший русскоязычный технический ресурс. Статьи есть обо всем. Если с английским у вас не очень - можно искать в Яндексе запросы вроде "<название технологии> site:habr.com", и скорее всего что-то найдется.\
   Уровень статей очень разный, так что возможно придется поискать ту, где будет написано понятно именно для вас.
2. [https://www.baeldung.com](https://www.baeldung.com) - очень много статей и туториалов по экосистеме Java. Написано достаточно просто и доходчиво, но на английском. Рекомендую тут искать ответы на вопросы и примеры использования конкретных библиотек
3. [https://mkyong.com/tutorials/spring-boot-tutorials/](https://mkyong.com/tutorials/spring-boot-tutorials/) - тоже много статей и туториалов по Java.&#x20;
4. JavaRush [https://javarush.ru/groups/general](https://javarush.ru/groups/general) - кроме курсов там есть и статьи и туториалы. Плюсы - написано на русском, код и пояснения, все красиво оформлено. Минусы - часто сильно устарело (особенно касается использования уже неактуальных возможностей того же Spring).
5. Уже упоминалось в разделе [chto-uchit-iz-klassicheskoi-computer-science.md](../s-chego-nachat/chto-uchit-iz-klassicheskoi-computer-science.md "mention")[https://refactoring.guru/ru/design-patterns/](https://refactoring.guru/ru/design-patterns/) - хороший сайт со статьями по паттернам проектирования. Понимание паттернов позволит пореже изобретать велосипеды в архитектуре вашего ПО.
6. [Stackoverflow](https://stackoverflow.com). Самый нужный сайт для любого программиста. Огромная база вопросов и ответов. В ней столько всего, что уже есть шутки про "stackoverflow-driven-development", мол, программисты нифига уже не умеют сами писать код, просто заходят на Stackoverflow, ищут нужный кусок кода там и вставляют в свою программу.

Если в поисковой выдаче в ответ на ваш вопрос вы видите ссылку на mkyong или baeldung - там вы скорее всего найдете хороший ответ на вопрос, рекомендую такие ссылки просматривать в первую очередь.

### Сайты с курсами и задачами

1. [https://leetcode.com](https://leetcode.com) - сайт с задачками на алгоритмы. Простые задачи вполне подходят для тренировки начинающих. \
   Вам дается онлайн-IDE, в которой вы пишете решение поставленной задачи (обычно 1-2 метода и десяток-другой строк), затем встроенная система тестирует его и проверяет на правильность.\
   Можно соревноваться с другими участниками, решать задачи на скорость, смотреть подборки типа "сто самых популярных задач на собеседовании в Apple" и т.п.
2. JavaRush - там есть курсы, где сперва вы изучаете что-то в теории, а затем пишете решение и оно проверяется на корректность. Отзывы неоднозначные, сам не пробовал

### Книги

1. В случае с Java обычно все вспоминают про самоучители Шилдта. Автор написал много книг по разным версиям Java, начиная с самых первых, выбирайте актуальную на текущий момент.\
   Главный плюс - детально разобран синтаксис и возможности языка. Главный минус (как и у многих самоучителей) - объясняется "как", но не объясняется "зачем". Это как раз тот пример, когда читателя пичкают ответами на вопрос "что такое цикл" и "как написать функцию", но при этом не объясняют, зачем собственно ее писать, и какая в этом польза.\
   Так что можно использовать как справочник по возможностям языка и как подсказку, почему программа не компилируется. Читать от корки до корки большого смысла, наверное, нет.
2. Альтернативой Шилдту часто называют "Java. Библиотека профессионала" Хорстманна. Кому-то нравится больше. По факту плюс-минус то же самое, от самых основ синтаксиса и к довольно продвинутым темам.
3. "Совершенный код" Макконелла. Не про Java, код там на С++, но их синтаксис достаточно похож, чтобы было понятно. В отличие от предыдущих авторов много внимания уделяет вещам, общим для любого языка программирования: как писать качественные программы, как вообще выглядит процесс разработки, какие основные принципы написания хорошего кода.
