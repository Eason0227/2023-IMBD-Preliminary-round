# 2023-IMBD-Preliminary-round
2023 Intelligent Manufacturing Big Data Analysis Competition - Preliminary round

## 數據資料
過去某段時間各爐層的燈管異常數據、各爐層累積使用時數、燈管功率輸出設定、爐層水冷板設定（水温、水量…）
## 預測目標
分別建模預測兩條産線在一段時間内毎個爐的燈管異常數量
## 使用方法

### 產線一
* 進行特徴工程，增加許多新特徴。
* 使用機器學習模型進行建模，模型包含Lasso regression、XGBoost、LightGBM、Catboost  
<table>
  <tr>
    <td>特徵名稱</td>
    <td>描述</td>
  </tr>

  <tr>
    <td> number_sum </td>
    <td> 前27天異常燈管總數 </td>
  </tr>
    <td> number_max </td>
    <td> 前27天異常燈管最大值 </td>
  </tr>
  <tr>
    <td> number_min </td>
    <td> 前27天異常燈管最小值 </td>
  </tr>
  <tr>
    <td> number_mode </td>
    <td> 前27天異常燈管眾數 </td>
  </tr>
  <tr>
    <td> days </td>
    <td> 前27天異常燈管出現天數 </td>
  </tr>
  <tr>
    <td> oven_encoder </td>
    <td> 前27天的平均損壞數量 </td>
  </tr>
  <tr>
    <td> cooler_max </td>
    <td> 該爐層的最大水冷板溫度 </td>
  </tr>
  <tr>
    <td> avg_accumulation </td>
    <td> 該爐層的平均使用時數 </td>
  </tr>
  <tr>
    <td> max_accumulation </td>
    <td> 該爐層的最大累積使用時數 </td>
  </tr>
  <tr>
    <td> min_accumulation </td>
    <td> 該爐層的最小累積使用時數 </td>
  </tr>
  <tr>
    <td> avg_power_setup </td>
    <td> 該爐層的平均功率輸出設定 </td>
  </tr>
</table>

### 產線二
* 使用ETS分解時間序列資料
* 使用ACF、PACF判斷時間序列的週期
* 使用ADF檢定(Dickey Fuller test)檢驗時間序列是否平穩
* 使用ARIMA、SARIMA進行建模
* 使用其他時間序列模型進行建模，如Holt、Holt’s winter、Moving average
