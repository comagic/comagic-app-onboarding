### Интеграция с EnvyCRM

**Ценность**  

Решение позволяет передавать в наш кабинет данные по сделкам, для дальнейшего построения Сквозной аналитики.

**Какие данные передаются**

- сделки: сумма сделки, статус, магазин, к которому относится сделка и тд; 
- воронка продаж и ее этапы;
- контакты;
- кастомные поля (с возможностью выбора).  

**Необходимые компоненты для работы интеграции**  
- Сквозная аналитика.

### Подключение интеграции 

Интеграция подключается в несколько шагов:

1. Нажмите "Активен" на этой странице.
2. Заполните поля/проставьте требуемые маркеры в настройках.  

**Авторизация в EnvyCRM**

Токен генерится в разделе  "Настройки" →  'Интеграция" →  "API"
![image](envycrm.jpg)

**Дополнительные поля** - Выберете дополнительные поля из EnvyCRM, которые необходимо передавать в CoMagic/UIS.


3. Создайте триггер в EnvyCRM на Webhook url сервиса CoMagic/UIS из настроек.   

- Настройки -> Интеграция -> Webhook

- Выбираем события "Создание сделки" и "Изменение этапа сделки"

![image](envy_webhook.gif)

4. Также в EnvyCRM необходимо создать поле “Сумма” в сделке.
В него необходимо вносить окончательную сумму сделки до перехода в завершающий этап воронки продаж. Название поля должно быть именно "Сумма"
![image](envy.jpg)

5. Нажмите сохранить.

После подключения интеграции сделки будут попадать в  Сырые данные -> Сделки.  
Для проверки корректности работы интеграции создайте тестовую сделку в EnvyCRM .
