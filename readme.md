# Publisher App

## Reflection
> How many data will the publisher program send to the message broker in one run?

Program publisher mengirimkan 5 buah pesan ke message broker. Setiap pesan bertipe UserCreatedEventMessage yang berisi dua buah data string: user_id dan user_name.

> The url of "amqp://guest:guest@localhost:5672" is the same as the one in the subscriber program. What does it mean?

URL tersebut adalah string koneksi AMQP yang digunakan untuk terhubung ke server message broker (seperti RabbitMQ). Baik publisher maupun subscriber menggunakan URL yang sama, artinya:

* guest (pertama): adalah username untuk login ke broker.

* guest (kedua): adalah password dari username tersebut.

* localhost: berarti broker berjalan di komputer lokal (mesin yang sama).

* 5672: adalah port default yang digunakan oleh protokol AMQP.

Dengan menggunakan URL yang sama, artinya publisher dan subscriber terhubung ke instance RabbitMQ yang sama, sehingga:

* Publisher dapat mengirim pesan ke antrian (user_created)

* Subscriber dapat menerima pesan dari antrian yang sama