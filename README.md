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

----

#### Melakukan pengecekan untuk nilai NULL yang ada
Dengan menggunakan fungsi pandas, kita tidak perlu melihat satu persatu baris data untuk mengetahui apakah ada nilai kosong atau NULL/NAN pada suatu dataset. Bayangkan jika kita memilki 1000 baris data. Apakah kita harus melihat semua baris data tersebut? Tentu saja tidak. Maka dari itu di pandas disediakan fungsi untuk mengecek apakah ada data yang kosong.

```python
import pandas as pd
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")

print(csv_data.isnull().values.any())
```

<details>
<summary markdown="span">OUTPUT</summary>

![9](https://user-images.githubusercontent.com/112692717/202115847-d164dee5-0664-4e9c-8328-6fa60470da75.PNG)

</details>

----

#### Mengisi dengan Mean
Salah satu metode yang bisa dikatakan sebagai solusi yang umum pada kasus general data science adalah mengisi data kosong dengan menggunakan mean dari masing-masing kolom. Pertama kita harus menentukan mean dari masing-masing kolom. Pada pandas terdapat fungsi mean() untuk menentukan nilai mean dari masing-masing kolom. Mean sendiri digunakan untuk data yang memiliki sedikit sifat outlier/noisy/anomali dalam sebaran datanya maupun isinya.

```python
import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")

print(csv_data.mean())
print("Dataset yang masih terdapat nilai kosong ! :")
print(csv_data.head(10))

csv_data=csv_data.fillna(csv_data.mean())
print("Dataset yang sudah diproses Handling Missing Values dengan Mean :")
print(csv_data.head(10))
```

<details>
<summary markdown="span">OUTPUT</summary>

![10](https://user-images.githubusercontent.com/112692717/202115851-3331c140-7adf-4a54-9f93-f39824e275c4.PNG)

</details>

----

#### Mengisi dengan Median
Berbeda dengan mean pada sesi sebelumnya, median digunakan untuk data-data yang memiliki sifat outlier yang kuat. Kenapa median dipilih? Median merupakan nilai tengah yang artinya bukan hasil dari perhitungan yang melibatkan data outlier. Pada beberapa kasus, data outlier dianggap mengganggu dan sering dianggap noisy karena bisa mempengaruhi distribusi kelas dan mengganggu analisa pada klasterisasi (clustering).

```python
import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")
print("Dataset yang masih terdapat nilai kosong ! :")
print(csv_data.head(10))

csv_data=csv_data.fillna(csv_data.median())
print("Dataset yang sudah diproses Handling Missing Values dengan Median :")
print(csv_data.head(10))
```

<details>
<summary markdown="span">OUTPUT</summary>

![11](https://user-images.githubusercontent.com/112692717/202115855-0e95d9ee-85dc-4d8a-b67a-868fd9838b4f.PNG)

</details>

----

#### Praktek Normalisasi menggunakan Scikit Learn pada Python
Scikit Learn merupakan library pada python yang digunakan untuk machine learning dan data science. Salah satu library yang selalu menjadi favorit dan komunitasnya sangat kuat. Scikit-learn sendiri tidak hanya untuk analytics saja, namun juga untuk pre-processing, feature selection, dan proses analysis lainnya.

```python
import pandas as pd
import numpy as np
from sklearn import preprocessing
csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")
array = csv_data.values
X = array[:,2:5]
Y = array[:,0:1]

dataset=pd.DataFrame({"Customer ID":array[:,0],"Gender":array[:,1],"Age":array[:,2],"Income":array[:,3],"Spending Score":array[:,4]})
print("dataset sebelum dinormalisasi :")
print(dataset.head(10))

min_max_scaler = preprocessing.MinMaxScaler(feature_range=(0,1)) #inisialisasi normalisasi MinMax
data = min_max_scaler.fit_transform(X) #transformasi MinMax untuk fitur
dataset = pd.DataFrame({"Age":data[:,0],"Income":data[:,1],"Spending Score":data[:,2],"Customer ID":array[:,0],"Gender":array[:,1]})

print("dataset setelah dinormalisasi :")
print(dataset.head(10))
```

<details>
<summary markdown="span">OUTPUT</summary>

![12](https://user-images.githubusercontent.com/112692717/202115859-b8e20431-e03f-4ad7-8680-9b675cbcb7ea.PNG)

</details>
