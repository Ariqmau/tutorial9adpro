## Reflection
### Understanding subscriber and message broker

a. What is amqp?

AMQP (Advanced Message Queuing Protocol) adalah protokol standar yang digunakan untuk komunikasi antar aplikasi melalui sistem message queue.
`amqp://guest:guest@localhost:5672` pada kode, AMQP terhubung ke broker pesan RabbitMQ, yang digunakan untuk menerima dan mengirim pesan antar layanan.

b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what
is the second guest, and what is localhost:5672 is for?

Format `guest:guest@localhost:5672` adalah URL koneksi yang menunjukkan bahwa aplikasi akan masuk ke RabbitMQ menggunakan username guest dan password guest. Kata localhost berarti aplikasi terhubung ke server RabbitMQ yang berjalan di komputer lokal, dan angka 5672 adalah port default yang digunakan RabbitMQ untuk menerima koneksi AMQP.

### Understanding publisher and message broker
a. How much data your publisher program will send to the message broker in one run?

Pada function main di `publisher/main.rs` ada 5 data yang akan dikirim dengan setiap data berisi user id dan user username.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber
program, what does it mean?

Berarti publisher dan subscriber berbicara dengan broker yang sama, sehingga pesan yang dikirim publisher bisa diterima oleh subscriber melalui antrian yang sama.

### Running RabbitMQ as message broker
![image](https://github.com/user-attachments/assets/064c2a61-5eb5-40ec-bf82-fc53fa99c5ac)

### Sending and processing event
![image](https://github.com/user-attachments/assets/e6d64220-850b-4042-a523-9cd806f6a359)
