# 🏥 ER-CXR AI Web Client

응급실 흉부 X-ray 판독 보조 AI 시스템의 웹 인터페이스입니다.

React + Vite 기반으로 구축되었으며, 의료진이 X-ray 이미지와 바이탈 사인을 입력하면 AI 분석 결과를 직관적으로 시각화합니다.

---

## 🛠 Tech Stack

| Category | Technology |
|----------|------------|
| Framework | React 18 |
| Build Tool | Vite |
| Language | JavaScript (ES6+) |
| Styling | CSS Modules |
| HTTP Client | Axios |

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18.0.0+
- npm

### Installation & Run
```bash
# 의존성 설치
npm install

# 개발 서버 실행
npm run dev

# 프로덕션 빌드
npm run build
```

---

## 📂 Project Structure
```
src/
├── api/           # API 호출 함수
├── assets/        # 이미지, 아이콘, 폰트
├── components/    # 재사용 UI 컴포넌트
├── pages/         # 페이지 컴포넌트
├── App.jsx        # 라우팅 설정
└── main.jsx       # Entry Point
```

---

## ✨ Key Features

**REM XTA UI Design Guidelines v1.0** 기반의 Flat Clinical UI를 적용했습니다.

### 📋 Smart Triage Dashboard
AI 분석 결과(Critical/Warning/Normal)와 KTAS 기준에 따라 위급 환자를 자동 정렬하여 빠른 의사결정을 지원합니다.

### 🖥 Scroll-free Interface
응급 상황을 고려한 Single-screen Layout으로, 스크롤 없이 모든 정보를 한 화면에서 확인할 수 있습니다.

### 🔄 Side-by-Side Comparison
과거/현재 X-ray 영상 비교 및 타임라인 뷰를 통한 병변 변화 추적 기능을 제공합니다.

### 🔬 Interactive AI Viewer
- **Heatmap Overlay**: AI 의심 병변 부위 시각화 (토글 가능)
- **Standard Tools**: Window/Level 조절, Zoom/Pan 기능

### ⚙️ Adjustable AI Threshold
실시간 슬라이더로 AI 민감도 임계값을 기관별/상황별 기준에 맞게 조정할 수 있습니다.

### 🎨 Medical-Safe Color System
의료 안전을 고려한 Semantic Colors(Soft Red/Green)와 Lucide React 아이콘을 사용합니다.