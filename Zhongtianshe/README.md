Description of modeling data and model performance of the Zhongtianshe Watershed.

Details of modeling procedures could be found in the corresponding markdown file, such as Zhongtianshe_SWATplus_59.3.md.

## 1. Data

|                                   | Zhongtianshe Watershed                                       |
| --------------------------------- | ------------------------------------------------------------ |
| DEM                               | DEM with a resolution of 25 m from Provincial Geomatics Centre of Jiangsu |
| Land use                          | Manually interpreted from a Google Earth image derived in 2015 |
| Soil                              | Soil type map obtained from Soil Science Database of China and soil properties from field sampling |
| Meteorological data               | Daily meteorological data (such as precipitation, temperature, humidity, wind speed, and solar radiation) from 2011 to 2015 provided by China Meteorological Data Service Centre and Liyang Meteorological Station |
| Agricultural management practices | Cropping and irrigation schedule including crop types and fertilizer usage from field survey |
| Observed data at the outlet       | Daily measured flow (2011–2015) and 5-day* measured total nitrogen data (2014–2015) from the site-monitoring station at the watershed outlet<br />\* During the rainy season (i.e., June to August) in the Zhongtianshe watershed, the total nitrogen is measured about every three days. |

Note: There is some data which is not public. If you are interested, please email us (zlj@lreis.ac.cn).

## 2. Model performance using SWAT+ (v59.3)

For the daily simulation of flow, the calibration period is from 2012 to 2013, and the validation period is from 2014 to 2015. limited by the available observed data of the total nitrogen, it is without validation for the total nitrogen.

### 2.1 Flow simulation

![zts_flow](https://github.com/Git160/Picture/raw/main/Zhongtianshe/zts_flow.jpg)

### 2.2 Nitrogen simulation

![zts_n](https://github.com/Git160/Picture/raw/main/Zhongtianshe/zts_n.jpg)