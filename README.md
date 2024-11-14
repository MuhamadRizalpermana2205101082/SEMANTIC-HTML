# SEMANTIC-HTML

## Praktikum SEMANTIC HTML
project analisis semantic html
Muhamad Rizal Permana 2205101083

name: Update README Analysis

on:
  push:
    paths:
      - '*.html'
      - '*.css'
    branches:
      - main

jobs:
  update-readme:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Write Analysis to README
        run: |
          echo "# Code Analysis" > README.md
          echo "" >> README.md
          
          echo "## Analisis" >> README.md
          echo "" >> README.md
          
          echo "### 1. HTML" >> README.md
          echo "- **Kesalahan Penulisan**: \`<!DOCTYPE html>\` kurang tanda seru, \`width=device-widh\` harusnya \`width=device-width\`, \`herf\` harusnya \`href\`, \`<u1>\` dan \`<1i>\` harusnya \`<ul>\` dan \`<li>\`, \`<selection>\` harusnya \`<section>\`." >> README.md
          echo "- **Struktur Tag**: Tag \`<head>\` tidak ada; harus menampung \`<meta>\` dan \`<link>\`." >> README.md
          echo "" >> README.md
          
          echo "### 2. CSS" >> README.md
          echo "- **Inkonistensi Nama**: \`grid-template-areas\` dan tag \`<section>\` perlu disesuaikan." >> README.md
          echo "- **Responsivitas**: Ukuran kolom/baris bisa diatur lebih responsif." >> README.md
          echo "- **Style Navigasi**: Tidak ada styling untuk \`<a>\` di dalam \`<nav>\`, jadi kurang menonjol." >> README.md
          echo "" >> README.md

          echo "## Kekurangan" >> README.md
          echo "" >> README.md
          echo "1. **HTML**: Banyak kesalahan penulisan seperti \`DOCTYPE\`, \`href\`, dan struktur \`<ul>\`-\`<li>\`, yang menyebabkan elemen tidak dikenali." >> README.md
          echo "2. **CSS**: Kurang responsif, tidak ada media queries untuk perangkat kecil." >> README.md
          echo "   - **Konten Placeholder**: \`<section>\` hanya berisi 'Konten', tanpa detail lebih lanjut." >> README.md
          echo "" >> README.md
          
          echo "## Perbedaan dari Kode Sebelumnya" >> README.md
          echo "" >> README.md
          echo "1. **HTML**: Kesalahan ejaan diperbaiki, struktur \`<ul>\`-\`<li>\` dibenahi." >> README.md
          echo "2. **CSS**: Struktur grid disederhanakan, layout konsisten dengan \`grid-template-areas\`." >> README.md

      - name: Commit changes
        run: |
          git config --global user.name "github-actions[bot]"
          git config --global user.email "github-actions[bot]@users.noreply.github.com"
          git add README.md
          git commit -m "Update README.md with HTML and CSS analysis"
          git push
        if: success()
