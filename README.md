# Kalkulator dengan Expo
## Nama : Muhammad Yusuf

# Penjelasan Code 
## Import Statements
```
import React, { useState } from 'react';
import { View, Text, TextInput, TouchableOpacity, Alert } from 'react-native';
import { styles } from './style'; // Import file style.tsx yang berisi StyleSheet
```

- React: Digunakan untuk membuat komponen React.
- useState: Hook yang digunakan untuk mendeklarasikan state dalam komponen fungsional.
- View, Text, TextInput, TouchableOpacity, Alert: Komponen bawaan dari React Native untuk membangun antarmuka pengguna.
- styles: Mengimpor gaya dari file style.tsx untuk styling komponen.

## Komponen Utama: App
```
const App = () => {
```

*`App` adalah komponen fungsional utama yang mengandung semua logika dan tampilan kalkulator.*
## State
```
const [formInput, setFormInput] = useState('');
```

- formInput: State yang digunakan untuk menyimpan input pengguna.
- setFormInput: Fungsi untuk mengubah nilai formInput.

## Fungsi `handleSubmit`
```
const handleSubmit = () => {
    try {
        // Mengevaluasi ekspresi matematika dan mengonversi hasil ke dalam string
        setFormInput(eval(formInput).toString());
    } catch (error) {
        console.error('Error during calculation:', error);
        Alert.alert('Error', 'Perhitungan tidak valid');
    }
};
```

- handleSubmit: Fungsi untuk menangani pengiriman perhitungan.
- try-catch: Blok untuk menangani kesalahan dalam perhitungan.
- eval: Fungsi JavaScript untuk mengevaluasi string sebagai ekspresi matematika.
- Alert: Menampilkan pesan kesalahan jika perhitungan tidak valid.

## Struktur Tampilan
```
return (
    <View style={styles.container}>
        <View style={styles.containerSibling}>
            <Text style={styles.h1}>Kalkulator React</Text>
            <TextInput
                style={styles.input}
                placeholder="Masukkan Perhitungan"
                onChangeText={setFormInput}
                value={formInput}
            />
```
- View: Kontainer utama untuk mengelompokkan elemen.
- Text: Komponen untuk menampilkan teks "Kalkulator React".
- TextInput: Input teks untuk pengguna memasukkan perhitungan.
- placeholder: Teks penanda di dalam input.
- onChangeText: Fungsi untuk mengubah nilai formInput ketika teks berubah.
- value: Nilai dari formInput.

## Tombol-Tombol Kalkulator
  ```
  <View style={styles.item}>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput('')}>
        <Text style={styles.buttonText}>Clear</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`(${formInput})`)}>
        <Text style={styles.buttonText}>( )</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}%`)}>
        <Text style={styles.buttonText}>%</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}/`)}>
        <Text style={styles.buttonText}>/</Text>
    </TouchableOpacity>
</View>
```

- TouchableOpacity: Komponen untuk membuat tombol yang dapat ditekan.
- onPress: Fungsi yang dijalankan ketika tombol ditekan.
- setFormInput: Mengubah nilai formInput sesuai tombol yang ditekan.
- Text: Teks di dalam tombol.

## Baris-Baris Tombol Lain
### Setiap baris tombol didefinisikan dengan cara yang sama, menambahkan angka atau operator ke `formInput`:

```
<View style={styles.item}>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}7`)}>
        <Text style={styles.buttonText}>7</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}8`)}>
        <Text style={styles.buttonText}>8</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}9`)}>
        <Text style={styles.buttonText}>9</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}*`)}>
        <Text style={styles.buttonText}>*</Text>
    </TouchableOpacity>
</View>
```

- Ini berlanjut untuk semua angka dan operator lain.

## Tombol Submit
```
<View style={styles.item}>
    <TouchableOpacity style={styles.button} onPress={handleSubmit}>
        <Text style={styles.buttonText}>Submit</Text>
    </TouchableOpacity>
</View>
```
- Tombol Submit menjalankan fungsi handleSubmit ketika ditekan.

## Export Komponen
```
export default App;
```
- export default App: Mengekspor komponen App agar dapat digunakan di tempat lain dalam aplikasi.



## Analoginya
*Bayangkan Anda sedang membuat sebuah kalkulator fisik. Anda punya layar untuk menampilkan angka dan tombol-tombol untuk memasukkan angka dan operasi matematika.*

## Penjelasan Algoritma dengan Analogi
### 1. Inisialisasi Komponen dan State
*Import dan inisialisasi:*

*Bayangkan Anda mengeluarkan semua bagian kalkulator dari kotak: layar, tombol, dan papan rangkaian.
Anda memasang semuanya di meja kerja Anda.*
```
import React, { useState } from 'react';
import { View, Text, TextInput, TouchableOpacity, Alert } from 'react-native';
import { styles } from './style';
```

## 2. Deklarasi Komponen App
### Membuat Kalkulator:

*Anda mulai merakit kalkulator. Anda memutuskan bagaimana layar dan tombol akan bekerja.*
```
const App = () => {
    const [formInput, setFormInput] = useState('');
formInput adalah layar kalkulator. Ia menyimpan apa yang sedang ditampilkan di layar.
setFormInput adalah cara Anda menulis sesuatu di layar.
```

## 3. Fungsi handleSubmit
### Menangani Pengiriman Perhitungan:

*Anda membuat mekanisme agar kalkulator bisa menghitung saat tombol sama dengan (=) ditekan.
Ketika tombol ini ditekan, kalkulator akan mencoba menghitung ekspresi yang ada di layar.*
```
const handleSubmit = () => {
    try {
        setFormInput(eval(formInput).toString());
    } catch (error) {
        console.error('Error during calculation:', error);
        Alert.alert('Error', 'Perhitungan tidak valid');
    }
};
```

- handleSubmit adalah fungsi yang dijalankan saat Anda menekan tombol = pada kalkulator.
- eval(formInput) adalah mekanisme di dalam kalkulator yang mencoba menghitung ekspresi matematika yang Anda masukkan.
*Jika ada kesalahan, kalkulator menampilkan pesan error.*

## 4. Struktur Tampilan dan Tombol
### Merakit Tampilan Kalkulator:

*Anda menempatkan layar di bagian atas kalkulator.*
*Di bawah layar, Anda menempatkan tombol-tombol yang bisa ditekan.*
```
return (
    <View style={styles.container}>
        <View style={styles.containerSibling}>
            <Text style={styles.h1}>Kalkulator React</Text>
            <TextInput
                style={styles.input}
                placeholder="Masukkan Perhitungan"
                onChangeText={setFormInput}
                value={formInput}
            />
```

- View adalah kotak utama kalkulator yang menyatukan semua bagian.
- Text adalah label yang menunjukkan ini adalah kalkulator.
- TextInput adalah layar kalkulator tempat Anda bisa mengetik angka dan operasi matematika.

## 5. Layout Tombol Kalkulator
### Menambahkan Tombol-Tombol:

*Anda menempatkan tombol-tombol angka dan operasi matematika di kalkulator.*
*Setiap tombol terhubung ke layar kalkulator dan menambahkan karakter yang sesuai ketika ditekan.*

```
<View style={styles.item}>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput('')}>
        <Text style={styles.buttonText}>Clear</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`(${formInput})`)}>
        <Text style={styles.buttonText}>( )</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}%`)}>
        <Text style={styles.buttonText}>%</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}/`)}>
        <Text style={styles.buttonText}>/</Text>
    </TouchableOpacity>
</View>
```

- TouchableOpacity adalah tombol yang bisa ditekan.
- onPress adalah apa yang terjadi ketika tombol ditekan, yaitu menambahkan karakter ke layar kalkulator.

## 6. Baris-Baris Tombol Lain
### Menambahkan Tombol Angka dan Operasi Lainnya:

*Anda menambahkan baris demi baris tombol angka dan operasi lainnya seperti `+`, `-`, `*`, dan `/`.*
*Setiap tombol memiliki fungsi yang sama, menambahkan karakter ke layar ketika ditekan.*

```
<View style={styles.item}>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}7`)}>
        <Text style={styles.buttonText}>7</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}8`)}>
        <Text style={styles.buttonText}>8</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}9`)}>
        <Text style={styles.buttonText}>9</Text>
    </TouchableOpacity>
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}*`)}>
        <Text style={styles.buttonText}>*</Text>
    </TouchableOpacity>
</View>
```

## 7. Tombol Submit
### Menambahkan Tombol Submit:

*Anda menambahkan tombol "=" yang akan menjalankan fungsi handleSubmit saat ditekan.*

```
<View style={styles.item}>
    <TouchableOpacity style={styles.button} onPress={handleSubmit}>
        <Text style={styles.buttonText}>Submit</Text>
    </TouchableOpacity>
</View>
```

*Tombol Submit menjalankan fungsi handleSubmit untuk menghitung ekspresi matematika yang ada di layar.*

## 8. Ekspor Komponen
### Menyelesaikan Kalkulator:

*Setelah semua bagian dirakit, Anda memasukkan kalkulator ke dalam kotak dan mengirimkannya untuk digunakan.*

j```
export default App;
export default App adalah cara Anda mengemas kalkulator ini sehingga bisa digunakan oleh orang lain.
```







# Welcome to Kalkulator Expo 👋
![image](https://github.com/MuhammadYusuf07/react-native-expo/assets/124348537/b4371522-c097-4a3e-bc3c-f99a6d07f0d4)

# Penjelasan Algoritma

**State `formInput` dan `setFormInput`:**
- `formInput` adalah variabel yang menyimpan ekspresi matematika yang dimasukkan oleh pengguna.
- `setFormInput` adalah fungsi untuk mengubah nilai dari `formInput`.

## Apa Itu State?

State dalam konteks pengembangan perangkat lunak mengacu pada kondisi atau keadaan suatu objek pada suatu waktu tertentu. Dalam React Native, setiap komponen dapat memiliki state sendiri yang digunakan untuk menyimpan data dinamis yang dapat berubah selama siklus hidup komponen tersebut.

### Contoh Penggunaan State dalam Komponen React Native

```jsx
// State untuk menyimpan input dari pengguna
const [formInput, setFormInput] = useState('');
```


**Fungsi `handleSubmit`:**
- **Evaluasi Ekspresi Matematika:**
  - Fungsi ini menggunakan `eval(formInput)` untuk mengevaluasi ekspresi matematika yang dimasukkan pengguna.
  - Hasil evaluasi diubah menjadi string menggunakan `.toString()` dan disimpan kembali ke `formInput`.
- **Penanganan Error:**
  - Jika terjadi kesalahan saat evaluasi (misalnya, ekspresi tidak valid), pesan error dicetak di konsol menggunakan `console.error()` dan pengguna diberi tahu melalui `Alert.alert()`.

# Contoh Penggunaan State dan Fungsi handleSubmit

## State untuk Menyimpan Input Pengguna

State `formInput` digunakan untuk menyimpan input yang dimasukkan pengguna melalui komponen `TextInput`. Ini memungkinkan aplikasi untuk secara dinamis menanggapi perubahan input pengguna dan memprosesnya sesuai dengan logika yang telah ditentukan.



```// State untuk menyimpan input dari pengguna
const [formInput, setFormInput] = useState('');
```


**Layout Tombol Kalkulator:**
- Tombol-tombol kalkulator dikelompokkan dalam beberapa baris menggunakan komponen `<View style={styles.item}>`.
- Setiap baris berisi beberapa `<TouchableOpacity>` yang mewakili tombol-tombol kalkulator.
- Tombol-tombol kalkulator diorganisir dalam beberapa baris menggunakan komponen <View style={styles.item}>. Setiap baris ini mengandung beberapa tombol <TouchableOpacity> yang bertindak sebagai input untuk operasi kalkulator.

**Contoh Code:**
``` <View style={styles.item}>
    {/* Tombol Clear */}
    <TouchableOpacity style={styles.button} onPress={() => setFormInput('')}>
        <Text style={styles.buttonText}>Clear</Text>
    </TouchableOpacity>
    {/* Tombol ( ) */}
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`(${formInput})`)}>
        <Text style={styles.buttonText}>( )</Text>
    </TouchableOpacity>
    {/* Tombol % */}
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}%`)}>
        <Text style={styles.buttonText}>%</Text>
    </TouchableOpacity>
    {/* Tombol / */}
    <TouchableOpacity style={styles.button} onPress={() => setFormInput(`${formInput}/`)}>
        <Text style={styles.buttonText}>/</Text>
    </TouchableOpacity>
</View>
```

**Penjelasan**
- Dalam contoh di atas, <View style={styles.item}> mengelompokkan tombol-tombol kalkulator ke dalam baris-baris. Setiap <TouchableOpacity> memiliki gaya yang ditentukan oleh styles.button dan styles.buttonText, yang mewakili tombol-tombol yang dapat ditekan untuk melakukan fungsi spesifik pada kalkulator.
- Pengguna dapat menghapus input (Clear), menggunakan tanda kurung untuk kelompok operasi (( )), menghitung persentase (%), dan melakukan pembagian (/) dengan menekan tombol-tombol ini. Ini memungkinkan interaksi yang intuitif dan efisien dengan kalkulator yang diimplementasikan dalam aplikasi React Native.



**Penanganan Aksi Tombol:**
- Setiap `<TouchableOpacity>` memiliki prop `onPress` yang menentukan aksi yang dilakukan saat tombol ditekan.
- Misalnya, tombol "Clear" mengosongkan `formInput`, tombol angka menambahkan angka tersebut ke `formInput`, dan tombol operasi matematika menambahkan operasi tersebut ke `formInput`.

**File `style.tsx`:**
- Digunakan untuk mengatur tata letak dan gaya dari komponen-komponen dalam aplikasi menggunakan StyleSheet dari React Native.
- Gaya seperti warna, ukuran, dan tata letak tombol ditetapkan menggunakan objek `styles`.

## Kesimpulan
Aplikasi Kalkulator ini dikembangkan dengan React Native dan TypeScript untuk memungkinkan pengguna melakukan perhitungan matematika sederhana secara interaktif. Pengguna dapat memasukkan ekspresi matematika, dan aplikasi akan mengevaluasinya langsung dengan menggunakan fungsi `eval()`. Dengan penanganan error yang baik, pengguna akan diberi tahu jika ada kesalahan dalam ekspresi yang dimasukkan, meningkatkan pengalaman pengguna secara keseluruhan.

