# Welcome to Kalkulator Expo 👋
![image](https://github.com/MuhammadYusuf07/react-native-expo/assets/124348537/b4371522-c097-4a3e-bc3c-f99a6d07f0d4)







## Penjelasan Algoritma

## Apa Itu State?

State dalam konteks pengembangan perangkat lunak mengacu pada kondisi atau keadaan suatu objek pada suatu waktu tertentu. Dalam React Native, setiap komponen dapat memiliki state sendiri yang digunakan untuk menyimpan data dinamis yang dapat berubah selama siklus hidup komponen tersebut.

## Contoh Penggunaan State dalam Komponen React Native

Dalam contoh kode yang diberikan, terdapat penggunaan state dalam komponen `App` untuk menyimpan input dari pengguna menggunakan `useState`:

```jsx
// State untuk menyimpan input dari pengguna
const [formInput, setFormInput] = useState('');


### Karakteristik State dalam React Native:

- **Data Dinamis:** State digunakan untuk menyimpan informasi yang dapat berubah selama interaksi pengguna dengan aplikasi.
- **Local pada Komponen:** Setiap komponen memiliki state sendiri yang bersifat lokal, tidak dapat diakses langsung oleh komponen lain.
- **Mutable (Dapat Diubah):** State dapat diperbarui menggunakan fungsi `setState`, sehingga memungkinkan komponen untuk merender ulang dengan data yang baru.
- **Penting untuk UI:** Digunakan untuk menyimpan informasi yang mempengaruhi tampilan dan interaksi pengguna dalam aplikasi.



**State `formInput` dan `setFormInput`:**
- `formInput` adalah state yang menyimpan ekspresi matematika yang dimasukkan oleh pengguna.
- `setFormInput` adalah fungsi untuk mengubah nilai dari `formInput`.

**Fungsi `handleSubmit`:**
- **Evaluasi Ekspresi Matematika:**
  - Menggunakan `eval(formInput)` untuk mengevaluasi ekspresi matematika yang ada dalam `formInput`.
  - Hasil evaluasi diubah menjadi string menggunakan `.toString()` dan disimpan kembali ke `formInput`.
- **Penanganan Error:**
  - Jika terjadi kesalahan selama evaluasi (misalnya, ekspresi tidak valid), pesan error dicetak di konsol menggunakan `console.error()` dan pengguna diberi tahu melalui `Alert.alert()`.

**Layout Tombol Kalkulator:**
- Tombol-tombol kalkulator dikelompokkan dalam beberapa baris menggunakan komponen `<View style={styles.item}>`.
- Setiap baris berisi beberapa `<TouchableOpacity>` yang mewakili tombol-tombol kalkulator.

**Penanganan Aksi Tombol:**
- Setiap `<TouchableOpacity>` memiliki prop `onPress` yang menentukan aksi yang diambil saat tombol ditekan.
- Contoh, tombol "Clear" mengosongkan `formInput`, tombol angka menambahkan angka tersebut ke `formInput`, dan tombol operasi matematika menambahkan operasi tersebut ke `formInput`.

**File `style.tsx`:**
- Digunakan untuk mengatur tata letak dan gaya dari komponen-komponen dalam aplikasi menggunakan StyleSheet dari React Native.
- Menggunakan `styles` untuk menetapkan gaya seperti warna, ukuran, dan tata letak tombol.

## Kesimpulan
Aplikasi Kalkulator ini memanfaatkan teknologi React Native dan TypeScript untuk menyediakan pengalaman interaktif dalam melakukan perhitungan matematika sederhana. Pengguna dapat dengan mudah memasukkan ekspresi matematika, dan aplikasi akan mengevaluasi secara langsung dengan menggunakan fungsi `eval()`. Dengan penanganan error yang baik, pengguna juga mendapatkan umpan balik yang jelas jika terjadi kesalahan dalam ekspresi yang dimasukkan. Dengan demikian, aplikasi ini tidak hanya memudahkan pengguna dalam melakukan perhitungan sehari-hari, tetapi juga memberikan pengalaman pengguna yang lebih interaktif dan informatif.
