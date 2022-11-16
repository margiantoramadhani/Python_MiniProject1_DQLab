### Data Wrangling Python
Source : https://academy.dqlab.id/main/package/practice/79?pf=0

----

#### Sample of Dataset Project

<details>
<summary markdown="span">csv_data</summary>

![1](https://user-images.githubusercontent.com/112692717/202115810-ca60b662-2d66-4f05-94bb-7753a630e17a.png)

</details>

----

#### Membaca file dengan menggunakan pandas
Sebagai salah satu library untuk melakukan proses awal dari analisis data, pandas juga memiliki kemampuan untuk membaca berbagai macam jenis file. Format yang bisa dibaca oleh pandas ada berbagai macam, antara lain .txt, .csv, .tsv, dan lainnya. Pandas tidak hanya bisa membaca file saja, namun juga bisa merubah data dari file menjadi bentuk dataframe yang akhirnya nanti bisa diakses, diagregasi dan diolah.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data)
```

<details>
<summary markdown="span">OUTPUT</summary>

![2](https://user-images.githubusercontent.com/112692717/202115817-eba11eb6-82ad-4b69-93b4-55d5648fcdb4.PNG)

</details>

----

#### Membaca file dengan menggunakan head()
Pada suatu kasus, data yang kita baca cukup banyak atau loading yang lama. Untuk memastikan data kita terbaca dengan baik dan bisa menampilkan data sebagian untuk ditampilkan secara benar, kita bisa memakai fungsi head().

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data.head())
```

<details>
<summary markdown="span">OUTPUT</summary>

![3](https://user-images.githubusercontent.com/112692717/202115819-dc250edb-9611-4572-939e-b6f58eee7c8b.PNG)

</details>

----

#### Melakukan akses data kolom
Dalam suatu analisis data ada kalanya kita hanya butuh melakukan akses beberapa data saja dan tidak perlu harus menampilkan semua data. Pada pandas kita bisa melakukan akses dalam berbagai kebutuhan. Mulai dari hanya akses kolom tertentu ataupun baris tertentu. Pada sesi kali ini kita akan mencoba untuk melakukan akses beberapa kolom tertentu pada suatu dataset.<\br>
Pertama yang harus dilakukan untuk melakukan akses kolom adalah mengetahui nama-nama kolom yang ada.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data["Age"])
```

<details>
<summary markdown="span">OUTPUT</summary>

![4](https://user-images.githubusercontent.com/112692717/202115823-b402ee19-d5b3-4c68-9d56-2e038a7c6ce6.PNG)

</details>

----

#### Melakukan akses data melalui baris
Selain melakukan akses data melalui kolom, dengan menggunakan pandas juga bisa melakukan akses dengan menggunakan baris. Berbeda dengan akses melalui kolom, fungsi untuk menampilkan data dari suatu baris adalah fungsi .iloc[i] dimana [i] menunjukan urutan baris yang akan ditampilkan yang dimana indexnya diawali dari 0.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data.iloc[5])
```

<details>
<summary markdown="span">OUTPUT</summary>

![5](https://user-images.githubusercontent.com/112692717/202115833-b26d5404-67aa-4ccf-85ac-c8a5d7ff7cea.PNG)

</details>

----

#### Menampilkan suatu data dari baris dan kolom tertentu
Tidak hanya dengan menentukan dari kolom dan baris, dengan menggunakan pandas kita juga bisa memanggil suatu data dari suatu baris dan kolom tertentu dalam satu waktu.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data["Age"].iloc[1])
print("Cuplikan Dataset:")
print(csv_data.head())
```

<details>
<summary markdown="span">OUTPUT</summary>

![6](https://user-images.githubusercontent.com/112692717/202115841-e7c277c8-3b1e-422f-a346-b617ac48f2bf.PNG)

</details>

----

#### Menampilkan data dalam range tertentu
Setelah menampilkan suatu kelompok data, bagaimana jika ingin menampilkan data dari baris ke 5 sampai ke 20 dari suatu dataset? Untuk mengantisipasi hal tersebut, pandas juga bisa menampilkan data dalam range tertentu, baik range untuk baris saja, kolom saja, dan range untuk baris dan kolom.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print("Menampilkan data ke 5 sampai kurang dari 10 dalam satu baris:")
print(csv_data.iloc[5:10])
```

<details>
<summary markdown="span">OUTPUT</summary>

![7](https://user-images.githubusercontent.com/112692717/202115844-4963ff52-7e23-4fe7-82c1-312d4f655cd2.PNG)

</details>

----

#### Menampilkan informasi statistik dengan Numpy
Mengetahui informasi statistik pada suatu data sangat penting. Mulai dari distribusi data, nilai max atau min, hingga standar deviasi dari suatu dataset. Jika datanya berjumlah dibawah 10 mungkin masih dikerjakan secara manual. Namun, bayangkan jika datanya sudah mencapai ratusan bahkan ribuan. Tidak mungkin pastinya untuk dilakukan secara manual. Maka dari itu pentingnya fungsi describe() pada pandas. Fungsi describe() ini memungkinkan untuk mengetahui informasi statistik dari suatu dataset secara cepat.</br>
Note : Banyak nilai NaN yang tampil. Hal itu karena pada dataset ada format data string yang akhirnya memunculkan format NaN.</br>
Untuk meminimalisir hal tersebut dan memfilter hanya data numerical saja, digunakan  exclude=["O"], dimana fungsi itu akan mengabaikan data yang non-numerical untuk diproses.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data.describe(exclude=["O"]))
```

<details>
<summary markdown="span">OUTPUT</summary>

![8](https://user-images.githubusercontent.com/112692717/202115845-2b15bd47-e477-4c2d-9eca-3a3c0abce7ac.PNG)

</details>
