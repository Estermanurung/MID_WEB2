## LATIHAN 1

## EXPERIMEN 1:@Controller vs @RestController
-Buka /test/view  → Apa yang muncul?   Muncul teks warna hitam tebal dan font yang besar yang berisi - Ini dari @Controller___________
-Buka /test/text  → Apa yang muncul?   Muncul teks dengan font kecil dan kata katanya - Ini dari @Controller + @ResponseBody → text langsung___________

-Apa perbedaannya?   
perbedaan nya di font tulisan nya yang satu tebal dan besar dan yang satu
kecil dan tipis banget tulisanya 
___________
-Kesimpulannya
@Controller tanpa @ResponseBody → return ___ (nama template/data langsung)-Mencari file di folder templates. 
Dengan @ResponseBody → return ___ (nama template/data langsung) data langsung teks polos atau JSON.

## Eksperimen 2: Apa Terjadi Jika Template Tidak Ada?

Apakah berhasil?           [Ya/Tidak] _Ya berhasil __________
HTTP Status code:          _500__________
Error message:             __Internal Server Error_________

Kesimpulan: Jika Controller return nama view yang tidak ada,
Spring akan mengembalikan error _404__ karena View Resolver tidak bisa menemukan
file template(seperti.html atau jsp) yang sesuai oleh controller___.

## EKSPERIMEN 3:  Perbedaan @RequestParam dan @PathVariable

| **URL** | **Hasil di Halaman**            |
| --- |---------------------------------|
| `/greet` | **Selamat Pagi, Mahasiswa ___** |
| `/greet?name=Budi` | **Selamat Pagi, Budi!___**      |
| `/greet?name=Budi&waktu=Siang` | **Selamat Siang, Budi___**      |
| `/greet/Ani` | **_Halo, Ani!__**               |
| `/greet/Ani/detail` | ** Halo, Ani!___**              |
| `/greet/Ani/detail?lang=EN` | **_Hello, Ani!__**              |

-**Pertanyaan:**

- URL mana yang pakai `@RequestParam`? **_yang memakai (?)/greet?name=Budi_ 
    dan /greet?name=Budi&waktu=Siang_**
- URL mana yang pakai `@PathVariable`? **_yang memakai (/) /greet/Ani dan /greet/Ani/detail__**
- URL mana yang pakai keduanya? **_/greet/Ani/detail?lang=EN__**

## Eksperimen 4: Tambahkan Halaman "About" & Category Summary



## ## **Pertanyaan Refleksi**

1. **Apa perbedaan antara `@Controller` dan `@RestController`? Dalam kasus apa kamu pakai masing-masing?**
2. **Perhatikan bahwa template `product/list.html` dipakai oleh 3 endpoint berbeda (list all, filter by category, search). Apa keuntungannya membuat template yang reusable seperti ini?**
3. **Kenapa Controller inject `ProductService` (bukan langsung akses data di ArrayList)? Apa yang terjadi kalau Controller langsung manage data?**
4. **Apa perbedaan `model.addAttribute("products", products)` dengan return `products` langsung seperti di `@RestController`?**
5. **Jika kamu buka `http://localhost:8080/products/abc` (ID bukan angka), apa yang terjadi? Kenapa?**
6. **Apa keuntungan pakai `@RequestMapping("/products")` di level class dibanding menulis full path di setiap `@GetMapping`?**
7. **Dalam lab ini, kata "Model" muncul dalam beberapa konteks berbeda. Sebutkan minimal 2 arti yang berbeda dan jelaskan perbedaannya.**