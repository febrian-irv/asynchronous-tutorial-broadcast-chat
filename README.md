## 2.1. Original code of broadcast chat
#### Server Terminal
![](msc/server.png)
#### Client Terminal
Client 1
![](msc/client1.png)
Client 2
![](msc/client2.png)
Client 3
![](msc/client3.png)

1 server dan 3 client dibuka pada pada 4 terminal berbeda. Terlihat bahwa setiap input message dari client akan dikirim kepada server dan diprint diserver itu sendiri. Setelah itu, server akan mengirimkan message itu kembali kesetiap client yang terhubung untuk diprint pada client tersebut.

## 2.2. Modifying the websocket port
Iya kedua file menggunakan websocket protocol yang sama. Hal tersebut terlihat pada listener dan client builder pada server dan client yang terdapat koneksi port yang dituju yaitu port 8080. Kedua file juga menggunakan tokio_websocket untuk websocket untuk menghandle komunikasi.

## 2.3. Small changes. Add some information to client
#### Server
![](msc/server2.png)
#### Client
Client 1
![](msc/clientinfo1.png)
Client 2
![](msc/clientinfo2.png)

Untuk menambahkan informasi terkait client pengirim maka diperlukan modifikasi pada bcast_tx.send() pada server. Hal tersebut karena server yang menerima alamat pengirim serta memiliki kemampuan untuk menentukan apa yang akan dikirimkan kembali kepada setiap client.