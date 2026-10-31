# Template Modular arXiv Preprint

## Deskripsi

Template penulisan naskah ilmiah berbasis LaTeX dengan format preprint arXiv. Repositori ini mengadaptasi gaya visual publikasi NeurIPS (`arxiv.sty`) dengan pemisahan struktur naskah secara modular untuk mempermudah penulisan artikel panjang dan kolaborasi berbasis Git.

## Prasyarat

Distribusi TeX modern dengan dukungan PDFLaTeX:

- TeX Live (2020 atau lebih baru)
- MiKTeX (Windows)
- MacTeX (macOS)

Utilitas build pendukung: `latexmk` dan `bibtex`.

## Kompilasi

Kompilasi otomatis menggunakan `latexmk`:

```bash
latexmk -pdf Main.tex
```

Atau kompilasi manual menggunakan `pdflatex` dan `bibtex`:

```bash
pdflatex Main.tex
bibtex Main
pdflatex Main.tex
pdflatex Main.tex
```

Berkas keluaran `Main.pdf` akan dihasilkan di direktori utama.

## Pengiriman ke arXiv

Sistem automated build pada portal arXiv tidak menjalankan perintah `bibtex`. Sebelum mengunggah naskah:

1. Jalankan kompilasi lokal hingga berkas `Main.bbl` terbentuk di direktori kerja.
2. Pastikan penamaan berkas bibliografi identik dengan berkas utama (`Main.tex` dan `Main.bbl`).
3. Kompres repositori menjadi arsip `.tar.gz` atau `.zip` yang mencakup:
   - `Main.tex`, `Main.bbl`, `arxiv.sty`
   - Direktori `Pengaturan/`, `Konten/`, `Aset/`, dan `Referensi/`
4. Unggah arsip tersebut melalui portal submission arXiv.org.

## Lisensi

Proyek ini didistribusikan di bawah Lisensi MIT berdasarkan karya asli oleh [George Kour](https://github.com/kourgeorge/arxiv-style). Lihat berkas [LICENSE](LICENSE) untuk ketentuan lengkap.
