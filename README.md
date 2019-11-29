# mqtt-cert


Скрипт `cert.sh` генерирует сертификаты для MQTT брокера mosquitto: 
* CA сертификат и ключ 
* сертификат и ключ для сервера 
* сертификат и ключ для клиента
  
При своей работе, SH скрипт использует openssl.
Хочется, чтобы приложение на golang использовало https://golang.org/pkg/crypto/, а не вызов openssl (если это возможно).
Основная проблематика, это генерация валидных сертификатов, чтобы не было ошибки при подключении: "cannot validate certificate for because it doesn't contain any IP SANs" (если генерировать сертификаты через SH скрипт, то такой проблемы не возникает).
Работать приложение будет на базе Ubuntu.