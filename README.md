# StockTrading

```
StockTrading/
├─ pyproject.toml              # 의존성/빌드(선택) or requirements.txt
├─ README.md
├─ scripts/
│  ├─ build_features.py        # 원천 DF→지표 생성/스플릿 저장
│  ├─ train.py                 # 학습 엔트리
│  ├─ evaluate.py              # 백테스트/지표 계산
│  └─ infer.py                 # 최근 구간 추론(포지션/비중 산출)
├─ src/rltrader/
│  ├─ configs/
│  │  ├─ base.yaml
│  │  ├─ data/kis_panel.yaml
│  │  ├─ envs/multistock.yaml
│  │  ├─ models/ppo.yaml
│  │  └─ models/sac.yaml
│  ├─ dataio/
│  │  ├─ datasets.py           # Panel 데이터 로드/스플릿
│  │  └─ loader.py             # 배치/윈도우 생성
│  ├─ features/
│  │  ├─ indicators.py         # 기술지표/VIX/turbulence 계산 훅
│  │  └─ pipeline.py           # 피처 파이프라인(선택적 스케일링)
│  ├─ envs/
│  │  ├─ env_multi_stock.py    # Gym Env(아래에 스켈레톤 제공)
│  │  └─ wrappers.py           # NormalizeObs/Reward 등
│  ├─ agents/
│  │  ├─ sb3_train.py          # Stable-Baselines3 학습/저장
│  │  └─ policies.py           # Custom MLP, CNN1D(옵션)
│  ├─ eval/
│  │  ├─ backtest.py           # 수익곡선/드로다운/샤프 등
│  │  └─ metrics.py
│  ├─ inference/
│  │  └─ predictor.py          # 모델 로드→비중 산출
│  └─ utils/
│     ├─ conf.py               # YAML 로드/머지/CLI override
│     ├─ logger.py             # TB/W&B
│     ├─ seeding.py
│     └─ mathops.py            # 안정적 softmax/비중클리핑
└─ data/                       # (로컬) parquet/hdf5 캐시
   ├─ raw/
   └─ proc/
```
