# Качество программного кода

Кроме того, чтобы просто написать код, выполняющий нужные действия, желательно еще сделать его читаемым, поддерживаемым и содержащим поменьше багов.

Качество ПО - большая тема, пройдемся тут по основным концепциям. Описанное ниже может пригодиться, скорее всего, тем кто уже начал работу в первой своей компании. Совсем уж начинающим не стоит забивать этим голову. Однако оставлю тут эту главу, чтобы на нее тоже можно было ссылаться в первые месяцы обучения новых сотрудников.

### Стандарты кодирования

Все начинается с исходного кода. Один и тот же фрагмент кода можно написать по-разному: использовать различные имена переменных, по-разному расставлять скобки и т.п.

Если каждый будет писать, как захочет, то в коде будет бардак, и читать его будет сложно. Поэтому придумывают различные так называемые _стандарты кодирования_ - наборы правил оформления исходного кода.&#x20;

Для Java есть стандарты, созданные еще Oracle - [https://www.oracle.com/technetwork/java/codeconventions-150003.pdf](https://www.oracle.com/technetwork/java/codeconventions-150003.pdf). Там детально прописано, как ставить скобочки, как называть классы и переменные, как писать комментарии. Большинство ИТ компаний используют либо этот стандарт, либо его вариацию. Рекомендую его изучить. Если в компании принят свой стандарт - вам, скорее всего, дадут ссылку на него при трудоустройстве.

Современные IDE имеют богатые возможности  для автоматического форматирования кода, в большинстве случаев они все сделают красиво за вас. Вам придется лишь выбирать правильные имена переменных и методов.

### Принципы написания кода

О том, как именно писать читаемый и поддерживаемый код, в интернете есть много противоречивой информации. Придумано множество принципов и методологий, прячущихся за странными аббревиатурами. Стоит, как минимум, знать как они расшифровываются. А со временем вы сможете выбрать те из них, которые больше подходят вам и вашему стилю кодирования.

Что такое все эти KISS, DRY, YAGNI и прочие можно прочитать в различных статьях наподобие [https://habr.com/ru/company/itelma/blog/546372/](https://habr.com/ru/company/itelma/blog/546372/). Вкратце, там обычно советуют все делать максимально просто (не плодить огромные методы на 1000 строк, а разбивать код на небольшие фрагменты), не дублировать код (выносить общие фрагменты в отдельные методы/классы) и т.п. Это все может показаться очевидным, но в реальности далеко не всегда почему-то получается им следовать.

### Тестирование ПО

Тоже отдельная большая тема. После того, как вы написали какой-то код, неплохо бы убедиться, что он работает, причем именно так, как надо.&#x20;

Пока речь идет о небольшом проекте, вы вполне можете после каждого серьезного изменения вручную прокликать все кнопочки и убедиться, что весь новый функционал добавлен, а старый нигде не сломался. Но как только проект увеличивается, объем такого ручного тестирования становится неприлично большим, а сам этот процесс - до невозможности скучным (в очередной раз нажать сто кнопок для проверки после каждого изменения - это с ума сойти можно, так что велика вероятность что вы быстро на тестирование забьете).

Для решения этой задачи придумано множество способов автоматизации тестирования, а также целая профессия и множество учебных курсов. Перечислим тут лишь некоторые основные ключевые слова, по которым вы сможете найти информацию дальше.

**Юнит-тесты**

Правильно написанный код состоит из небольших слабо связанных фрагментов. Такие фрагменты могут быть легко использованы в отрыве от всей остальной инфраструктуры вашего ПО, что позволяет писать маленькие простые тестовые программы, проверяющие корректность его работы на конкретных сценариях.

Вот написали вы класс, который умеет считать, например, среднее арифметическое массива чисел:

```
class MeanCalculator {

  double calculate(double[] array) { ... }
}
```

Вам надо убедиться, что для типичных сценариев использования ваш код будет выдавать правильные ответы.&#x20;

Для Java стандартом де-факто для написания Unit-тестов является фреймворк JUnit. Он содержит ряд аннотаций, которыми вы можете пометить свои классы с тестами. Код, который найдет такие классы, запустит их, проверит результаты и сформирует отчет. И дополнительные вспомогательные методы для проверки ожидаемых значений.

Юнит-тесты для такого класса могут выглядеть как:

```
class MeanCalculatorTest {
   // В этом тесте мы просто считаем среднее, сравниваем с ожидаемым результатом
   // JUnit кинет ошибку, если результат отличается
   @Test
   void testCalculateSimple() {
     MeanCalculator mc = new MeanCalculator();
     double rz = mc.calculate(new Double[] {2.0, 4.0, 6.0})
     Assertions.assertEquals(6.0, rz);
   }
   
   // Тест на краевой случай: что будет, если передать на вход пустой массив
   // Наш метод по идее должен в таком случае кинуть IllegalArgumentException
   // Мы говорим JUnit, что в этом тесте такой эксепшн - это ожидаемое поведение
   // Так что тест будет считаться проваленным, если исключения не будет
   @Test(expected = IllegalArgumentException.class)
   void testEmpty() {
     MeanCalculator mc = new MeanCalculator();
     double rz = mc.calculate(new Double[] {})
   }

}
```

Подробнее про юнит-тестирование - в множестве статей и литературы наподобие [https://habr.com/ru/post/169381/](https://habr.com/ru/post/169381/) или [https://www.baeldung.com/junit-5](https://www.baeldung.com/junit-5)

Постоянный автоматический запуск юнит-тестов при каждом коммите в VCS позволяет отлавливать ошибки сразу же как они были внесены. При этом он позволяет эффективно отлавливать _регрессии_ - когда новое изменение ломает старую функциональность, которая раньше работала правильно. Вручную их отлавливать сложно, так как получается что каждый раз надо тестировать не только новый функционал, но и весь старый.

**Интеграционные и UI тесты**

К сожалению, в реальных проектах бывает мало проверить отдельные методы и классы. Нужно еще проверить и сложные пользовательские сценарии, взаимодействие между разными компонентами вашего ПО, полный цикл запроса от обработки HTTP контроллером до записи результата в БД.&#x20;

Такие тесты, проверяющие крупные куски вашего ПО, называются интеграционными. От Unit-тестов они отличаются большей сложностью, временем выполнения и необходимостью поднимать какое-то сложное окружение (полностью запустить Спринг, иметь запущенную БД и т.п.).

В Спринге для этого есть множество инструментов, почитать про которые можно вот тут [https://www.baeldung.com/spring-boot-testing](https://www.baeldung.com/spring-boot-testing)

Немного особняком стоят тесты пользовательского интерфейса. С ними всегда связано много сложностей, так как они требуют буквально открыть ваше ПО и прокликать на все кнопки. Для таких штук приходится использовать специальные инструменты, например Selenium позволяет писать скрипты управления браузером для автоматических тестов содержимого веб-страниц.

**Нагрузочные тесты**

Бывает, что код вроде бы работает как надо, но написан неоптимальным образом и быстро начинает задыхаться при увеличении объемов обрабатываемых данных (почему так бывает, мы обсуждали в [главе про алгоритмы](../s-chego-nachat/chto-uchit-iz-klassicheskoi-computer-science.md)). На ваших тестовых наборах данных и при ручном тестировании все может работать отлично, но как только ваш код попадает в реальное использование, в него начинают ломиться тысячи пользователей и гигабайты данных, все умирает или начинает очень долго отвечать.

Чтобы отлавливать такие ситуации в процессе разработки существует нагрузочное тестирование. Различными инструментами пытаются создать нагрузку, эквивалентную той, которую создадут реальные пользователи. Например, с помощью [Apache Jmeter](https://jmeter.apache.org) можно бомбардировать ваше веб-приложения тысячами запросов как бы от имени разных пользователей, а затем смотреть статистику по количеству ошибок и задержкам ответов.

**Test Driven Development**

Достаточно холиварная концепция разработки ПО, однако хотя бы название ее стоит знать, так как она в какой-то степени применяется в некоторых крупных компаниях.

Суть такова: при обычной разработке вы сперва пишете код, затем пишете тесты на этот код. При TDD вы сперва пишете тесты, и лишь затем - код, который они тестируют.

Этот подход кажется совершенно контринтуитивным, однако он реально работает. В таком случае ваши тесты без кода - это по сути спецификация этого кода. В тестах вы заранее описываете, что вот этот метод на таких входных данных должен выдавать такой ответ, а на таких - вот такой. Затем вам уже гораздо легче реализовать этот метод, имея такую четкую спецификацию.

### Заключение

Знания всего этого от начинающего разработчика в обязательном порядке, скорее всего, не потребуют. Но на собеседовании понимание принципов и знакомство хотя бы с одним тестовым фреймворком однозначно будет плюсом.

С написанием юнит-тестов вам, скорее всего, придется столкнуться. Во всех нормальных компаниях они используются, как самый дешевый и простой способ значительно поднять качество кода, причем пишут их как правило сами разработчики.

Другие ступени (интеграционные, нагрузочные, UI тесты) часто или отсутствуют, или ими занимаются уже специально обученные QA-инженеры. Хотя велика вероятность, что по мере роста в профессии вам тоже придется с ними столкнуться.
