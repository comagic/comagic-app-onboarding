### Call to visit <br />

**Ценность интеграции**  <br />
Данная интеграция позволяет передавать заявки с ОМНИ-формы Такси в Call to visit.<br />  

 
### Подключение интеграции <br />    

1. Нажмите "Активен" на этой странице.<br />
2. Выполните настройку интеграции. <br />

- Создайте http уведомление в нашем ЛК.  <br />
    - Тип события : Заявка такси
    - метод POST
    - в URL укажите адрес из параметра Webhook url из настроек интеграции
    - в тело уведомления укажите следующее : <br />
  
 <Alert backgroundColor="#c3e8d7">

    {
    "deffered_trip":{{start_time}},
    "controller": "order",
    "action": "create",
    "src_lat": {{src_latitude}} ,
    "sig": "подставляется клиентом",
    "src_long": {{src_longitude}} ,
    "src_address": {{taxi_address}},
    "phone": {{visitor_phone_number}},
    "dst_address": "подставляется клиентом",
    "dst_lat": "подставляется клиентом",
    "dst_long": "подставляется клиентом",
    "project_id":  "подставляется клиентом"
    
    }
  
   Значения "sig", "dst_address", "dst_lat", "dst_long", "project_id"  уникальны и заполняются по каждому проекту клиента отдельно.

  </Alert>   
  <br />


3. Нажмите сохранить.   <br />
