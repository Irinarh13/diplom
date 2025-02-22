# План автоматизации тестирования сервиса покупки туров

# 1. Список автоматизируемых сценариев

## Покупка тура через кнопку "Купить" на главной страницы сервиса.

1. Покупка с оплатой дебетовой картой со статусом APPROVED, отправка формы с валидными данными:
* Отправка формы с валидными данными карты. "Номер" = "4444 4444 4444 4441", "Месяц" = "08", "Год" = "23", "Владелец" = "IVAN PETROV", 
"CVV" = "345" (Ожидаемый результат - сообщние: "Успешно. Операция одобрена Банком");

2. Покупка с оплатой дебетовой картой со статусом DECLINED, отправка формы с валидными данными:
* Отправка формы с валидными данными карты. "Номер" = "4444 4444 4444 4442", "Месяц" = "08", "Год" = "23", "Владелец" = "IVAN PETROV", 
"CVV" = "345" (Ожидаемый результат - сообщние: "Ошибка! Банк отказал в проведении операции").

## Тестирование полей с данными

3. Отправка пустой формы
* Отправить пустую форму (Ожидаемый результат - под полями сообщния: "Поле обязательно для заполнения"

### Поле "Номер карты"

4. В поле "Номер карты" вводим номер другого формата. Например - 4444 4444 4444 4443 (Ожидаемый результат - сообщение: "Поле 
  обязательно для заполнения" или "Неверный формат");
5. В поле "Номер карты" вводим 16 нолей (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");
6. В поле "Номер карты" вводим 15 цифр. Например - 4444 4444 4444 444 (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения" или "Неверный формат");
7. Оставляем поле "Номер карты" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");
8. В поле "Номер карты" вводим буквы и специальные символы. Например - fhhb $*)@ jkjs уолц (Ожидаемый результат - сообщение: "Поле 
   обязательно для заполнения" или "Неверный формат")

### Поле "Месяц"

9. В поле "Месяц" вводим цифру больше 12 (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", 
  "Неверно указан срок действия карты" или "Неверный формат");
10. В поле "Месяц" вводим одну цифру (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", 
  "Неверно указан срок действия карты" или "Неверный формат");
11. Оставляем поле "Месяц" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок 
  действия карты" или "Неверный формат");
12. В поле "Месяц" вводим два ноля (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", 
  "Неверно указан срок действия карты" или "Неверный формат");
13. В поле "Месяц" вводим буквы и специальные символы. Например - h* (Ожидаемый результат - сообщение: "Поле 
   обязательно для заполнения" или "Неверный формат")

### Поле "Год"

14. В поле "Год" вводим значение меньше текущего года. Например - 22 (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения", "Неверно указан срок действия карты" или "Истёк срок действия карты");
15. В поле "Год" вводим одну цифру (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок действия карты" 
  или "Истёк срок действия карты");
16. Оставляем поле "Год" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок действия 
  карты" или "Истёк срок действия карты");
17. В поле "Год" вводим два нуля (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок действия карты" 
  или "Истёк срок действия карты"
18. В поле "Год" вводим буквы и специальные символы. Например - Р? (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения", "Неверно указан срок действия карты" или "Истёк срок действия карты").

### Поле "Владелец"

19. В поле "Владелец" вводим фамилию и имя на кириллице. Например - ИВАН ПЕТРОВ (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения" или "Неверный формат");
20. В поле "Владелец" вводим буквы и специальные символы. Например - 23%$### *^^ (Ожидаемый результат - сообщение: 
  "Поле обязательно для заполнения" или "Неверный формат")
21. Оставляем поле "Владелец" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");

### Поле "CVV"

22. В поле "CVV" вводим одну или две цифры. например - 34 (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный 
  формат");
23. Оставляем поле "CVV" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");
24. В поле "CVV" вводим три ноля (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный 
  формат");
25. В поле "CVV" вводим буквы и специальные символы. Например - *Ц? (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или 
  "Неверный формат");

## Покупка тура через кнопку "Купить в кредит" на главной страницы сервиса.

26. Покупка с оплатой дебетовой картой со статусом APPROVED, отправка формы c валидными данными:
* Отправка формы с валидными данными карты. "Номер" = "4444 4444 4444 4441", "Месяц" = "08", "Год" = "23", "Владелец" = "IVAN PETROV", 
"CVV" = "345" (Ожидаемый результат - сообщние: "Успешно. Операция одобрена Банком");

27. Покупка с оплатой дебетовой картой со статусом DECLINED, отправка формы с валидными данными:
* Отправка формы с валидными данными карты. "Номер" = "4444 4444 4444 4442", "Месяц" = "08", "Год" = "23", "Владелец" = "IVAN PETROV", 
"CVV" = "345" (Ожидаемый результат - сообщние: "Ошибка! Банк отказал в проведении операции").

## Тестирование полей с данными

28. Отправка пустой формы
* Отправить пустую форму (Ожидаемый результат - под полями сообщния: "Поле обязательно для заполнения"

### Поле "Номер карты"

29. В поле "Номер карты" вводим номер другого формата. Например - 4444 4444 4444 4443 (Ожидаемый результат - сообщение: "Поле 
  обязательно для заполнения" или "Неверный формат");
30. В поле "Номер карты" вводим 16 нолей (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");
31. В поле "Номер карты" вводим 15 цифр. Например - 4444 4444 4444 444 (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения" или "Неверный формат");
32. Оставляем поле "Номер карты" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");
33. В поле "Номер карты" вводим буквы и специальные символы. Например - fhhb $*)@ jkjs уолц (Ожидаемый результат - сообщение: "Поле 
   обязательно для заполнения" или "Неверный формат")

### Поле "Месяц"

34. В поле "Месяц" вводим цифру больше 12 (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", 
  "Неверно указан срок действия карты" или "Неверный формат");
35. В поле "Месяц" вводим одну цифру (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", 
  "Неверно указан срок действия карты" или "Неверный формат");
36. Оставляем поле "Месяц" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок 
  действия карты" или "Неверный формат");
37. В поле "Месяц" вводим два ноля (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", 
  "Неверно указан срок действия карты" или "Неверный формат");
38. В поле "Месяц" вводим буквы и специальные символы. Например - h* (Ожидаемый результат - сообщение: "Поле 
   обязательно для заполнения" или "Неверный формат")

### Поле "Год"

39. В поле "Год" вводим значение меньше текущего года. Например - 22 (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения", "Неверно указан срок действия карты" или "Истёк срок действия карты");
40. В поле "Год" вводим одну цифру (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок действия карты" 
  или "Истёк срок действия карты");
41. Оставляем поле "Год" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок действия 
  карты" или "Истёк срок действия карты");
42. В поле "Год" вводим два нуля (Ожидаемый результат - сообщение: "Поле обязательно для заполнения", "Неверно указан срок действия карты" 
  или "Истёк срок действия карты"
43. В поле "Год" вводим буквы и специальные символы. Например - Р? (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения", "Неверно указан срок действия карты" или "Истёк срок действия карты").

### Поле "Владелец"

44. В поле "Владелец" вводим фамилию и имя на кириллице. Например - ИВАН ПЕТРОВ (Ожидаемый результат - сообщение: "Поле обязательно для 
  заполнения" или "Неверный формат");
45. В поле "Владелец" вводим буквы и специальные символы. Например - 23%$### *^^ (Ожидаемый результат - сообщение: 
  "Поле обязательно для заполнения" или "Неверный формат")
46. Оставляем поле "Владелец" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");

### Поле "CVV"

47. В поле "CVV" вводим одну или две цифры. например - 34 (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный 
  формат");
48. Оставляем поле "CVV" пустым (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный формат");
49. В поле "CVV" вводим три ноля (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или "Неверный 
  формат");
50. В поле "CVV" вводим буквы и специальные символы. Например - *Ц? (Ожидаемый результат - сообщение: "Поле обязательно для заполнения" или 
  "Неверный формат");

# 2. Список используемых инструментов

IntelliJ IDEA, Java 11,Git, Github, JUnit 5, Selenide, Lombok, Docker, Allure.

# 3. Список возможных рисков при автоматизации

* Изменение кода, строение сайта. Нужно будет переделывать тесты под новые данные;
* Эффект пестицида - это эффект, при котором при регулярном прогоне тестовых сценариев, ошибки перестают находиться;
* Если необходимые инструменты будут недоступны. Нужно будет искать замену и переделывать проект.

# 4. Интервальная оценка с учётом рисков в часах
* Подготовка к тестированию — 4 часа;
* Написание кода — от нескольких дней до нескольких недель (всё зависит от опыта и загруженности тестировщика);
* Подготовка отчета по тестированию — 10 часов.

# 5. План сдачи работ
* Написание и сдача авто-тестов — в течение 4-5 рабочих дней после согласования плана;
* Подготовка отчетов по тестированию — после тестов;
* Подготовка отчета автоматизации — через 2-3 рабочих днях после завершения тестирования.


























