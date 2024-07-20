**segmentasi citra gambar menggunakan metode k-means clustering**

|Nama|Nim|Kelas|
| :-: | :-: | :-: |
|Muhamad Jati Wasesa|312210481|TI.22.A5|
|Idris Syahrudin|312210467|TI.22.A5|
|Dimas Aditya Putranto|312210489|TI.22.A5|
|Hardi Wirkan|312210492|TI.22.A5|

**source code untuk melakukan segmentasi citra gambar menggunakan K-means clustering**
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
%matplotlib inline
# unutk membaca gambar gunakan gambar sesuai dengan yg dimiliki
image = cv2.imread('images/monarch.jpg')
# Change color to RGB (from BGR)
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image)

# berfungsi untuk Membentuk ulang gambar menjadi susunan piksel 2D dan 3 nilai
warna (RGB)
pixel_vals = image.reshape((-1,3))
# berfungsi untuk mengkonversikan ke tipe float
pixel_vals = np.float32(pixel_vals)

#baris kode di bawah ini menentukan kriteria agar algoritme berhenti berjalan,
#yang akan terjadi adalah 100 iterasi dijalankan atau epsilon (yang merupakan
akurasi yang dibutuhkan)
#menjadi 85%
criteria = (cv2.TERM_CRITERIA_EPS + cv2.TERM_CRITERIA_MAX_ITER, 100, 0.85)
# lalu lakukan k-means clustering dengan jumlah cluster yang ditetapkan sebagai 3
#juga pusat acak pada awalnya dipilih untuk pengelompokan k-means
k = 3
retval, labels, centers = cv2.kmeans(pixel_vals, k, None, criteria, 10,
cv2.KMEANS_RANDOM_CENTERS)
# mengonversi data menjadi nilai 8-bit
centers = np.uint8(centers)
segmented_data = centers[labels.flatten()]
# membentuk ulang data menjadi dimensi gambar asli
segmented_image = segmented_data.reshape((image.shape))
plt.imshow(segmented_image)
```

**Gambar awal**

![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 001](https://github.com/Muhjat7/k-means/assets/129918243/218d9fd2-1b14-4cbd-8312-f33ab1074c34)![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 002](https://github.com/Muhjat7/k-means/assets/129918243/267662c9-6524-4e9b-a0b9-df51bafeadcd)

![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 003](https://github.com/Muhjat7/k-means/assets/129918243/bf2178b9-5a3f-4a1b-8ce3-9ebf8a1bfb5a)![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 004](https://github.com/Muhjat7/k-means/assets/129918243/224b30c3-a762-44f8-b345-f6dcb300b134)









**Hasil segmentasi gambar menggunakan metode k-means clustering**

![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 005](https://github.com/Muhjat7/k-means/assets/129918243/15116b5b-9b7e-4bee-995d-32d7341c5a86)![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 006](https://github.com/Muhjat7/k-means/assets/129918243/4ed03568-20c8-4289-bc3d-c005755a86f0)

![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 007](https://github.com/Muhjat7/k-means/assets/129918243/bb7e3919-2a3f-4fa5-9898-f041da3af26c)![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 005](https://github.com/Muhjat7/k-means/assets/129918243/d7db9766-6d07-40b1-9543-62590cb2a7a3)










**Meta data**

![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 008](https://github.com/Muhjat7/k-means/assets/129918243/121b3dfa-3308-4d73-a28c-b7228f8d7986) <br>
<b>	Gambar awal</b> <br> <br>


![Aspose Words 557df43f-e579-4a8e-abbd-d9bec1c0f9ea 009](https://github.com/Muhjat7/k-means/assets/129918243/a78b628e-f42a-4c0e-9e90-984c61472f28) <br>
<b> setelah segmentasi gambar menggunakan metode k-means clustering </b>

