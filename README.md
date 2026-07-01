# Spiking Neural Network Tutorials

snnTorch로 배우는 스파이킹 신경망(SNN) 튜토리얼 시리즈.
뉴런 모델과 입력 인코딩에서 시작해, 국소 학습 규칙(STDP, 3-factor R-STDP, e-prop)과 예측 부호화까지 노트북 01–05로 이어집니다.

## 노트북 구성

| # | 파일 | 내용 |
|---|---|---|
| 01 | `01_snn_neuron_and_encoding.ipynb` | SNN 뉴런 모델과 입력 인코딩 |
| 02 | `02_stdp_unsupervised.ipynb` | STDP 기반 비지도 학습 |
| 03 | `03_three_factor_rstdp.ipynb` | 3-factor 보상 변조 STDP (R-STDP) |
| 04 | `04_eprop.ipynb` | e-prop (eligibility propagation) |
| 05 | `05_predictive_coding.ipynb` | 예측 부호화 (predictive coding) |

## 실행 환경

- **Python** 3.11
- **PyTorch** 2.12 — Apple Silicon에서는 MPS 백엔드 사용
- **snnTorch** 1.0
- 그 외: matplotlib, numpy, JupyterLab, ipykernel

## 실행 방법

프로젝트 루트에서 아래 순서대로 실행합니다.

```bash
# 1. 가상환경 생성 & 활성화
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip

# 2. 패키지 설치
pip install torch snntorch matplotlib numpy jupyterlab ipykernel

# 3. Jupyter 커널 등록
python -m ipykernel install --user --name snn-tutorial --display-name "Python (snn-tutorial)"

# 4. JupyterLab 실행
jupyter lab
```

설치 확인:

```bash
python -c "import torch, snntorch; print('torch', torch.__version__, '| snntorch', snntorch.__version__, '| MPS', torch.backends.mps.is_available())"
# 예시 출력: torch 2.12.1 | snntorch 1.0.0 | MPS True
```

JupyterLab이 열리면 노트북을 01 → 05 순서로 열고, 커널을 **Python (snn-tutorial)** 로 선택하세요.
