# 🌦️ Power BI Weather & Air Quality Dashboard  
** Tools: Power BI, DAX, API/CSV Data**

---

## 项目介绍 | Project Overview
这是一个使用 **Power BI** 构建的交互式天气与空气质量仪表盘。  
This is an **interactive dashboard** built with **Power BI** to visualize **weather forecasts** and **air quality indicators**.

---

## 功能亮点 | Key Features
- **多城市选择 (City Selection)**: 切换 Beijing, Hangzhou, London 等城市  
- **天气预测 (Weather Forecast)**: 显示 7 天平均温度曲线  
- **日出日落 (Sunrise & Sunset)**: 自动展示不同城市的时间  
- **空气质量指数 (Air Quality Index)**: PM2.5, SO2, NO2, CO 实时数值 & AQI 分级颜色显示  
- **降水概率 (Chance of Rain)**: 直观柱状图展示不同日期的降雨概率  

---

## 技术细节 | Technical Details
- 使用 **DAX 公式** 动态计算 AQI 分级颜色：  
```DAX
AQI Color TEMPLATE =
VAR AQI = ROUND(SELECTEDVALUE('Current'[PM2.5]),0)
RETURN
SWITCH(
    TRUE(),
    AQI <= 50, "#43d946",   -- Green
    AQI <= 100, "#fff570",  -- Yellow
    AQI <= 150, "#ff9800",  -- Orange
    AQI <= 200, "#d99343",  -- Brown
    AQI <= 300, "#ff5b0f",  -- Red-Orange
    "#d95243"               -- Dark Red
)
