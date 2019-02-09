# 調和分析應用於潮汐分析
## Harmonic-analysis for tide analysis   
--------------------------------------------   
### 調和分析
調和分析是一種頻譜分析方法，是傅立葉分析的擴展，簡單來說就是週期函數的疊加，廣泛應用於各種領域中，如信號分析、量子力學、潮汐分析等。  
想了解調和分析相關內容請參閱  
[Harmonic analysis](https://en.wikipedia.org/wiki/Harmonic_analysis "Wikipedia")。  
---------------------------------------------   
### 潮汐調和分析
潮汐是由地球、月球的自轉與公轉受到太陽與月球的引力等影響，產生周期性的變化。
潮汐依其組成分潮成分之差異，主要分為太陽潮 (solar tide)、太陰潮 (lunar tide)、日月潮 (lunisolar tide)、倍潮 (overtide)、混合潮 (compound tide) 等。若依週期來分，主要分為全日潮 (diurnal tides)、半日潮 (semi-diurnal tides)等。  
本程式選用台灣常用60分潮，但若資料長度不足，建議將長週期的分潮剔除。  
(/figure/tide analysis.png)
