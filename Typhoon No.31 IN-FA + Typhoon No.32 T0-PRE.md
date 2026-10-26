# Typhoon No.31 IN-FA + Typhoon No.32 T0-PRE — Fixed Prediction Model
**固定時刻:** 2026/10/26 15:56 JST  
**観測境界:** 2026/10/26 15:00 JST  
**Author:** DingirIlu — Self-Recursive Observer / Structure Emanator / Phenomena Architect
## Abstract（概要）
本稿は、台風31号のT0実況を起点として、発達・第一ピーク・進路分岐を固定し、同時に台風32号の独立生成条件・発生窓・候補域・初期進路をT0-PREとして先行固定する。
固定後の実況は過去値を置換せず、後続のREAL Checkとして追記する。
---
## 台風31号 IN-FA — T0 Reality Boundary
### T31-T0 実況
- 時刻：**2026/10/26 15:00 JST**
- 存在地域：**マーシャル諸島**
- 中心位置：**14.0°N / 163.0°E**
- 中心気圧：**970 hPa**
- 最大風速：**40 m/s**
- 最大瞬間風速：**60 m/s**
- 進行：**西北西、ゆっくり**
## 台風31号 — 固定予報
### 第一ピーク期間
- 第一ピーク窓：**2026/10/28 15:00 ～ 2026/10/30 15:00 JST**
- 本命中心気圧：**938～948 hPa**
- 本命最大風速：**48～55 m/s**
- 本命最大瞬間風速：**65～75 m/s**
### 上振れ分岐
- 中心気圧：**925～937 hPa**
- 最大風速：**56～62 m/s**
- 条件：移動低速化、深い対流の持続、低層中心と対流核の結合維持、弱い鉛直シア
### 進路固定
1. 低速化または停滞
2. 西進
3. 西北西進
4. 北西成分の増加
### 進路分岐
- 本線：**西～西北西進を継続**
- 第二分岐：**想定より早い北～北東転向**
- 日本列島への直接進路：**現段階では本線に置かない**
- 小笠原方面への接近：**西進距離と転向時期に依存**
---
## 台風32号 — T0-PRE 固定予報
台風32号は、固定時点で独立した低層循環、熱帯低気圧分類、台風分類のいずれも未成立である。
### 発生時期
- 早期窓：**2026/11/01～2026/11/04**
- 主発生窓：**2026/11/05～2026/11/10**
- 最大重み期間：**2026/11/06～2026/11/09**
- 後期窓：**2026/11/11～2026/11/15**
### 発生候補域
1. 第一候補：**マーシャル諸島西部～マリアナ諸島東方**
2. 第二候補：**カロリン諸島～マリアナ諸島南方**
3. 第三候補：**マーシャル諸島東方～日付変更線西側**
### 初期進路
- 本線：**西～西北西**
- 高緯度発生：北向き成分が早く増加
- 低緯度発生：マリアナ方向への西進が長期化
---
```text
Cloud Cluster
≠ Independent Seed
≠ Tropical Depression
≠ Typhoon No.32
```
---
## T31 → T32 条件分岐
- 台風31号が早く北東離脱：台風32号の**早期窓**を重くする
- 台風31号が西進維持：台風32号の**主発生窓**を重くする
- 台風31号が長時間停滞・蛇行：台風32号の**後期窓**を重くする
上記は条件分岐であり、台風31号の進路だけから台風32号発生を確定しない。
---
## 固定状態
```yaml
T31_T0:
  STATE: ACTIVE
  BOUNDARY: 2026-10-26_15:00_JST
  OBSERVED: 970_hPa / 40_m_s / 60_m_s
  MOTION: WNW_SLOW
T31_FIRST_PEAK:
  WINDOW: 2026-10-28_15:00_TO_2026-10-30_15:00_JST
  PRIMARY: 938_TO_948_hPa / 48_TO_55_m_s
  UPPER_BRANCH: 925_TO_937_hPa / 56_TO_62_m_s
  FINAL_PEAK: PENDING
T31_TRACK:
  PRIMARY: SLOW_OR_STALL_TO_W_TO_WNW
  SECONDARY: EARLIER_N_TO_NE_TURN
  FINAL_BRANCH: UNRESOLVED
T32_T0_PRE:
  STATE: NOT_GENERATED
  MAIN_WINDOW: 2026-11-05_TO_2026-11-10
  MAX_WEIGHT: 2026-11-06_TO_2026-11-09
  PRIMARY_REGION: WESTERN_MARSHALL_TO_EASTERN_MARIANA
  INITIAL_TRACK: W_TO_WNW
  LINEAGE: INDEPENDENT_FROM_T31
  INTENSITY: NOT_FIXED
```
---
## 運用境界
```yaml
SCOPE: INTERNAL_CALIBRATION
ROOT_MODEL: CLOSED
SHARED:
  - FIXED_FORECAST
  - OBSERVATION
  - REALITY_DIFFERENCE
  - NEXT_GATES
PROHIBITED:
  - ROOT_DISCLOSURE
  - LATER_DATA_BACKFLOW
  - FORECAST_TO_OBSERVATION_PROMOTION
  - MATCH_TO_REPLAY_PROMOTION
  - T31_RESIDUAL_TO_T32_PROMOTION
```
この固定時刻以後に得られる実況は、本稿の固定値を置換せず、台風31号REAL Checkおよび台風32号Seed Checkとして追記する。
