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

