# VeighNa (vn.py) - 퀀트 트레이더를 위한 파이썬 오픈소스 트레이딩 시스템

<p align="center">
  <img src ="https://vnpy.oss-cn-shanghai.aliyuncs.com/veighna-logo.png"/>
</p>

💬 [**English README**](README_ENG.md)

<p align="center">
    <img src ="https://img.shields.io/badge/version-4.3.0-blueviolet.svg"/>
    <img src ="https://img.shields.io/badge/platform-windows|linux|macos-yellow.svg"/>
    <img src ="https://img.shields.io/badge/python-3.10|3.11|3.12|3.13-blue.svg" />
    <img src ="https://img.shields.io/github/actions/workflow/status/vnpy/vnpy/pythonapp.yml?branch=master"/>
    <img src ="https://img.shields.io/github/license/vnpy/vnpy.svg?color=orange"/>
</p>

## 📖 소개 (Introduction)

**VeighNa (vn.py)** 는 파이썬(Python) 기반의 오픈소스 퀀트 트레이딩 시스템 개발 프레임워크입니다.
"By Traders, For Traders(트레이더에 의한, 트레이더를 위한)"라는 모토 아래 개발된 이 프로젝트는 금융 기관(사모펀드, 증권사, 자산운용사)부터 개인 퀀트 투자자까지 폭넓게 사용되고 있습니다.

**왜 VeighNa인가요?**
*   **완전한 생태계:** 데이터 수집, 전략 개발, 백테스팅(과거 데이터 검증), 모의 투자, 그리고 실전 매매까지 하나의 플랫폼에서 해결할 수 있습니다.
*   **이벤트 기반 (Event-Driven):** 시장의 틱(Tick) 데이터 변경, 주문 체결 등 '이벤트'가 발생할 때마다 즉각 반응하도록 설계되어 고빈도 매매(HFT)부터 저빈도 스윙 전략까지 유연하게 대응합니다.
*   **강력한 확장성:** 전 세계 다양한 거래소와 연결할 수 있는 인터페이스(Gateway)와 다양한 전략 앱(App)을 블록 조립하듯 사용할 수 있습니다.

---

## 🚀 4.0 버전 업데이트: AI 트레이딩 (AI-Powered)

VeighNa 출시 10주년을 맞아 **AI(머신러닝) 퀀트 전략**을 위한 `vnpy.alpha` 모듈이 추가되었습니다. 이제 전통적인 기술적 분석뿐만 아니라 AI 모델을 활용한 트레이딩도 가능합니다.

*   **:bar_chart: Dataset:** 머신러닝 학습을 위한 대량의 데이터 처리 및 특징(Feature) 추출 엔진.
*   **:bulb: Model:** Lasso, LightGBM, MLP(딥러닝) 등 다양한 예측 모델 템플릿 제공.
*   **:robot: Strategy:** AI 신호를 기반으로 한 실전 퀀트 전략 개발 지원.
*   **:microscope: Lab:** 데이터 관리부터 모델 훈련, 백테스팅까지의 워크플로우를 통합 관리.

---

## 🌟 주요 기능 및 아키텍처 (Features & Architecture)

퀀트 초보자를 위해 VeighNa의 핵심 구조를 쉽게 설명합니다.

### 1. 트레이딩 인터페이스 (Gateway)
Gateway는 **여러분의 프로그램과 증권사/거래소를 연결해주는 다리** 역할을 합니다. VeighNa는 별도의 코드 수정 없이 설정만으로 다양한 시장에 접속할 수 있습니다.

*   **국내 선물/옵션:** CTP (중국), 융항(Rohon) 등
*   **해외 파생상품:** **Interactive Brokers (IB)** (전 세계 주식, 선물, 옵션, 외환 거래 가능), 직달(Direct Futures) 등
*   **암호화폐/기타:** 다양한 커뮤니티 플러그인을 통해 지원

### 2. 트레이딩 앱 (App)
전략을 실행하거나 특정 기능을 수행하는 모듈입니다. 초보자는 다음 앱들부터 시작하는 것이 좋습니다.

*   **CTA Strategy (추세 추종 전략):** 가장 대중적인 전략 모듈입니다. 이동평균선 교차, 볼린저 밴드 등 기술적 지표를 활용한 자동매매를 지원합니다.
*   **CTA Backtester (백테스터):** 코딩 없이 GUI(그래픽 환경)에서 과거 데이터로 내 전략이 수익이 났을지 검증해볼 수 있습니다.
*   **Data Manager:** 거래소에서 받은 데이터를 저장하고 관리합니다.
*   **Data Recorder:** 실시간 시세를 데이터베이스에 자동으로 녹화합니다.
*   **Portfolio Strategy:** 여러 종목을 동시에 거래하는 포트폴리오 전략을 지원합니다.
*   **Spread Trading:** 차익거래(Arbitrage)를 위한 스프레드 매매 모듈입니다.
*   **Option Master:** 옵션 가격 결정 모형 및 리스크 관리(Greeks) 기능을 제공합니다.

### 3. 이벤트 엔진 (Event Engine)
VeighNa의 심장입니다. 시세 수신, 주문 전송, 체결 확인 등 모든 동작을 '이벤트'로 처리하여 프로그램이 멈추지 않고 빠르고 안정적으로 동작하게 합니다.

---

## 💻 설치 가이드 (Installation)

### 시스템 요구사항
*   **OS:** Windows 11+, Ubuntu 22.04+, **macOS (Darwin)**
*   **Python:** 3.10 이상 (64비트). **3.13 버전 권장**

### 설치 단계
소스코드를 다운로드(Clone) 받은 후, 운영체제에 맞는 스크립트를 실행하면 필요한 라이브러리가 자동으로 설치됩니다.

1.  **소스코드 다운로드 (이미 완료된 경우 생략)**
    ```bash
    git clone https://github.com/vnpy/vnpy.git
    cd vnpy
    ```

2.  **설치 스크립트 실행**

    *   **macOS (현재 사용자)**
        ```bash
        bash install_osx.sh
        ```

    *   **Windows**
        ```cmd
        install.bat
        ```

    *   **Ubuntu**
        ```bash
        bash install.sh
        ```

> **Tip:** 설치 도중 `talib` 등 일부 라이브러리 설치에 실패할 경우, 해당 OS에 맞는 컴파일러(예: macOS의 경우 Xcode Command Line Tools)가 설치되어 있는지 확인하세요.

---

## 🏃‍♂️ 빠른 시작 (Quick Start)

VeighNa는 두 가지 방식으로 실행할 수 있습니다.

### 방법 1: 그래픽 인터페이스 (VeighNa Station) 사용
초보자에게 권장하는 방법입니다. 설치가 완료되면 바탕화면의 바로가기나 터미널 명령어로 `VeighNa Station`을 실행하여 로그인 후 **'VeighNa Trader'** 버튼을 클릭하면 됩니다.

### 방법 2: 파이썬 스크립트로 직접 실행 (`run.py`)
자신만의 설정을 구성하고 싶다면 스크립트를 직접 작성하여 실행합니다.

1.  프로젝트 루트(또는 작업 폴더)에 `run.py` 파일을 생성하고 아래 코드를 붙여넣으세요.

```python
# run.py 예제 코드
from vnpy.event import EventEngine
from vnpy.trader.engine import MainEngine
from vnpy.trader.ui import MainWindow, create_qapp

# 사용할 게이트웨이와 앱을 임포트합니다.
# (사용하지 않는 게이트웨이는 주석 처리하세요)
from vnpy_ctp import CtpGateway            # 예: CTP 게이트웨이
from vnpy_ctastrategy import CtaStrategyApp # CTA 전략 앱
from vnpy_ctabacktester import CtaBacktesterApp # CTA 백테스터 앱

def main():
    """VeighNa Trader 실행 함수"""
    qapp = create_qapp()

    event_engine = EventEngine()
    main_engine = MainEngine(event_engine)
    
    # 1. 게이트웨이 추가 (증권사 연결)
    # Interactive Brokers 등을 사용하려면 해당 패키지(vnpy_ib)를 설치 후 import해야 합니다.
    main_engine.add_gateway(CtpGateway) 
    
    # 2. 앱 추가 (기능 추가)
    main_engine.add_app(CtaStrategyApp)
    main_engine.add_app(CtaBacktesterApp)

    # 3. 메인 윈도우 실행
    main_window = MainWindow(main_engine, event_engine)
    main_window.showMaximized()

    qapp.exec()

if __name__ == "__main__":
    main()
```

2.  터미널에서 실행합니다.
    ```bash
    python run.py
    ```

---

## 📂 폴더 구조 설명 (Directory Structure)

*   `vnpy/`: VeighNa의 핵심 코드가 들어있는 폴더입니다.
    *   `trader/`: 트레이딩 엔진, 데이터 모델 등 기초 프레임워크.
    *   `event/`: 이벤트 처리 엔진.
    *   `chart/`: 차트 그리기 모듈.
*   `examples/`: **(중요)** 초보자를 위한 다양한 예제가 있습니다.
    *   `veighna_trader/`: 표준 실행 스크립트 예제.
    *   `cta_backtesting/`: 주피터 노트북(.ipynb)을 이용한 백테스팅 예제.
    *   `alpha_research/`: AI/머신러닝 연구용 예제.
*   `docs/`: 프로젝트 문서.

---

## 🤝 커뮤니티 및 기여 (Community & Contribution)

*   **공식 문서 (Docs):** [https://www.vnpy.com/docs/cn/index.html](https://www.vnpy.com/docs/cn/index.html)
*   **Github 이슈:** 버그 리포트나 기능 제안은 [Issues](https://github.com/vnpy/vnpy/issues) 탭을 이용해주세요.
*   **포럼:** [VeighNa 공식 포럼](https://www.vnpy.com/forum/)

---

## ⚠️ 라이선스 (License)

MIT License를 따릅니다. 누구나 무료로 사용하고 수정할 수 있습니다.

---
*Updated for Quant Beginners by Gemini*