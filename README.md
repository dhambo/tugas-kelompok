# **LAPORAN PROJECT UTS STRUKTUR DATA**

## **Sistem Parkir Menggunakan Queue (Linked List)**

---

## **Identitas Kelompok**

* Nama Anggota 1: (Yustina Dhambo)

* NIM: (2501010337)

* GitHub: (https://github.com/dhambo/tugas-kelompok.git)

* Nama Anggota 2: (Apoilinarisa Jack Herment)

* NIM: (2501010333)

* GitHub: ([Link GitHub](https://github.com/dhambo/tugas-kelompok.git))

---

# **BAB I – PENDAHULUAN**

## **1.1 Latar Belakang**

Dalam kehidupan sehari-hari, sistem parkir sering digunakan di berbagai tempat seperti pusat perbelanjaan, kampus, dan perkantoran. Pengelolaan parkir yang tidak teratur dapat menyebabkan kemacetan dan ketidakefisienan.

Oleh karena itu, diperlukan suatu sistem yang mampu mengatur kendaraan masuk dan keluar secara terstruktur. Salah satu solusi yang dapat digunakan adalah dengan menerapkan struktur data queue (antrian) yang menggunakan prinsip FIFO (First In First Out).

---

## **1.2 Rumusan Masalah**

1. Bagaimana konsep queue (FIFO) dapat digunakan dalam sistem parkir?
2. Bagaimana implementasi linked list dalam membangun sistem parkir yang dinamis?
3. Bagaimana sistem parkir ini dapat meningkatkan efisiensi pengelolaan kendaraan?

---

## **1.3 Tujuan**

1. Menerapkan konsep queue dalam kasus nyata sistem parkir
2. Mengimplementasikan linked list dalam program
3. Membuat sistem parkir yang teratur dan efisien

---

# **BAB II – LANDASAN TEORI**

Struktur data adalah cara untuk menyimpan dan mengelola data agar dapat digunakan secara efisien. Pemilihan struktur data yang tepat akan mempengaruhi kinerja suatu program.

Queue adalah struktur data yang menggunakan prinsip FIFO (First In First Out), di mana elemen yang pertama masuk akan menjadi elemen pertama yang keluar. Konsep ini sangat cocok digunakan dalam sistem parkir satu jalur.

Berbeda dengan queue, stack menggunakan prinsip LIFO (Last In First Out). Namun, konsep stack tidak sesuai untuk sistem parkir karena kendaraan tidak keluar berdasarkan urutan terakhir masuk.

Implementasi queue dapat dilakukan menggunakan array atau linked list. Linked list lebih fleksibel karena tidak memiliki batas ukuran tetap dan memungkinkan penambahan serta penghapusan data secara dinamis.

### **Referensi**

* Cormen, T. H. – Introduction to Algorithms
* Weiss, M. A. – Data Structures and Algorithm Analysis
* Goodrich, M. T. – Data Structures and Algorithms

---

# **BAB III – DESAIN DAN IMPLEMENTASI SISTEM**

## **3.1 Desain Sistem**

Alur sistem:

Input → Proses → Output

* Input: Plat nomor kendaraan
* Proses: Enqueue, Dequeue, Peek
* Output: Data kendaraan dalam parkir

---

## **3.2 Pseudocode**

START
Buat queue parkir

ULANGI
  Tampilkan menu
  Input pilihan

  Jika pilihan = 1 → Enqueue
  Jika pilihan = 2 → Dequeue
  Jika pilihan = 3 → Peek
  Jika pilihan = 4 → Display
  Jika pilihan = 5 → Selesai

SELESAI

---

## **3.3 Implementasi Program (Python)**

```python
class Node:
    def __init__(self, plat):
        self.plat = plat
        self.next = None

class QueueParkir:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, plat):
        new_node = Node(plat)
        if self.rear is None:
            self.front = self.rear = new_node
            print("Kendaraan masuk:", plat)
            return
        self.rear.next = new_node
        self.rear = new_node
        print("Kendaraan masuk:", plat)

    def dequeue(self):
        if self.front is None:
            print("Parkiran kosong")
            return
        keluar = self.front
        self.front = self.front.next
        if self.front is None:
            self.rear = None
        print("Kendaraan keluar:", keluar.plat)

    def peek(self):
        if self.front is None:
            print("Parkiran kosong")
        else:
            print("Kendaraan terdepan:", self.front.plat)

    def display(self):
        if self.front is None:
            print("Parkiran kosong")
            return
        current = self.front
        print("Isi parkiran:")
        while current:
            print(current.plat, end=" -> ")
            current = current.next
        print("None")


parkir = QueueParkir()

while True:
    print("\n=== SISTEM PARKIR ===")
    print("1. Kendaraan Masuk")
    print("2. Kendaraan Keluar")
    print("3. Lihat Kendaraan Depan")
    print("4. Tampilkan Parkiran")
    print("5. Keluar")

    pilihan = int(input("Pilih: "))

    if pilihan == 1:
        plat = input("Masukkan plat nomor: ")
        parkir.enqueue(plat)
    elif pilihan == 2:
        parkir.dequeue()
    elif pilihan == 3:
        parkir.peek()
    elif pilihan == 4:
        parkir.display()
    elif pilihan == 5:
        break
```

---

# **BAB IV – KESIMPULAN**

Berdasarkan hasil implementasi, sistem parkir yang dibuat menggunakan struktur data queue berhasil mengatur kendaraan berdasarkan urutan kedatangan dengan prinsip FIFO.

Implementasi linked list memberikan fleksibilitas dalam pengelolaan data karena tidak memiliki batas kapasitas tetap. Sistem ini berjalan sesuai dengan teori struktur data dan mampu diterapkan pada kasus nyata.

Dengan adanya sistem ini, pengelolaan parkir menjadi lebih teratur, efisien, dan mudah dikontrol.

---


