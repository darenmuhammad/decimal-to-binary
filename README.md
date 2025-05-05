# 📘 JavaScript Fundamental Concepts

Dokumentasi ini mencakup penjelasan dasar mengenai beberapa konsep penting dalam JavaScript: **Call Stack**, **Recursion**, dan **setTimeout**. Materi ini sangat berguna untuk memperkuat logika dan pemahaman pemrograman.

---

## 🧠 Call Stack

Call Stack adalah mekanisme **LIFO (Last In, First Out)** yang digunakan JavaScript untuk mengeksekusi fungsi.

### Cara Kerja:
1. Saat fungsi dipanggil, ia dimasukkan ke atas **stack**.
2. Saat fungsi selesai dieksekusi, ia **dikeluarkan dari stack**.
3. Jika fungsi memanggil fungsi lain, maka fungsi baru ditambahkan ke atas stack terlebih dahulu.

### Contoh:
```javascript
function greet() {
  console.log("Hello!");
}

function start() {
  greet();
  console.log("Start complete.");
}

start();
```

### Ilustrasi Stack:
```
start()    --> masuk ke stack
greet()    --> masuk ke stack
greet()    --> keluar
start()    --> lanjut & keluar
```

---

## 🔁 Recursion

Recursion adalah teknik fungsi yang **memanggil dirinya sendiri** hingga kondisi tertentu (base case) tercapai.

### Struktur Umum:
```javascript
function recursiveFunction() {
  if (condition) {
    return; // base case
  }
  recursiveFunction(); // recursive call
}
```

### Contoh: Faktorial
```javascript
function factorial(n) {
  if (n === 0) return 1;        // base case
  return n * factorial(n - 1);  // recursive case
}
console.log(factorial(5)); // Output: 120
```

> ⚠️ Pastikan selalu ada **base case** agar tidak terjadi infinite recursion.

---

## ⏱️ setTimeout()

`setTimeout()` adalah fungsi asynchronous yang digunakan untuk menunda eksekusi kode.

### Sintaks:
```javascript
setTimeout(function, delay_in_milliseconds);
```

### Contoh:
```javascript
console.log("Mulai...");
setTimeout(() => {
  console.log("Ditunda 2 detik");
}, 2000);
console.log("Selesai.");
```

### Output:
```
Mulai...
Selesai.
Ditunda 2 detik
```

> Karena bersifat asynchronous, `setTimeout` tidak menghambat eksekusi kode setelahnya.

---

## 📌 Kesimpulan

- **Call Stack** menentukan urutan eksekusi fungsi.
- **Recursion** memungkinkan fungsi memanggil dirinya sendiri.
- **setTimeout** membantu menunda eksekusi fungsi tanpa memblokir kode lain.
