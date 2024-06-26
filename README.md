# Tugas Praktikum { Pertemuan ke 11 } <img src=https://logos-download.com/wp-content/uploads/2016/05/MySQL_logo_logotype.png width="130px" >


|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Wawan Suwandi|312310457|TI.23.A.5|Basis Data|

# Soal Latihan Praktikum ( Pegawai )

![alt text](picture/tabel1.PNG)

**Perintah SQL :**

```
CREATE TABLE pegawai (
    idpegawai VARCHAR(5) PRIMARY KEY,
    nama_depan VARCHAR(10) NOT NULL,
    nama_belakang VARCHAR(15) NOT NULL,
    email VARCHAR(25) UNIQUE KEY,
    telepon VARCHAR(15),
    tgl_kontrak DATA,
    id_job VARCHAR(5),
    gaji INT,
    tunjangan INT
    );
```

***Output :***

![Cuplikan layar 2024-05-24 225230](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/ef4a7354-439d-49cb-94eb-a14188e2c24d)


```
INSERT INTO pegawai VALUES
    ('E001', 'Erine', 'Etherium', 'erine@yahoo.com', '07117059004', '2005-09-01', 'L001', 2000000, 500000),
	('E002', 'Zyzy', 'Force', 'zyzy@yahoo.com', '081312345678', '2006-09-01', 'L002', 2000000, 200000),
	('E003', 'Light', 'Yagami', 'light@gmail.com', '081367384322', '2006-10-01', 'L003', 1500000, NULL),
	('E004', 'Senku', 'Yagami', 'senku@gmail.com', '081363484342', '2006-10-01', 'L004', 1500000, 9),
	('E005', 'Nathan', 'noel', 'nathan@yahoo.com', '08163454555', '2007-09-01', 'L005', 1250000, 9),
	('E006', 'Udin', 'Firmansyah', 'udin@yahoo.com', '08527388432', '2008-09-01', 'L006', 1750000, NULL);
```

***Output :***

![Cuplikan layar 2024-05-24 234139](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/30de5d3c-8b22-4893-94ca-7f2489ca2452)

## Tugas Praktikum

**1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !**

```
SELECT*FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```

***Output :***

![Cuplikan layar 2024-05-24 234332](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/730810ca-a2fc-4b13-a0d3-50be12962dd2)

**2. Tampilkan pegawai yang tunjangannya NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NULL;
```

***Output :***

![Cuplikan layar 2024-05-24 234425](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/fd0127a1-8e4a-4123-816b-e5e469a469f7)



**3. Tampilkan pegawai yang tunjangannya tidak NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NOT NULL;
```

***Output :***

![Cuplikan layar 2024-05-24 234513](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/578af578-38ee-4593-8f30-55bfefd6e292)


**4. Tampilkan/hitung jumlah baris/record tabel pegawai!**

```
SELECT COUNT(*) AS jmlh_pegawai FROM pegawai;
```

***Output :***

![Cuplikan layar 2024-05-24 234612](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/98b3f23d-8d30-4762-9bf5-3e79062a4299)


**5. Tampilkan/hitung jumlah total gaji di tabel pegawai!**

```
SELECT SUM(gaji) AS ttl_gaji FROM pegawai;
```

***Output :***

![Cuplikan layar 2024-05-24 234723](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/33b31a54-e2c3-45b3-828d-b03da9f7be91)



**6. Tampilkan/hitung rata-rata gaji pegawai!**

```
SELECT AVG(gaji) AS mean_gaji FROM pegawai;
```
.
***Output :***

![Cuplikan layar 2024-05-24 234757](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/d7c180df-5550-4264-8d82-d3576fd59427)

**7. Tampilkan gaji terkecil!**

```
SELECT MIN(gaji) AS terkecil FROM pegawai;
```

***Output :***

![Cuplikan layar 2024-05-24 234834](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/4a1a88c5-e0e5-4a92-8c28-98d2757e6577)



**8. Tampilkan gaji terbesar!**

```
SELECT MAX(gaji) AS terbesar FROM pegawai;
```

***Output :***

![Cuplikan layar 2024-05-24 234927](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/efd3dd8c-3230-4781-92c8-3871637e14bb)


# Soal Latihan Praktikum ( Hewan )

![alt text](picture/tabel2.PNG)

**Perintah SQL :**

```
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );
```

***Output :***

![Cuplikan layar 2024-05-25 001539](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/f56a52f0-f040-4d5e-b1fb-43ed86dea83e)


```
INSERT INTO hewan VALUES
    ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
    ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
    ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
    ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
    ('p5', 'Fang', 'Benny', 'Dog', 'M'),
    ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
    ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
    ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
    ('p9', 'Slim', 'Benny', 'Snake', 'M');
```

***Output :***

![Cuplikan layar 2024-05-25 003408](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/33ab3913-ade1-4d29-b5c5-a9be03d144c0)


## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY owner;
```

***Output :***

![Cuplikan layar 2024-05-25 003536](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/338392bd-3ecf-4254-9350-ee1e90b0ed26)


**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY species;
```

***Output :***


![Cuplikan layar 2024-05-25 004404](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/caaef04f-d9c4-4ef4-8ade-c4ce05405905)


**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY sex;
```

***Output :***


![Cuplikan layar 2024-05-25 003626](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/7e900594-d831-4680-b294-e3e16230f7eb)

**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***

![Cuplikan layar 2024-05-25 003713](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/74adde18-6300-49c2-9872-0d91f94e23a4)

**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***

![Cuplikan layar 2024-05-25 005052](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/b77d9454-cdb9-4e10-a37c-2449702ef07d)


**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***

![Cuplikan layar 2024-05-25 005247](https://github.com/Ws529/Basis-data-Pertemuan11/assets/147570983/71905696-b813-4a44-8385-99ac97518593)



## Berikan Kesimpulan Anda !

Terdapat beberapa ***Query Filter*** yang ditemukan pada tugas praktikum 4 :

- Operator `IN` digunakan untuk memfilter data yang terdapat pada list IN
- Operator `NOT IN` digunakan untuk memfilter data yang tidak terdapat pada list IN
- Operator `IS NULL` digunakan untuk menampilkan data dengan nilai data NULL
- Operator `IS NOT NULL` digunakan untuk menampilkan data dengan nilai data tidak NULL
- `COUNT` adalah perintah yang digunakan untuk menghitung jumlah baris suatu kolom pada tabel.
- `SUM` adalah perintah yang digunakan untuk menghitung jumlah nilai suatu kolom pada tabel.
- `AVG` adalah perintah yang digunakan untuk menghitung rata-rata dari nilai suatu kolom pada tabel.
- `MIN` adalah perintah yang digunakan untuk menampilkan nilai terkecil dari suatu kolom pada tabel.
- `MAX` adalah perintah yang digunakan untuk menampilkan nilai terbesar dari suatu kolom pada tabel.
- Klausa `GROUP BY` berfungsi untuk mengelompokkan data berdasarkan field tertentu.

## FINISH. <img align="center" alt="Ikhsan-Python" height="40" width="45" src="https://em-content.zobj.net/source/microsoft-teams/337/student_1f9d1-200d-1f393.png"> <img align="center" alt="Ikhsan-Python" height="40" width="45" src="https://em-content.zobj.net/thumbs/160/twitter/348/flag-indonesia_1f1ee-1f1e9.png">
