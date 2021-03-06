# Kafka: запись и чтение данных

## Постановка задачи

Дан [CSV файл](https://www.kaggle.com/sootersaalu/amazon-top-50-bestselling-books-2009-2019)

Необходимо:
1. Создать в Kafka тему *books* с тремя секциями (partition).
2. Написать **Producer**, который будет читать файл, сериализовать его в JSON и отправлять в тему *books*.
3. Написать **Consumer**, который будет читать данные из темы *books* и выводить в *stdout* последние 5 записей (с максимальным значением *offset*) из каждой секции. При чтении темы одновременно можно хранить в памяти только 15 записей.

## Реализация

Решение построено на стандартном [Akka Streams](https://doc.akka.io/docs/akka/current/stream/index.html) и [Alpakka Kafka](https://doc.akka.io/docs/alpakka-kafka/current/index.html).

* **producer** - реализация *Producer*
* **consumer** - реализация *Consumer*
