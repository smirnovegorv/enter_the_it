# Зачем так сложно?!

После первого прочтения этого раздела у начинающего разработчика может голова пойти кругом. Много новых концепций, технологий и странных названий. И появляется идущий из глубин души крик "емае, ну зачем так сложно делать простые вещи??!".

В самом деле, может показаться, что все эти DI, контроллеры, аннотации и прочая начинка Спринга совершенно избыточны. Однако так кажется только поначалу и из-за недостатка опыта. Чтобы прочувствовать это - надо не раз походить по граблям. Попробовать написать все "по-простому", увидеть, что оно не расширяется и быстро становится нечитаемым и неподдерживаемым, попридумывать костыли всякие, а потом осознать, что придуманные костыли - это и есть те самые паттерны, которые в Спринге были с самого начала, только более кривые (потому что у сообщества Спринга было 20 лет чтобы все это понять и довести... ну не до совершенства, но до устраивающего всех уровня). Понять, что оно все тут (не только в Спринге, все эти подходы встречаются и в других аналогичных фреймворках на других языках) на своем месте, все это результат десятилетий реального опыта разработки различных веб-сервисов.

Да, для маленьких учебных проектов можно этим всем не заморачиваться, а взять какой-нибудь веб-фреймворк попроще, код бизнес-логики писать прямо в контроллерах, а вместо БД сохранять все в текстовый файлик. И может оно даже будет работать. Но потом, попав в реальную компанию с реальным проектом на сотни тысяч строк, где такой подход уже не работает, вам придется переучиваться. Так что лучше уж немного потерпеть и сперва научиться делать правильно, чтобы потом уже быстро и эффективно работать.

![](<../../.gitbook/assets/image (9).png>)
