### Data Wrangling Python
Source : https://academy.dqlab.id/main/package/practice/79?pf=0

----

#### Sample of Dataset Project

<details>
<summary markdown="span">csv_data</summary>

![Lampiran 1](https://user-images.githubusercontent.com/112692717/202100360-cac89276-75e4-4f5d-84e5-e0fb845995ae.png)

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

![lampiran 2](https://user-images.githubusercontent.com/112692717/202102367-f4ec3df6-7de1-43b4-a463-40af9a6eb785.PNG)

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



</details>
