## Service with scanning QR codes using a web camera    
---    

Cервис сканирования и распознавания QR кодов с помощью Web камеры     

Управление сервисом оуществляется с помощью команд отправляемых на JSON-RPC сервер    

Команды управления:    

Проверка работы сервиса   
```shell
{ "jsonrpc": "2.0", "method": "ping", "id": "13" }
```   

Включение WEB сканера    
```shell
{ "jsonrpc": "2.0", "method": "enable", "id": "15" }
```   

Выключение WEB сканера    
```shell
{ "jsonrpc": "2.0", "method": "disable", "id": "15" }
```    

Cчитывание сканированных данных    
```shell
{ "jsonrpc": "2.0", "method": "getscan", "id": "12" }
```     

Получение информации по работе с сервисом (help)    
```shell
{ "jsonrpc": "2.0", "method": "help", "id": "12" }
```

Настройка сервиса с помощью изменения файла ```.env```    
Переменные которые требуют изменения     
```WEBSCAN_WEBCAM``` - абсолютный путь к webcam    
```WEBSCAN_PORT``` -  порт на котором будет работать сервис    

Из диретории, где установлено приложение, возможно управление с помощью команд ```make```    
```shell
make install-webscan - Установка зависимостей и приложения
make uninstall - Удаление приложения
make run - Запуск приложения
make ping - Проверка работы сервиса
make enable	- Включение WEB сканера
make disable - Выключение WEB сканера
make getscan - Cчитывание сканированных данных
make info - Получение информации по работе с сервисом (help)
```    

Перед установкой приложение необходимо убедиться имеется ли в системе библиотека ```libzbar0``` - необходима для чтения данных QR кодов    
Установка ```libzbar0```  в случае необходимости   
```shell
sudo apt-get install libzbar0
```
Команда ```make install-webscan``` создает изолированное виртуальное окружение, куда устанавливается приложение    

Для корректной работы команд ```make ping, make enable, make disable, make getscan, make info```   
необходимо чтобы в системе были установлены утилиты ```curl, jq, zip```     
Установка ```curl``` и ```jq```  в случае необходимости   
```shell
sudo apt-get install curl jq zip unzip
```    

---
