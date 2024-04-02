# API Automation Framework

Framework ini adalah sebuah kerangka kerja otomasi API yang dibangun menggunakan Java, TestNG, dan Apache HTTP Client. Kerangka kerja ini memungkinkan pengguna untuk melakukan otomatisasi pengujian API REST dengan mudah dan efisien.

## Langkah-langkah Penggunaan

### Langkah 1: Pilih Dependency

Menambahkan dependensi TestNG dan Apache HTTP Client ke dalam file `build.gradle`:

```
 dependencies{
// TestNG dependency
testImplementation group: 'org.testng', name: 'testng', version: '7.5'
// Apache dependency
    implementation 'org.apache.httpcomponents:httpclient:4.5.13'
}
```
### Langkah 2: Struktur Projek

Struktur projek untuk menyimpan _java class_ adalah sebagai berikut:
```
src/
└── test/
    └── java/
        └── com/
            └── example/
                ├── requests/
                ├── tests/
                └── utilities/
```

### Langkah 3: Implementasi Kode pada _Java Class_

_Java Class_:
1. **HttpClientHelper.java**: Kelas utilitas untuk mengirim HTTP request menggunakan Apache HTTP Client.
2. **APITest.java**: Kelas untuk menulis test cases menggunakan TestNG.
3. **TestRunner.java**: Kelas untuk menjalankan test cases.

### Langkah 4: Konfigurasi TestNG

File testng.xml untuk konfigurasi TestNG:

```
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >

<suite name="API Test Suite">
    <test name="API Tests">
        <classes>
            <class name="com.example.tests.APITest"/>
        </classes>
    </test>
</suite>
```

### Test Cases

1.    **Tes Positif**: Uji API untuk respons yang benar dengan input yang benar.
2.    **Tes Negatif**: Uji API untuk respons yang salah dengan input yang salah, seperti mengirim tipe data yang salah atau kolom wajib diisi tidak ada. (**Dengan expected dan actual result yang sesuai**)
3.    **Tes Batas**: Uji API untuk edge cases yang berbeda, seperti nilai maksimum atau minimum untuk parameter masukan.