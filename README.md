### Install Tailwind in CodeIgniter 3 

Hai,
saya berhasil menggunakan Tailwind CSS di proyek CodeIgniter 4 saya. Jika masih ada yang mencarinya, saya ikuti langkah-langkah di bawah ini:

- Langkah 1:

  Di folder proyek CodeIgniter, jalankan perintah di bawah ini untuk menginstal paket node dan membuat tailwind.config.js kosong

  Kode:
  ```bash
  npm install -D tailwindcss
  npx tailwindcss init
  ```
  
- Langkah 2:
  Perbarui  tailwind.config.js seperti di bawah ini:
  Kode:
  /** @type {import('tailwindcss').Config} */
  module.exports = {
    content: ["./app/Views/**/*.php"],
    theme: {
      extend: {},
    },
    plugins: [],
  }

- Langkah 3:
  Buat input.css dengan kode di bawah ini. Anda dapat membuatnya di mana saja. Saya buat di app > Views > css > input.css
  Kode:
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

- Langkah 4:
  Pada terminal di folder proyek CodeIgniter, jalankan perintah di bawah ini. Jika Anda menggunakan jalur yang berbeda untuk input.css dan output css (milik saya style.css) maka ubah jalur yang sesuai.
  Kode:
  npx tailwindcss -i ./app/Views/css/input.css -o ./public/assets/css/styles.css --watch

- Langkah 5:
  Sekarang cukup sertakan file css (milik saya style.css) di file php Anda. Dengan perintah Langkah 4, ini akan tetap berjalan, jadi jika Anda menambahkan kelas css tailwind apa pun di file php, maka secara otomatis akan menambahkannya ke file css keluaran.
  Semoga ini membantu!
