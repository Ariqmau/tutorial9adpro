## Reflection
a. What is amqp?

AMQP (Advanced Message Queuing Protocol) adalah protokol standar yang digunakan untuk komunikasi antar aplikasi melalui sistem message queue.
`amqp://guest:guest@localhost:5672` pada kode, AMQP terhubung ke broker pesan RabbitMQ, yang digunakan untuk menerima dan mengirim pesan antar layanan.

b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what
is the second guest, and what is localhost:5672 is for?

Format `guest:guest@localhost:5672` adalah URL koneksi yang menunjukkan bahwa aplikasi akan masuk ke RabbitMQ menggunakan username guest dan password guest. Kata localhost berarti aplikasi terhubung ke server RabbitMQ yang berjalan di komputer lokal, dan angka 5672 adalah port default yang digunakan RabbitMQ untuk menerima koneksi AMQP