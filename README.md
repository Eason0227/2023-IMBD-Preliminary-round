# 2023-IMBD-Preliminary-round
2023 Intelligent Manufacturing Big Data Analysis Competition - Preliminary round

## 數據資料
過去某段時間各爐層的燈管異常數據、各爐層累積使用時數、燈管功率輸出設定、爐層水冷板設定（水温、水量…）
## 預測目標
分別建模預測兩條産線在一段時間内毎個爐的燈管異常數量
## 使用方法

### 產線一
* 進行特徴工程，增加許多新特徴，如前幾天異常燈管數的最大値等特徴，
* 使用機器學習模型(Lasso、LGBM等)進行建模

### 產線二
* 使用ETS分解時間序列資料
* 使用ACF、PACF判斷時間序列的週期
* 使用ADF檢定(Dickey Fuller test)檢驗時間序列是否平穩
* 使用ARIMA、SARIMA進行建模
* 使用其他時間序列模型進行建模，如Holt、Holt’s winter、Moving average
