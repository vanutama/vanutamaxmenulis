# Konfigurasi Font untuk Post

File ini menjelaskan cara mengatur ukuran font untuk paragraf di semua post melalui `fontConfig.ts`.

## Lokasi Konfigurasi

Buka file: `src/config/fontConfig.ts`

## Pengaturan Font Paragraf

Di dalam `fontConfig.ts`, Anda akan menemukan bagian `postContent`:

```typescript
postContent: {
  // 段落 <p> 标签的字体大小
  paragraph: {
    fontSize: "1.05rem",        // Ukuran font dasar
    lineHeight: "1.8",          // Tinggi baris
    // Opsional: Ukuran font responsif (mobile, tablet, desktop)
    responsive: {
      mobile: "1rem",           // < 768px
      tablet: "1.05rem",        // 768px - 1024px
      desktop: "1.05rem",       // > 1024px
    },
  },
}
```

## Cara Mengubah Ukuran Font

### 1. Mengubah ukuran font dasar untuk semua device:

Ubah nilai `fontSize`:
```typescript
fontSize: "1.1rem",  // Lebih besar
fontSize: "0.95rem", // Lebih kecil
```

### 2. Mengubah tinggi baris:

Ubah nilai `lineHeight`:
```typescript
lineHeight: "2.0",   // Lebih longgar
lineHeight: "1.6",   // Lebih rapat
```

### 3. Mengubah ukuran responsif per device:

```typescript
responsive: {
  mobile: "0.95rem",    // Font kecil di mobile
  tablet: "1.05rem",    // Font sedang di tablet
  desktop: "1.15rem",   // Font besar di desktop
}
```

## Menerapkan Perubahan

Setelah mengubah nilai di `fontConfig.ts`, perubahan akan otomatis diterapkan ke file `markdown.css` yang mengatur styling untuk semua paragraf `<p>` dalam post.

Jika Anda menggunakan dev server, refresh browser untuk melihat perubahan.

## File yang Terkait

- **Konfigurasi**: `src/config/fontConfig.ts` - Tempat mengatur ukuran font
- **Styling**: `src/styles/markdown.css` - File yang menerapkan konfigurasi ke paragraf
- **Komponen**: `src/pages/posts/[...slug].astro` - Template post yang menggunakan styling

## Tips

- Gunakan satuan `rem` agar font-size responsif terhadap user preferences
- `1rem` = ukuran font dasar browser (biasanya 16px)
- `1.05rem` = 16.8px
- `1.1rem` = 17.6px
- Line-height yang baik untuk keterbacaan adalah antara 1.5 - 2.0
