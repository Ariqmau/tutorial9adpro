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
![image](https://github.com/user-attachments/assets/16a68b26-dce3-42db-8a14-79d11d74e5b0)
Panel kiri(publisher) mengirim 5 data setiap kali run(2x run), dan panel kanan(subscriber) menerima dan memproses data yang dikirim.

### Monitoring chart based on publisher
![image](https://github.com/user-attachments/assets/122ca0e7-d341-46ba-88fd-f173f343dd4c)
Spike pada chart mengindikasikan messages yang dikirim oleh publisher(2x run, 2 spike)

### Simulation slow subscriber
![image](https://github.com/user-attachments/assets/f0ec928e-e5fa-421c-bdc3-c5627e0187c5)
Puncak spike berada di 25 karena saya menjalankan `cargo run` publisher sebanyak 7x dan ada 5 pesan per run publisher, jadi ada 35 pesan. Namun, subscriber sudah menerima sebagian dari pesan tersebut jadi sisa yang belum sempat diproses pada titik tertinggi adalah 25.
