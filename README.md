# Лабораторная работа №1: Основы HTTP
 
## Цель выполнения работы

Целью данной лабораторной работы является изучение основных принципов протокола HTTP.

Условие

## Задание №1. Анализ HTTP-запросов

1. Зайдите на сайт http://sandbox.usm.md/login.
2. Откройте вкладку Network в инструментах разработчика браузера.
3. Введите неверные данные для входа (например, username: student, password: studentpass).
4. Проанализируйте запросы, которые были отправлены на сервер.

5. Ответьте на следующие вопросы : 

- Какой метод HHTP был использован для отправки запроса?

   -  Для отправки запроса был использован метод POST . В инструментах разработчика браузера во вкладке Network , в разделе Headers ( Request Method ) видим что метод POST  

      ![1.2](https://github.com/wdevil6ixteen/Framework/blob/main/1.2.jpg)

 - Какие заголовки были отправлены в запросе?

    - При отправке в запрос был использован заголовок text/plain;charset=UTF-8 находим в разделе Headers - Response Headers - Content Type(text/plain;charset=UTF-8) - этот заголовок означает , что содержимое сообщения представлено в виде обычного текста , и интерпертируются как текст закодированный в UTF-8  
     
      ![1.3](https://github.com/wdevil6ixteen/Framework/blob/main/1.3.jpg)

  - Какие параметры были отправлены в запросе?

    - Обращаем внимание на раздел Payload . Там мы увидим отправленные нами данные, такие как username и password
  
     ![1.4](https://github.com/wdevil6ixteen/Framework/blob/main/1.4.jpg)
   
   - Какой код состояния был возвращен сервером?

     - В разделе Headers обратим внимание на Status Code и значение . В первом случае введенния правильного значения отображается - 200 OK , а в случае не правильного входа - 401 Unauthorized
      
      ![1.5](https://github.com/wdevil6ixteen/Framework/blob/main/1.5.jpg)

    - Какие заголовки были отправлены в ответе?  

      - Исходя из информации Network , сервер отправил пять заголовков

     - Далее , повторяем шаги, но используя правильные данные логина и пароля .

           -   Вместо 401 , код выявил знечение 200 OK

              ![1.6](https://github.com/wdevil6ixteen/Framework/blob/main/1.6.jpg)

    ## Задание №2. Составление HTTP-запросов

    (1)   GET / HTTP/1.1
HOST: http://sandbox.com
User-Agent: Melnic Chiril

    (2)   POST /cars HTTP/1.1
HOST: http://sandbox.com
Content-Type: application/json

{
"make" : "Toyota",
"model" : "Corolla",
"year": "2020"
}

    (3)  
    PUT /cars HTTP/1.1
HOST: http://sandbox.com/cars/1
User-Agent: Melnic Chiril
Content-Type: application/json

{
"make" : "Toyota",
"model" : "Corolla",
"year": "2021"
}

     (4)
POST /cars HTTP/1.1
Host: sandbox.com
Content-Type: application/json
User-Agent: John Doe
model=Corolla&make=Toyota&year=2020


Код 200 - если произведен с методом GET , и прошёл успешно
Код 201 - если произведен с методом POST , и прошёл успешно
Код 400 - В запросе есть ошибка, и сервер не понимает, что от него хотят
Код 401 - если пользователь не осуществил аутентификацию правильно,поэтому сервер не будет выполнять запрос
Код 403 - если пользователь осуществил запрос, не имел прав на его исполнение
Код 404 - в случае не правильного адреса
Код 500 - сбой в системе(сервере) , например нехватка памяти,или опять же сбой и т.д


## Задание №3. Дополнительное задание. HTTP_Quest

Работа выполнена через POSTMAN

Первым шагом выполняю отправку запроса с методом пост на нужный URL с моим именем и фамилией в качестве заголовка.
Успешно выполненный запрос предоставил следующий ответ от сервера:

![2](https://github.com/wdevil6ixteen/Framework/blob/main/1.jpg)

Далее, я произвожу PUT запрос с телом запроса моего возраста.

![2](https://github.com/wdevil6ixteen/Framework/blob/main/2.jpg)

Последним я произвожу GET запрос и получаю финальный секрет

![3](https://github.com/wdevil6ixteen/Framework/blob/main/3.jpg)

Секретный код : OSMcAggoDTc5DwAdCERGe0FCV2dTSH1Y

![4](https://github.com/wdevil6ixteen/Framework/blob/main/4.png)

## Использованные источники

Коды состояний: [https://ru.wikipedia.org/wiki/%D0%A1%D0%BF%D0%B8%D1%81%D0%BE%D0%BA_%D0%BA%D0%BE%D0%B4%D0%BE%D0%B2_%D1%81%D0%BE%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D1%8F_HTTP]
