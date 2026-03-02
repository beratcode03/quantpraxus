# 🚀 Quantpraxus  
### YKS Analiz ve Performans Takip Sistemi

> Öğrenci performansını veriyle buluşturan, modern ve kapsamlı bir analiz platformu.

<div align="center">
  <img src="docs/images/dashboard.png" alt="Quantpraxus Dashboard Preview" width="800"/>
</div>

![Version](https://img.shields.io/badge/version-0.0.3-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Electron](https://img.shields.io/badge/electron-38.2.0-47848F.svg)
![React](https://img.shields.io/badge/react-18.3.1-61DAFB.svg)
![TypeScript](https://img.shields.io/badge/typescript-5.6.3-3178C6.svg)

---

## 🎯 About

Quantpraxus, YKS hazırlık sürecinde öğrenci performansını ölçülebilir ve analiz edilebilir hale getirmek için geliştirilmiş full-stack bir analiz platformudur.

Basit bir net takip aracından, performans trendlerini, konu bazlı eksikleri ve çalışma alışkanlıklarını analiz eden modüler bir sisteme evrilmiştir.

Web ve masaüstü (Electron) ortamlarında çalışır.

---

## ✨ Core Features

- 📊 Performance dashboard with trend analysis
- 📚 Subject-based weakness detection (TYT / AYT)
- ⏱ Integrated Pomodoro timer & task management
- 🖥 Offline-first desktop support (Electron)
- 💾 JSON data export / import
- 📈 Detailed mock exam tracking & statistics
- 🌙 Dark / Light theme support

---

## 🛠 Tech Stack

| Layer      | Technology |
|------------|------------|
| Frontend   | React 18, TypeScript, Tailwind CSS, Radix UI |
| Backend    | Node.js, Express |
| Database   | PostgreSQL (Drizzle ORM - planned) + Local JSON Storage |
| Desktop    | Electron, Electron Builder |
| Testing    | Vitest, Playwright |

---

## 🏗 System Architecture

```
User (React + Vite)
        ↓
API Client (Fetch)
        ↓
Express Server (Node.js)
        ↓
Storage Layer (Drizzle ORM)
        ↓
JSON Storage ↔ PostgreSQL (Planned)
```

---

## ⚙️ Engineering Challenges

### 1. ESM vs CJS Conflict
Vite (ESM) ile Electron (CJS) modül sistemi çakışması, ayrı build pipeline stratejisi uygulanarak çözüldü.

### 2. Timezone Normalization
UTC ve Türkiye saat farklarından doğan veri tutarsızlıkları, merkezi tarih yardımcı fonksiyonları ile normalize edildi.

### 3. Performance Optimization
1000+ kayıt içeren veri setlerinde:
- Optimize edilmiş sorgular
- Memoization teknikleri
- Lazy rendering

kullanılarak performans iyileştirildi.

---

## 📁 Project Structure

```
.
├── client/        # React + Electron frontend
├── server/        # Express backend
├── electron/      # Electron main process
├── shared/        # Shared types & schemas
├── data/          # JSON storage
└── tests/         # Unit & E2E tests
```

---

## 🚀 Installation

### Requirements
- Node.js >= 20
- npm or yarn

### Setup

```bash
git clone https://github.com/beratcode03/quantpraxus.git
cd quantpraxus
npm install
```

### Development

```bash
# Web
npm run dev

# Desktop
npm run electron:dev
```

### Production Build

```bash
# Web
npm run build

# Electron
npm run electron:build
```

---

## 🧪 Testing

```bash
npm run test
npx playwright test
npm run test:coverage
```

---

## 🔮 Roadmap

- [ ] Full PostgreSQL migration
- [ ] Mobile app (React Native)
- [ ] AI-based study recommendations
- [ ] Cloud sync support
- [ ] Social comparison system

---

## 👨‍💻 Author

Built by **Berat Cankır**.

Quantpraxus represents an end-to-end full-stack system — from database modeling to cross-platform desktop packaging.

Contributions, issues, and discussions are welcome.

---

## 📄 License

MIT License — see `LICENSE` file for details.

---

⭐ If you find this project useful, consider giving it a star.