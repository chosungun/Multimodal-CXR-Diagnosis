./assets/banner.png

<div align="center">

# 🏥 REM XTA: Real-time Emergency Monitor
### 흉부 X-ray & 바이탈 멀티모달 기반 응급실 판독 보조 솔루션

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

[데모 영상 보기] • [문서(Docs)] • [AI 모델]

</div>

---

## 📖 Introduction
[cite_start]**REM XTA(X-ray Triage Assist)**는 과밀화된 응급실 환경에서 의료진의 신속하고 정확한 의사결정을 돕기 위해 개발된 웹 애플리케이션입니다[cite: 3, 4].
단순한 이미지 분류를 넘어, **흉부 엑스레이(CXR)**와 환자의 **활력 징후(Vital Signs)** 데이터를 결합한 **멀티모달(Multimodal) 딥러닝 모델**을 사용하여 폐질환 진단 정확도를 높였습니다.

## 📺 Project Demo
실제 웹 애플리케이션의 구동 모습과 시나리오 시연 영상입니다.

[![REM XTA Demo Video](http://img.youtube.com/vi/cdm94JtcWEc/maxresdefault.jpg)](https://www.youtube.com/watch?v=cdm94JtcWEc)

> **💡 시연 시나리오:** 환자 등록 → 바이탈/X-ray 입력 → AI 멀티모달 분석 → 히트맵 확인 → Triage(응급도) 분류

---

## ✨ Key Features

[cite_start]본 프로젝트는 현업 수준의 **UI/UX 가이드라인(REM UI Design Guide v1.0)**을 수립하고 이를 준수하여 개발되었습니다[cite: 1, 2].

### [cite_start]1. Smart Triage Dashboard [cite: 32, 33]
* **응급도 자동 분류:** AI 분석 결과와 KTAS(한국형 응급환자 분류도구) 기준에 따라 위급 환자를 리스트 최상단에 자동 정렬합니다.
* **실시간 모니터링:** Critical / Warning / Normal 상태를 직관적인 컬러 코드로 표시합니다.

### [cite_start]2. Specialized Viewer & Comparison [cite: 24, 25]
* **Side-by-Side 비교:** 환자의 과거 영상과 현재 영상을 나란히 배치하여 병변의 변화를 추적합니다.
* **AI Heatmap:** 모델이 주목한 병변 위치를 히트맵(CAM)으로 시각화하며, On/Off 토글이 가능합니다.

### [cite_start]3. Optimized for ER Workflow [cite: 19, 78, 112]
* **Scroll-free Interface:** 분초를 다투는 상황에서 정보 탐색 시간을 줄이기 위해, 스크롤 없는 단일 화면(Single-screen) 인터페이스를 구현했습니다.
* [cite_start]**Flat Clinical UI:** 의료진의 피로도를 낮추고 정보 가독성을 높이기 위해 그림자와 장식을 배제한 Flat Design을 적용했습니다[cite: 6, 14].

---

## 🛠 System Architecture

### Frontend (Client)
* [cite_start]**Framework:** React + Vite [cite: 110]
* [cite_start]**Style:** CSS Modules (Design System Variables applied) [cite: 110]
* [cite_start]**Design System:** [REM XTA UI Design Guidelines v1.0 (PDF)](./docs/REM_XTA_UI_Design_Guide.pdf) [cite: 1, 2]

### AI Model (Research)
* **Environment:** Google Colab Pro
* **Model:** CNN (EfficientNet/ResNet for Image) + MLP (for Tabular) Fusion Model
* **Dataset:** MIMIC-CXR (Image) + Pseudo Vital Data

---

## 📂 Directory Structure

```text
repo-name/
├── 📂 assets/                 # 리드미 배너, 스크린샷 이미지
├── 📂 docs/                   # 기획서 및 디자인 가이드 (PDF)
├── 📂 frontend/               # React 웹 애플리케이션 (Vite)
│   ├── src/
│   ├── public/
│   └── README.md              # 프론트엔드 실행 가이드
│
├── 📂 ai-model/               # AI 모델 학습 코드
│   ├── notebooks/             # Colab 학습용 .ipynb 파일
│   ├── weights/               # 학습된 모델 가중치
│   └── requirements.txt
│
└── README.md                  # 메인 프로젝트 설명서
```

## 🚀 Getting Started

### 1. Frontend (Web Client)
웹 인터페이스의 상세한 설치 및 실행 방법은 `frontend` 디렉토리의 가이드를 참고해 주세요.

> 👉 **[Go to Frontend Guide](./frontend/README.md)**

* **Key Command:** `npm run dev` (Vite)
* **Requirements:** Node.js 18+

### 2. AI Model Training (Research)
AI 모델 학습 및 추론 코드는 Google Colab 환경에서 바로 실행할 수 있도록 구성되어 있습니다.

1. `ai-model/notebooks/` 폴더의 **`01_multimodal_training.ipynb`** 파일을 확인합니다.
2. Google Colab에서 해당 파일을 엽니다. (Open in Colab)
3. 런타임 유형을 **GPU**로 설정한 후 셀을 순차적으로 실행합니다.
4. **Note:** 민감한 환자 데이터셋은 저장소에 포함되어 있지 않으므로, 제공된 샘플 데이터(`sample_vital.csv`)를 활용하거나 별도의 데이터 경로를 설정해야 합니다.

---

## 🎨 Design Reference
이 프로젝트는 현업 수준의 철저한 UI/UX 기획 단계를 거쳐 개발되었습니다.
상세한 디자인 원칙과 벤치마킹 포인트는 아래 **UI 디자인 가이드라인** 문서에서 확인하실 수 있습니다.

> 📄 **[View Full Design Guide (PDF)](./docs/REM_XTA_UI_Design_Guide.pdf)**

### [cite_start]Design Philosophy: Flat Clinical UI [cite: 6, 14]
* [cite_start]**Minimalism:** 그림자와 그라디언트를 배제하여 의료진의 시각적 피로도를 최소화하고 정보 가독성을 높였습니다. [cite: 17]
* [cite_start]**Scroll-free:** 모든 핵심 정보(X-ray, Vital, AI Score)를 스크롤 없이 한눈에 파악할 수 있는 **Single-screen Layout**을 적용했습니다. [cite: 19]

### [cite_start]Benchmarking [cite: 22]
* [cite_start]**Lunit INSIGHT CXR**의 핵심 기능을 벤치마킹하여, '과거 영상 자동 비교(Side-by-Side)' 및 'AI 임계값(Threshold) 조정' 기능을 구현했습니다. [cite: 23, 27, 28]

### [cite_start]Medical-Safe Color System [cite: 35]
* [cite_start]**Signature Blue:** 신뢰감을 주는 `#3D6BFF` (Primary 500)를 메인 컬러로 사용합니다. [cite: 38]
* [cite_start]**Semantic Colors:** 의료 안전을 위해, 너무 자극적이지 않은 **Soft Red**(#E85468)와 **Soft Green**(#52C39A)을 사용하여 위험도(Critical/Normal)를 표시합니다. [cite: 44, 45, 52, 60]

---

## 📬 Contact & Feedback

* **Author:** 조성은/shap2819@hs.ac.kr
* **GitHub:** https://github.com/chosungun

이 프로젝트가 도움이 되셨다면 ⭐️ **Star**를 눌러주세요!