# 🚀 Crypto Marketplace - เว็บไซต์ติดตาม Cryptocurrency

เว็บไซต์สำหรับติดตาม ราคา และข้อมูล Cryptocurrency แบบ Real-time ที่สร้างด้วย React + Vite

## ✨ คุณสมบัติหลัก

- 📊 แสดงข้อมูล Cryptocurrency แบบ Real-time
- 💱 รองรับหลายสกุลเงิน (USD, EUR, INR)
- 📈 กราฟแสดงแนวโน้มราคา
- 🔍 ค้นหา Cryptocurrency
- 📱 Responsive Design

## 🛠️ เทคโนโลยีที่ใช้

- **React 19** - Frontend Framework
- **Vite** - Build Tool
- **React Router** - Navigation
- **React Google Charts** - แสดงกราฟ
- **CoinGecko API** - ข้อมูล Cryptocurrency

## 📦 การติดตั้ง

### 1. Clone โปรเจค
```bash
git clone <repository-url>
cd crypto-marketplace
```

### 2. ติดตั้ง Dependencies
```bash
npm install
```

### 3. สร้าง API Key จาก CoinGecko

#### วิธีการสร้าง CoinGecko API Key:

1. **เข้าไปที่เว็บไซต์ CoinGecko**
   - ไปที่ [CoinGecko](https://www.coingecko.com/)

2. **สมัครสมาชิก**
   - คลิก "Sign Up" มุมบนขวา
   - กรอกข้อมูล: อีเมล, รหัสผ่าน
   - ยืนยันอีเมล

3. **เข้าไป Developer Dashboard**
   - เข้าสู่ระบบแล้วไปที่ [Developer Dashboard](https://www.coingecko.com/en/developers/dashboard)
   - หรือคลิกโปรไฟล์ → "Developer Dashboard"

4. **สร้าง API Key**
   - คลิก "Generate API Key" หรือ "Create API Key"
   - เลือก Plan (Demo Plan ฟรี)
   - ตั้งชื่อ API Key
   - คลิก "Generate"

5. **คัดลอก API Key**
   - คัดลอก API Key ที่ได้ (จะขึ้นต้นด้วย `CG-`)

#### ข้อจำกัด Demo Plan (ฟรี):
- **50 calls/minute**
- **10,000 calls/month**
- เข้าถึง API พื้นฐานได้

### 4. ตั้งค่า Environment Variables

สร้างไฟล์ `.env` ใน root directory:

```env
VITE_API_KEY=CG-your-api-key-here
```

**⚠️ สำคัญ**: 
- ใน Vite ต้องใช้ `VITE_` เป็น prefix
- ไม่ต้องใส่เครื่องหมาย `"` หรือ `'` รอบ API key
- ห้าม commit ไฟล์ `.env` (มี gitignore แล้ว)

### 5. รันโปรเจค
```bash
npm run dev
```

เปิดเบราว์เซอร์ไปที่ `http://localhost:5173`

## 📁 โครงสร้างโปรเจค

```
src/
├── components/          # Components ต่างๆ
│   ├── Footer/         # Footer component
│   ├── LineChart/      # กราฟแสดงแนวโน้มราคา
│   └── Navbar/         # Navigation bar
├── context/            # React Context
│   └── CoinContext.jsx # จัดการข้อมูล Cryptocurrency
├── pages/              # หน้าต่างๆ
│   ├── Home/          # หน้าหลัก
│   └── Coin/          # หน้าแสดงรายละเอียด Coin
├── assets/            # รูปภาพและไฟล์ static
└── App.jsx            # Main App component
```

## 🔧 Scripts ที่มีให้ใช้

```bash
# รัน Development server
npm run dev

# Build สำหรับ Production
npm run build

# ตรวจสอบ Code ด้วย ESLint
npm run lint

# Preview Production build
npm run preview
```

## 🌟 วิธีใช้งาน

### 1. หน้าหลัก (Home)
- ดูรายการ Cryptocurrency ท็อป 10
- เปลี่ยนสกุลเงิน (USD/EUR/INR)
- ค้นหา Cryptocurrency
- คลิกเพื่อดูรายละเอียด

### 2. หน้ารายละเอียด (Coin Details)
- ข้อมูลราคาปัจจุบัน
- กราฟแนวโน้มราคา 10 วันย้อนหลัง
- Market Cap, 24h High/Low
- Market Rank

### 3. การเปลี่ยนสกุลเงิน
- เลือกจาก Dropdown ใน Navbar
- รองรับ USD ($), EUR (€), INR (₹)

## ⚠️ การแก้ไขปัญหา

### ปัญหา API ไม่ทำงาน:

1. **ตรวจสอบ API Key**
   ```bash
   # เช็คว่า environment variable โหลดได้
   console.log(import.meta.env.VITE_API_KEY)
   ```

2. **ตรวจสอบไฟล์ .env**
   - อยู่ใน root directory (เดียวกับ package.json)
   - ไม่มีเครื่องหมาย `"` หรือ `'`
   - ขึ้นต้นด้วย `VITE_`

3. **Restart Development Server**
   ```bash
   # หยุด server (Ctrl+C) แล้วรันใหม่
   npm run dev
   ```

4. **ตรวจสอบ Network**
   - เปิด Developer Tools → Network tab
   - ดูว่า API calls ส่งไปหรือไม่
   - ตรวจสอบ Response status

### ปัญหา Rate Limit:

หาก API calls เกินขีดจำกัด:
- รอ 1 นาที (Demo Plan: 50 calls/minute)
- ลดการ refresh หน้า
- พิจารณาอัพเกรด Plan

## 🔒 ความปลอดภัย

- **API Key**: ใส่ในไฟล์ `.env` เท่านั้น
- **Git**: ไฟล์ `.env` ถูก ignore แล้ว
- **Production**: ใช้ Environment Variables ของ hosting service

## 🚀 Deploy

### Vercel:
1. Upload โปรเจคไป GitHub
2. Connect GitHub repo กับ Vercel
3. ตั้งค่า Environment Variable: `VITE_API_KEY`
4. Deploy!

### Netlify:
1. Build โปรเจค: `npm run build`
2. Upload folder `dist` ไป Netlify
3. ตั้งค่า Environment Variable: `VITE_API_KEY`

