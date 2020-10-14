# Jarkom_Modul1_Lapres_D04

## Tim D4
## Kevin Angga Wijaya - 05111840000024
## Samuel C. Y. Sinambela -05111840000036

### Soal Praktikum Modul 1

Terdapat tiga buah file *.pcapng yang mendukung soal-soal display filter, yaitu:
- File pertama untuk menjawab soal nomor 1-5 dan nomor 10.
- File kedua untuk menjawab soal nomor 6, 7, dan 9.
- File ketiga untuk menjawab soal nomor 8.

#### Display Filter
1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!  
   - NGINX  
   - Bukti : http.host eq "testing.mekanis.me" lalu follow TCP Stream salah satu paket  
![Capture](https://user-images.githubusercontent.com/60419316/95985147-6df5df00-0e4e-11eb-88bd-531c5b2d3240.PNG)  

2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!  
   - Buka export object → http lalu filter file tersebut dengan “Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg”  
![1](https://user-images.githubusercontent.com/60419316/95985298-a1386e00-0e4e-11eb-9e85-6111551741bc.PNG)  
Lalu save dan buka isi file tersebut  
![3](https://user-images.githubusercontent.com/60419316/95985401-bf05d300-0e4e-11eb-8909-3b4b1ac54f12.PNG)  

3. Cari username dan password ketika login di "ppid.dpr.go.id"!  
   - filter : http.host== "ppid.dpr.go.id", lalu lihat isi paket yang “POST /index/login”  
![4](https://user-images.githubusercontent.com/60419316/95985522-e52b7300-0e4e-11eb-8d84-34903c475d6d.PNG)  
   - Username:10pemuda  
   - Password: guncangdunia  
![5](https://user-images.githubusercontent.com/60419316/95985589-f7a5ac80-0e4e-11eb-95b3-4b5ae6ca1177.PNG)  

4. Temukan paket dari web-web yang menggunakan basic authentication method!  
   - command : http.authbasic lalu lihat full url dari setiap paket dengan melakukan follow tcp stream  
![6](https://user-images.githubusercontent.com/60419316/95985740-24f25a80-0e4f-11eb-9a19-e1221d468488.PNG)  
   - http://testing.mekanis.me/  
   - http://aku.pengen.pw/  

5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!  
![7](https://user-images.githubusercontent.com/60419316/95985811-43585600-0e4f-11eb-939d-4e6ffe9c8336.PNG)  

6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).  
   - Menggunakan find untuk mencari “zipkey.txt”  
![8](https://user-images.githubusercontent.com/60419316/95985895-6420ab80-0e4f-11eb-96f4-27f489fd7595.PNG)  
   - Pada file “zipkey.txt” , di follow stream sehingga memunculkan password yang akan digunakan untuk mengekstrak file “Answer.zip”  
![9](https://user-images.githubusercontent.com/60419316/95985964-7bf82f80-0e4f-11eb-88d1-e8f48ca7fdb8.PNG)    
   - Mencari “Answer.zip”, lalu follow stream  
![10](https://user-images.githubusercontent.com/60419316/95986055-97fbd100-0e4f-11eb-925c-472a347928ea.PNG)  
   - Mensave raw nya, lalu disave dengan format nama “Answer.zip”  
![11](https://user-images.githubusercontent.com/60419316/95986110-aea22800-0e4f-11eb-9657-ed2d6452ca49.PNG)  
   - Membuka “Open This.pdf”  
![12](https://user-images.githubusercontent.com/60419316/95986165-c4175200-0e4f-11eb-8982-5c95f435c82f.PNG)  


7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"  
![13](https://user-images.githubusercontent.com/60419316/95986230-db563f80-0e4f-11eb-980d-ac6037645d24.PNG)  
   - Lalu follow TCP stream paket yang pertama  
![14](https://user-images.githubusercontent.com/60419316/95986286-edd07900-0e4f-11eb-93f4-85548324505a.PNG)  
   - Save as soal7.zip  
![15](https://user-images.githubusercontent.com/60419316/95986347-093b8400-0e50-11eb-8cce-f2bc3a91925f.PNG)
   - Buka Yes.pdf
![16](https://user-images.githubusercontent.com/60419316/95986382-19ebfa00-0e50-11eb-93fe-3c35fe2168e1.PNG)  

8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!  
   - Cari objek yang didownload menggunakan command : ftp.request.command == RETR  
   - Objek : Readme  
![17](https://user-images.githubusercontent.com/60419316/95986446-3425d800-0e50-11eb-83fa-8e6e1bfb000c.PNG)  

9. Cari username dan password ketika login FTP pada localhost!  
   - USER : dhana  
   - PASSWORD : dhana123  
   - Command : ftp.request.command == USER || ftp.request.command == PASS  
![18](https://user-images.githubusercontent.com/60419316/95986500-4d2e8900-0e50-11eb-9d5f-17e20a646ea3.PNG)  

10. Cari file .pdf di wireshark lalu download dan buka file tersebut!
clue: "25 50 44 46"  
![19](https://user-images.githubusercontent.com/60419316/95986530-5ddeff00-0e50-11eb-9a58-098890af3e2b.PNG)  
   - Follow TCP Stream paket tersebut.  
![20](https://user-images.githubusercontent.com/60419316/95986570-6df6de80-0e50-11eb-8374-b282fdd6cf56.PNG)  
   - Ganti dari ASCII jadi RAW lalu Save As  
![21](https://user-images.githubusercontent.com/60419316/95986625-849d3580-0e50-11eb-98e5-8b312949b407.PNG)  
![22](https://user-images.githubusercontent.com/60419316/95986706-9c74b980-0e50-11eb-80fe-8aeac2ed8da8.PNG)  
   - Isi file :  
![23](https://user-images.githubusercontent.com/60419316/95986760-af878980-0e50-11eb-9d10-8c3cd5cbf06e.PNG)  

#### Display Filter
11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
![24](https://user-images.githubusercontent.com/60419316/95987029-1311b700-0e51-11eb-9b53-b09b7e151823.PNG)  
   - Tulis port 21 dan pilih Adapter for Loopback traffic capture. Lalu buka cmd dan login pada ftp.  
![25](https://user-images.githubusercontent.com/60419316/95987078-22910000-0e51-11eb-9039-fac4b1922831.PNG)  
   - Wireshark akan menampilkan sebagai berikut:  
![26](https://user-images.githubusercontent.com/60419316/95987137-363c6680-0e51-11eb-9bde-beb34dfca3f6.PNG)  

12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!  
![27](https://user-images.githubusercontent.com/60419316/95987206-4b18fa00-0e51-11eb-91bf-fa7ecfcdc29a.PNG)  
   - Tulis port 80 dan pilih Wi-Fi. Lalu bukalah salah satu website dengan port 80(http), dalam hal ini saya membuka website http://jurnalotaku.com/  
![28](https://user-images.githubusercontent.com/60419316/95987252-5cfa9d00-0e51-11eb-8463-314bb81a52b4.PNG)  
   - Maka wireshark akan menampilkan sebagai berikut jika kita filter dengan : http.host == “jurnalotaku.com”  
![29](https://user-images.githubusercontent.com/60419316/95987308-70a60380-0e51-11eb-843f-f651591e0712.PNG)  
 
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!  
![30](https://user-images.githubusercontent.com/60419316/95987366-861b2d80-0e51-11eb-8de9-29150775fdeb.PNG)  
   - Tulis port 443 dan pilih Wi-Fi. Lalu bukalah salah satu website dengan port 443(https), dalam hal ini saya membuka website https://github.com/  
![31](https://user-images.githubusercontent.com/60419316/95987420-9b905780-0e51-11eb-9bd4-2c088538fc06.PNG)  
   - Lalu buka wireshark kembali, paket-paket dari github.com akan dicatat  
![32](https://user-images.githubusercontent.com/60419316/95987471-ac40cd80-0e51-11eb-8e7a-cea7a7f24a58.PNG)  

14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!  
![33](https://user-images.githubusercontent.com/60419316/95987522-c11d6100-0e51-11eb-8ea1-80248a979b5b.PNG)  
   - Pilih IPv4 address sebagai ip dalam hal ini 192.168.1.22, lalu ditaruh di capture wireshark dengan memilih Wi-Fi seperti berikut ini :  
![34](https://user-images.githubusercontent.com/60419316/95987580-d2ff0400-0e51-11eb-9f9c-e71a4ad40e82.PNG)  
   - Hasilnya seperti ini:  
![35](https://user-images.githubusercontent.com/60419316/95987636-e6aa6a80-0e51-11eb-8cc5-b190cbab2568.PNG)  
   - Misal membuka website dengan protokol http, seperti http://jurnalotaku.com/, maka ketika di display filter http.host==”jurnalotaku.com” akan menghasilkan sebagai berikut :  
![36](https://user-images.githubusercontent.com/60419316/95987690-f924a400-0e51-11eb-9d80-a105afc7f7f3.PNG)  

15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!   
   - Tuliskan di filter dst host monta.if.its.ac.id, lalu pilih Wi-Fi.  
![37](https://user-images.githubusercontent.com/60419316/95987758-0cd00a80-0e52-11eb-9c7c-f1356ef54ec9.PNG)  
   - Buka website  monta.if.its.ac.id, sehingga akan menghasilkan paket-paket sebagai berikut di wireshark :  
![38](https://user-images.githubusercontent.com/60419316/95987796-1d808080-0e52-11eb-8e1a-5491a66bdde6.PNG)
