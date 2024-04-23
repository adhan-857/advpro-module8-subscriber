### a) What is ***ampq***?
AMQP (*Advanced Message Queuing Protocol*) adalah sebuah protokol jaringan terbuka yang dirancang untuk mengirim pesan antar aplikasi atau organisasi dengan cara yang aman dan standar. Protokol ini memungkinkan interoperabilitas antara berbagai sistem pesan karena menyediakan spesifikasi yang jelas mengenai *message orientation, queuing, routing, reliability,* dan *security*. AMQP membantu *publisher* untuk berkomunikasi dengan *client*, dimana data atau pesan akan dikirimkan ke middleware ini dan client akan mendapatkan data atau pesan dari middleware tersebut.
<br>
<br>

### b) what it means? `guest:guest@localhost:5672`, what is the first ***quest***, and what is the second ***guest***, and what is ***localhost:5672*** is for?
`guest:guest` merupakan *username* dan *password* yang digunakan untuk autentikasi ke server AMQP. Kedua *guest* yang pertama adalah *username* dan yang kedua adalah *password*. `localhost` adalah *hostname* yang menunjukkan bahwa server berjalan pada *local computer*, yang berarti server tersebut berada pada komputer yang sama dengan *client* yang mengaksesnya. Terakhir, `:5672` adalah nomor *port* yang digunakan oleh server AMQP untuk menerima koneksi, yang merupakan *port* default untuk koneksi tanpa enkripsi pada server AMQP.
<br>
<br>

### Simulation slow subscriber
![image](https://github.com/adhan-857/my-first-repo/assets/119088782/6a475668-ba25-4690-a012-39e93e430aec)
Pada gambar di atas, terlihat bahwa terdapat **20 *message*** pada *queue* pada suatu waktu. Hal ini terjadi karena *subscriber* memerlukan waktu yang lebih lama untuk mengelola tiap *event* atau pesan dibandingkan *publisher* mengirim *event* atau pesan sehingga terjadi penumpukan *message*.