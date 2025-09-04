<div align="center">

# 🔑 AWS EC2 SSH Access with Windows (PuTTY vs PowerShell)

<p align="center">
  <a href="https://aws.amazon.com/ec2/">
    <img src="https://img.shields.io/badge/AWS-EC2-orange?logo=amazonaws&logoColor=white" />
  </a>
  <a href="https://ubuntu.com">
    <img src="https://img.shields.io/badge/Ubuntu-24.04%20LTS-E95420?logo=ubuntu&logoColor=white" />
  </a>
  <a href="https://www.putty.org/">
    <img src="https://img.shields.io/badge/PuTTY-SSH%20Client-blue?logo=windows-terminal&logoColor=white" />
  </a>
  <a href="https://daringfireball.net/projects/markdown/">
    <img src="https://img.shields.io/badge/Made%20with-Markdown-000000?logo=markdown" />
  </a>
</p>

</div>

---

<div align="center">

## 🔽 Download PuTTY

[![Download PuTTY](https://img.shields.io/badge/Download-PuTTY-blue?logo=windows-terminal&logoColor=white)](https://www.putty.org/)  

Atau langsung ke situs resminya 👉 [PuTTY Official Download Page](https://www.putty.org/)

</div>

---

<p align="center">
  <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExeHprb2M2bmFzd3E1bDExOHM5a2FpNnZmeW5kbmNsZzVjNmkzeWhwdCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/iWkJkeurcTp7lJ1qUt/giphy.gif" width="500" />
</p>


---

## 📌 Pendahuluan
Ketika meluncurkan **EC2 Instance di AWS**, Amazon memberikan **Key Pair** berupa file `.pem`. File ini adalah **private key** untuk login ke server.  

- Di **Linux/macOS**, login langsung dengan perintah `ssh`.  
- Di **Windows**, ada dua opsi:
  1. **PowerShell/WSL** → bisa langsung pakai `.pem`.  
  2. **PuTTY** → harus convert `.pem` → `.ppk` dengan **PuTTYgen**.  

---

## 🖥️ 1. Menggunakan PowerShell (lebih simpel)

### ✅ Langkah-langkah
1. Simpan file key pair dari AWS, misalnya `my-key.pem`.  
2. Buka **PowerShell** lalu jalankan:  

   ```powershell
   ssh -i "C:\Users\<username>\Downloads\my-key.pem" ubuntu@<Public-IP>
   ```


🔐 2. Menggunakan PuTTY (butuh konversi key)
✅ Peranan PuTTY
PuTTY = aplikasi SSH Client untuk Windows.
Dulu Windows belum ada SSH bawaan → jadi PuTTY jadi alat utama untuk remote server.

✅ Peranan PuTTYgen
PuTTY hanya bisa pakai key .ppk.
Maka .pem → harus dikonversi ke .ppk dulu dengan PuTTYgen.

✅ Langkah-langkah
Buka PuTTYgen → klik Load → pilih my-key.pem.

Klik Save private key → simpan sebagai my-key.ppk.

Buka PuTTY → masukkan:

Host Name: ubuntu@<Public-IP>

Port: 22

Auth: Browse ke file my-key.ppk.

Klik Open → login berhasil.

```mermaid
flowchart TD
    A[AWS Download .pem Key] --> B{Windows User}
    B -->|Pakai PowerShell| C[Gunakan .pem langsung via ssh]
    B -->|Pakai PuTTY| D[Convert .pem → .ppk dengan PuTTYgen]
    D --> E[Gunakan .ppk di PuTTY untuk login]
```

| Opsi           | Kelebihan                    | Kekurangan                    |
| -------------- | ---------------------------- | ----------------------------- |
| **PowerShell** | Mudah, langsung pakai `.pem` | Hanya jalan di Windows modern |
| **PuTTY**      | Bisa dipakai di Windows lama | Harus convert `.pem` → `.ppk` |


---

## 📚 Referensi

- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [PuTTY Official Site](https://www.putty.org/)
- [Ubuntu Cloud](https://ubuntu.com/cloud)

---



<h3 align="center" style="color:#39ff14; font-size:1.5rem;">
💡 ☕ Traktir Kopi & Nasi Padang / Nasi Gorengnya ya cuy! 😄
</h3>

<div align="center">

<p style="color:#ffffff; font-size:1.1rem;">
Dukung terus biar semangat bikin karya edukatif lainnya...  
Keep supporting so I stay motivated to create more educational works!
</p>

<a href="https://www.paypal.com/paypalme/bungtempong99" target="_blank" style="text-decoration:none;">
  <img 
    src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-☕-FF6600?style=for-the-badge&logo=paypal&logoColor=white" 
    alt="Buy Me a Coffee" 
    style="margin-top:10px;"
  />
</a>

<p style="color:#39ff14; font-size:1rem; margin-top:8px;">
Support with ☕ so I can buy 🍜 and keep being 🧠!
</p>

</div>

---

<h2 align="center" style="color:#39ff14;">📫 Let’s Connect together</h2>

<p align="center">
  <a href="https://github.com/kongali1720" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-kongali1720-39ff14?style=for-the-badge&logo=github&logoColor=white" height="35">
  </a>
  <a href="mailto:admin@kongali1720.com">
    <img src="https://img.shields.io/badge/Email-admin@kongali1720.com-DAF7A6?style=for-the-badge&logo=gmail&logoColor=white" height="35">
  </a>
  <a href="https://discord.gg/dXM88zFU" target="_blank">
    <img src="https://img.shields.io/badge/Discord-kongali1720_32854-7289DA?style=for-the-badge&logo=discord&logoColor=white" height="35">
  </a>
  <a href="https://www.instagram.com/kongali1720/" target="_blank">
    <img src="https://img.shields.io/badge/Instagram-kongali-E1306C?style=for-the-badge&logo=instagram&logoColor=white" height="35">
  </a>
</p>

<p align="center">
  <a href="https://x.com/Kongali1720" target="_blank">
    <img src="https://img.shields.io/badge/X-@KongAli50422468-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" height="35">
  </a>
  <a href="https://younext.cloud" target="_blank">
    <img src="https://img.shields.io/badge/Web-Interactive-younext?style=for-the-badge&logo=web&logoColor=white" height="35">
  </a>
  <a href="https://kongali1720.com" target="_blank">
    <img src="https://img.shields.io/badge/Portfolio-kongali1720-FF69B4?style=for-the-badge&logo=portfolio&logoColor=white" height="35">
  </a>
  <a href="https://wa.me/447440014278" target="_blank">
    <img src="https://img.shields.io/badge/WhatsApp-+44_7440014278-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" height="35">
  </a>
</p>


---

<h3 align="center" style="color:#ff69b4;">❤️ 💻 INITIATING HUMANITY MODE... for Down Syndrome ❤️</h3>

<div align="center">

<table style="margin: 0 auto; border-collapse: collapse; box-shadow: 0 4px 10px rgba(0,0,0,0.2); border-radius: 8px; overflow: hidden;">
  <thead style="background-color:#ff69b4; color:white;">
    <tr>
      <th style="padding: 12px 25px; font-size: 18px;">Item</th>
      <th style="padding: 12px 25px; font-size: 18px;">Keterangan / Description</th>
    </tr>
  </thead>
  <tbody style="background-color:#1a1a1a; color:#39ff14;">
    <tr>
      <td style="padding: 12px 25px;">🎯 Target</td>
      <td style="padding: 12px 25px;">Anak-anak Pejuang Down Syndrome / Kids with Down Syndrome</td>
    </tr>
    <tr>
      <td style="padding: 12px 25px;">📡 Status</td>
      <td style="padding: 12px 25px;">Butuh Dukungan / Needs Support</td>
    </tr>
    <tr>
      <td style="padding: 12px 25px;">🧠 Response</td>
      <td style="padding: 12px 25px;">Buka Hati + Klik Link = Satu Senyum Baru / Open Heart + Click Link = One New Smile</td>
    </tr>
  </tbody>
</table>

<p align="center" style="margin-top:15px; color:white; font-size:1rem;">
Mereka bukan berbeda — mereka dilahirkan untuk mengajarkan dunia tentang cinta yang murni dan kesabaran yang luar biasa.<br>
They are not different — they were born to teach the world pure love and extraordinary patience.
</p>

<p align="center" style="margin-top: 15px;">
  <a href="https://mydonation4ds.github.io/" target="_blank" style="display: inline-block; text-decoration:none;">
    <img 
      src="https://img.shields.io/badge/SUPPORT--NOW-%23FF6600?style=for-the-badge&logo=heart&logoColor=white&labelColor=FF6600&color=FF4500&logoWidth=15" 
      alt="Support Now" 
      style="height: 40px;"
    />
  </a>
</p>

---

<section align="center" style="font-family: Arial, sans-serif;">

<h2 style="margin-bottom: 15px; color: #0070f3;">💳 Dukungan Pembayaran</h2>

<table align="center" style="margin: 0 auto; border-collapse: collapse; border-radius: 8px; overflow: hidden;">
  <thead style="background-color: #0070f3; color: white;">
    <tr>
      <th style="padding: 10px 20px; font-size: 16px;">Visa</th>
      <th style="padding: 10px 20px; font-size: 16px;">Mastercard</th>
      <th style="padding: 10px 20px; font-size: 16px;">PayPal</th>
    </tr>
  </thead>
  <tbody style="background-color: #f9f9f9;">
    <tr>
      <td style="padding: 10px;">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Visa_Logo.png/120px-Visa_Logo.png" alt="Visa" width="90" />
      </td>
      <td style="padding: 10px;">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Mastercard-logo.svg/120px-Mastercard-logo.svg.png" alt="Mastercard" width="90" />
      </td>
      <td style="padding: 10px;">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/PayPal_logo.svg/120px-PayPal_logo.svg.png" alt="PayPal" width="90" />
      </td>
    </tr>
  </tbody>
</table>

</section>

---

<p align="center" style="margin-top: 15px;">
  Kalau project ini bantu kamu, jangan lupa kasih bintang ⭐ dan share ke teman-teman!<br>
  Follow <a href="https://x.com/KongAli50422468" target="_blank">@KongAli50422468</a> untuk diskusi & update seru 🔥
</p>

<p align="center" style="margin-top: 10px;">
  <a href="https://x.com/KongAli50422468" target="_blank">
  </a>
</p>



