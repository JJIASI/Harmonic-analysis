# 調和分析應用於潮汐分析
# Harmonic-analysis for tide analysis   
作者:張家羲

--------------------------------------------   
# 調和分析
調和分析是一種頻譜分析方法，是傅立葉分析的擴展，簡單來說就是週期函數的疊加，廣泛應用於各種領域中，如信號分析、量子力學、潮汐分析等。  
想了解調和分析相關內容請參閱  

[Harmonic analysis](https://en.wikipedia.org/wiki/Harmonic_analysis "Wikipedia")。  
---------------------------------------------   
# 潮汐調和分析
潮汐是由地球、月球的自轉與公轉受到太陽與月球的引力等影響，產生周期性的變化。
潮汐包含了無限多的分潮，依其組成分潮成分之差異，主要分為太陽潮 (solar tide)、太陰潮 (lunar tide)、日月潮 (lunisolar tide)、倍潮 (overtide)、混合潮 (compound tide) 等。若依週期來分，主要分為全日潮 (diurnal tides)、半日潮 (semi-diurnal tides)等。  
而因為潮汐具有週期性，因此可表示成傅立葉級數(Fourier series)，如下式  
![](https://wikimedia.org/api/rest_v1/media/math/render/svg/1ceecb10ad563feabef4732e6f94c6a3f1d3c099)  
η(t)為潮位函數  
wn為角頻率  
t為時間  
蒐集某地區潮位資料後，將所有選定之分潮角頻率代入公式，求解出振幅，即可預測未來潮汐資料。  
  
_半日潮(以S2,Principal solar semidiurnal 分潮為例)_  
![半日潮](https://github.com/JJIASI/Harmonic-analysis/blob/master/figure/S2.png)  
  
  
_全日潮(以K1,Lunar diurnal 分潮為例)_  
![全日潮](https://github.com/JJIASI/Harmonic-analysis/blob/master/figure/K1.png)
    
_長潮(以Sa,Solar annual 分潮為例)_
![長潮](https://github.com/JJIASI/Harmonic-analysis/blob/master/figure/Sa.png)
  
將所有選定之分潮疊加後，即為該地區的預測潮汐資料。
![tide analysis](https://github.com/JJIASI/Harmonic-analysis/blob/master/figure/tide%20analysis.png?raw=true)   
_本程式選用台灣常用60分潮，但若資料長度不足，建議將長週期的分潮剔除。_  
   
內容參考   
[Theory of tides](https://en.wikipedia.org/wiki/Theory_of_tides#Harmonic_analysis "Wikipedia")  
[潮汐調和分析](https://zh.wikipedia.org/wiki/%E6%BD%AE%E6%B1%90%E8%AA%BF%E5%92%8C%E5%88%86%E6%9E%90 "Wikipedia")  
  
------------------------------------
#主程式 ha 功能介紹  
執行程式前，需先安裝`numpy` , `pandas` , `lunardate`  
    
`HA` 調和分析，求得調和參數, 振幅, 相位角。
`HA_pred` 預測潮汐。
`tide_sta` 統計潮汐資料，求得高低潮位及朔望高低潮位，供港灣設計時使用。

```
para, amp, pha_ang = HA(obs_Date , water_level , speed_rate)  
para:調和參數  
amp:振幅  
ph_ang:相位角
obs_Date:觀測時間
water_level:觀測水位高
speed_rate:選定之分潮角頻率，默認為60分潮
  
所輸入的時間序列格式需為 'yyyymmddhh'
```


