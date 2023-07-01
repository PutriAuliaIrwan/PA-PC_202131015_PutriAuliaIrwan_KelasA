
# Project UAS

NAMA    : PUTRI AULIA IRWAN  
NIM     : 202131015  
KELAS   : PENGOLAHAN CITRA(A)

Teori yang mendukung mengenai projek terkait
Dalam konteks word segmentation, terdapat beberapa teori dan pendekatan yang mendukung pengembangan dan pemahaman tentang topik ini. Berikut adalah beberapa teori yang relevan:

1. Teori Morfologi: Teori morfologi berkaitan dengan struktur internal kata dan bagaimana kata-kata terbentuk dari unit-unit yang lebih kecil yang disebut morfem. Pendekatan berbasis morfologi mengasumsikan bahwa kata-kata dalam bahasa memiliki pola-pola tertentu yang dapat digunakan untuk memisahkan kata dalam teks yang tidak memiliki pemisah kata yang jelas. Teori morfologi membantu dalam mengidentifikasi dan memahami pola-pola ini.

2. Teori Linguistik Komputasional: Teori linguistik komputasional menggabungkan prinsip-prinsip linguistik dengan metode komputasional untuk memahami dan memodelkan bahasa. Dalam konteks word segmentation, teori ini membantu dalam mengembangkan algoritma dan model komputasional yang efektif untuk memisahkan kata dalam teks. Pendekatan berbasis aturan dan aturan transformasi berdasarkan teori ini digunakan untuk melakukan segmentasi kata.

3. Teori Pembelajaran Mesin: Pendekatan pembelajaran mesin telah digunakan secara luas dalam word segmentation. Teori ini melibatkan penggunaan algoritma pembelajaran mesin untuk mempelajari pola-pola dalam teks yang dapat digunakan untuk memisahkan kata. Metode seperti Conditional Random Fields (CRF), Hidden Markov Models (HMM), dan algoritma pembelajaran mesin lainnya digunakan dalam konteks word segmentation untuk mengidentifikasi pola dan fitur yang relevan dalam teks.

4. Teori Statistik dan Probabilitas: Teori statistik dan probabilitas memainkan peran penting dalam word segmentation. Metode berbasis statistik menggunakan model probabilitas untuk memprediksi kemungkinan segmen kata dalam teks. Pendekatan seperti n-gram language modeling dan model probabilitas berdasarkan korpus teks digunakan untuk menentukan kemungkinan segmen kata yang paling masuk akal.

5. Evaluasi dan Penilaian: Teori evaluasi dan penilaian memberikan kerangka kerja untuk mengukur kualitas segmentasi kata yang dihasilkan oleh algoritma. Metrik seperti precision, recall, dan F1-score digunakan untuk mengevaluasi kinerja algoritma word segmentation. Teori ini membantu dalam menguji dan memperbaiki algoritma word segmentation yang dikembangkan.

Dengan memadukan dan menggabungkan teori-teori ini, peneliti dan pengembang dapat mengembangkan pendekatan dan algoritma word segmentation yang lebih baik dan efektif.

##Tahapan cara menyelesaikan projek secara rinci:

import cv2 #bertujuan untuk menggunakan fungsi dan fitur yang disediakan oleh pustaka OpenCV (Open Source Computer Vision Library) dalam pemrosesan gambar dan penglihatan komputer

import numpy as np#berfungsi untuk membuat mengimport library atau plot data
import matplotlib.pyplot as plt

img = cv2.imread('putriauliairwan.jpeg')

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 

plt.imshow(img)
plt.show()#berfungsi untuk untuk membaca dan memuat sebuah gambar dalam format tertentu ke dalam sebuah variabel di Python

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY) #bertujuan untuk mengonversi gambar ke skala keabuan (grayscale) menggunakan library OpenCV

edged = cv2.Canny(gray, 30, 200) #bertujuan untuk mendeteksi tepi pada gambar dalam skala 
cv2.waitKey(0) #bertujuan untuk menunggu hingga tombol keyboard ditekan sebelum melanjutkan eksekusi program
contours, hierarchy = cv2.findContours(edged, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE) #bertujuan untuk menemukan kontur pada gambar yang telah dikenai deteksi tepi 
cv2.imshow('Canny Edges After Contouring', edged)#bertujuan untuk menyimpan gambar hasil deteksi tepi dalam file dengan format JPEG
cv2.imwrite('CannyFish.jpg', edged)  
cv2.waitKey(0) #Baris ini kembali menunggu tombol keyboard ditekan sebelum melanjutkan eksekusi program setelah menampilkan gambar hasil deteksi tepi

print("Number of Contours: " + str(len(contours))) #bertujuan untuk mencetak jumlah kontur yang ditemukan dalam gambar

cv2.drawContours(img, contours, -1, (0, 255, 0), 3) #bertujuan untuk menggambar kontur pada gambar img menggunakan library OpenCV

cv2.imshow('Contours', img) #Baris ini bertujuan untuk menampilkan gambar yang telah digambar kontur menggunakan fungsi imshow(). Gambar tersebut akan ditampilkan dalam jendela dengan judul "Contours"
cv2.imwrite('Contours.jpg', img) #ertujuan untuk menyimpan gambar yang telah digambar kontur dalam format JPEG
cv2.waitKey(0) #bertujuan untuk menunggu tombol keyboard ditekan sebelum melanjutkan eksekusi program

img2 = cv2.imread('putriauliairwan.jpg') #bertujuan untuk membaca gambar dengan nama file "putriauliairwan.jpg" dan menyimpannya dalam variabel img2 
if len(contours) != 0: #bertujuan untuk memeriksa apakah terdapat kontur yang ditemukan sebelumnya
	c = max(contours, key = cv2.contourArea)
cv2.drawContours(img2, c, -1, (0, 255, 0), 3) #bertujuan untuk menggambar kontur terbesar pada gambar img2 menggunakan warna hijau (0, 255, 0) dengan ketebalan garis sebesar 3
cv2.imshow('Largest Contour', img) #bertujuan untuk menampilkan gambar dengan kontur terbesar menggunakan fungsi imshow()
cv2.imwrite('LargestContour.jpg', img) #bertujuan untuk menyimpan gambar dengan kontur terbesar dalam format JPEG. Gambar tersebut akan disimpan dengan nama "LargestContour.jpg"
cv2.waitKey(0) #bertujuan untuk menunggu tombol keyboard ditekan sebelum melanjutkan eksekusi program

plt.imshow(img)
plt.show() #bertujuan untuk menampilkan gambar menggunakan matplotlib. Gambar tersebut akan ditampilkan menggunakan fungsi imshow() dari matplotlib, kemudian ditampilkan menggunakan show() 
