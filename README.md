# 🎮 Board Game Hub & Online Arcade Portal

ศูนย์รวมปาร์ตี้บอร์ดเกมออนไลน์และออฟไลน์ (Online & Pass & Play Board Game Arcade) พัฒนาด้วย **HTML5, Vanilla JavaScript, Tailwind CSS** และซิงค์ข้อมูลเรียลไทม์ผ่าน **Firebase Realtime Database**

---

## 🚀 รายชื่อเกมในระบบ (Featured Games)

### 1. 🐺 Werewolf: Nightfall (หมาป่าสลายหมู่บ้าน - GM Guide Edition)
* **โหมดการเล่น:** Pass & Play (เครื่องเดียวด้วยระบบ GM Interactive Notebook) / Online Multiplayer (เร็วๆ นี้)
* **บทบาทในเกม (12 Roles):** Werewolf, Wolf Cub, Alpha Wolf, Seer, Bodyguard, Hunter, Prince, Silencer, Villager, Mayor, Fool, Doppelganger
* **ฟีเจอร์เด่น:**
  * **GM Master Player List:** ตารางสรุปรายชื่อ บทบาทลับ และสถานะผู้เล่นแบบเรียลไทม์สำหรับ GM
  * **Night Phase Checklist:** สคริปต์สเต็ปคำพูดนำเล่น พร้อมระบบเฉลยผลการส่องของ Seer บนจอ GM ทันที
  * **Automated Lynch Traits:** ตรวจสอบสกิลพิเศษอัตโนมัติ (เจ้าชายรอดพ้นประหารครั้งแรก, คนบ้าชนะทันที, พรานป่ายิงคนตายตาม)
  * **Win Condition Checker:** คำนวณฝั่งชนะอัตโนมัติเมื่อเงื่อนไขครบ

### 2. 🎭 Insider Game (เกมล่าหาผู้รู้คำตอบ v2.5)
* **โหมดการเล่น:** Pass & Play (เครื่องเดียว) และ Online Multiplayer (สร้างห้องด้วยรหัส 8 หลัก)
* **บทบาทในเกม:** Game Master (GM), Insider (ผู้แอบรู้คำตอบ), Common (ผู้ร่วมเล่นทั่วไป)
* **ฟีเจอร์เด่น:**
  * **Word Bank:** คลังคำศัพท์ภาษาไทยกว่า 100+ คำ (ดึงจาก Firebase หรือไฟล์ `wordBank.JSON`)
  * **Interactive Mascot:** มาสคอตเวกเตอร์ 3D กะพริบตาและโผล่มาทักทายผู้เล่น
  * **Timer & Voting System:** ระบบนับถอยหลัง 5 นาทีและระบบโหวตจับ Insider

---

## 📁 โครงสร้างไฟล์สำหรับอัปโหลดขึ้น GitHub (`github_deploy`)

```text
github_deploy/
├── index.html            # หน้าพอร์ทัลหลัก (Board Game Hub Portal)
├── insider_game.html     # ไฟล์หลักเกม Insider Game (v2.5)
├── werewolf_game.html    # ไฟล์หลักเกม Werewolf (GM Guide Edition)
├── wordBank.JSON         # คลังคำศัพท์ภาษาไทยสำหรับ Insider
├── werewolf_mascot.png   # ภาพมาสคอตหมาป่าสำหรับ Werewolf
├── firebase_rules.json   # กฎความปลอดภัย Realtime Database Rules
└── README.md             # เอกสารอธิบายโปรเจกต์
```

---

## 🌐 การนำไปเปิดใช้งานบน GitHub Pages

1. สร้าง Repository ใหม่บน GitHub (เช่น `boardgame-hub`)
2. คัดลอกไฟล์ทั้งหมดในโฟลเดอร์ `github_deploy` ไปวางและ Commit ขึ้น GitHub:
   ```bash
   git init
   git add .
   git commit -m "Deploy Board Game Hub & Games v2.5"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/boardgame-hub.git
   git push -u origin main
   ```
3. เปิดไปที่ **Settings ➔ Pages** ใน GitHub Repository ของคุณ
4. เลือก Branch เป็น `main` / Folder เป็น `/ (root)` แล้วกด **Save**
5. เข้าเล่นผ่าน URL ของ GitHub Pages ได้ทันที (เช่น `https://YOUR_USERNAME.github.io/boardgame-hub/`)

---

## 🔒 การตั้งค่า Firebase Security Rules

คัดลอกเนื้อหาในไฟล์ `firebase_rules.json` ไปวางในแท็บ **Rules** ของ Firebase Realtime Database Console เพื่อเปิดสิทธิ์อ่านเขียนโหนดสถิติ (`stats/werewolf`, `stats/insider`) สำหรับโหมดออฟไลน์
