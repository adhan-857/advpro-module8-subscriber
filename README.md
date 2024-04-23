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

### Reflection and Running at least three subscribers
**Subscriber 1:**<br>
![image](https://github.com/adhan-857/my-first-repo/assets/119088782/50975936-8a6c-48a3-b1bb-84385d43bddd)
<br>
<br>

**Subscriber 2:**<br>
![image](https://github.com/adhan-857/my-first-repo/assets/119088782/4ea826ee-25b0-4fca-b68a-351e6593d64f)
<br>
<br>

**Subscriber 3**:<br>
![image](https://github.com/adhan-857/my-first-repo/assets/119088782/e66f4720-b117-42ca-a4a4-e0dec1e337b4)
<br>
Dari tiga gambar di atas, dapat dilihat bahwa tiap *subscriber* memproses *event* yang berbeda secara bersamaan. *Subscriber* pertama akan memproses pesan dengan urutan *user id* 1-4-2-5-3, *subscriber* kedua akan memproses pesan dengan urutan *user* id 2-5-3-1-4, dan *subscriber* ketiga akan memproses pesan dengan urutan *user id* 3-1-4-2-5, begitu pun seterusnya.
<br>
<br>

![image](https://github.com/adhan-857/my-first-repo/assets/119088782/edd7ff50-49fc-40f6-833b-d8c9c55f0a04)
<br>
Terlihat bahwa message queue berkurang (menjadi lebih cepat dibandingkan) sebelumnya. Hal ini disebabkan karena sekarang pesan atau *event* tersebut telah diproses oleh lebih banyak *subscriber* sehingga tidak terjadi penumpukan seperti sebelumnya.
<br>
<br>
Menurut saya, salah satu cara untuk meningkatkan performa dari aplikasi *subscriber* adalah dengan membuatnya menjadi *multithreading*. Hal ini agar aplikasi dapat mengolah banyak *event* dari *publisher* sekaligus.