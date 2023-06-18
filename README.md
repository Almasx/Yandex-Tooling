# Yandex-Tooling Project Analysis

This document presents the analysis of the page [https://www.gd.ru/articles/9039-finansovyy-kontrol](https://www.gd.ru/articles/9039-finansovyy-kontrol) using Chrome DevTools. The analysis covers the Performance, Network, and Coverage tabs of the DevTools.

## Table of Contents

- [1. Network Tab Analysis](#1-network-tab-analysis)
  - [1.1 HAR Archive](#11-har-archive)
  - [1.2 Non-optimal Places](#12-non-optimal-places)
- [2. Performance Tab Analysis](#2-performance-tab-analysis)
  - [2.1 Page Loading Profile](#21-page-loading-profile)
  - [2.2 Performance Metrics](#22-performance-metrics)
  - [2.3 LCP DOM Element](#23-lcp-dom-element)
  - [2.4 Document Processing Stages](#24-document-processing-stages)
- [3. Coverage Tab Analysis](#3-coverage-tab-analysis)
  - [3.1 Screenshot After Page Load](#31-screenshot-after-page-load)
  - [3.2 Unused CSS](#32-unused-css)
  - [3.3 Unused JS](#33-unused-js)

# Yandex-Tooling: Performance Analysis Tasks

## 1. Network Tab Analysis

### 1.1 HAR Archive
The resource loading profile when opening the page was written and saved to a HAR archive.


### 1.2 Non-Optimal Places

#### 1.2.1 Resource Duplication
Several resources were found to be duplicated:

- `cast_sender.js`
- `code.js`
- `openapi.js`
- `www.lcont.ru`
- `fontawesome-webfont.woff2`

*Screenshot 1*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/6a775ea9-3966-42ae-bffe-8db825f186d1)

*Screenshot 2*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/3705762a-46a6-4c9c-872a-f1f712bc1a81)

*Screenshot 3*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/9a706d3a-28ca-4b6c-81cf-e2056a7bb990)

*Screenshot 4*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/546973e9-f2b4-4161-b522-5013cc13219e)

*Screenshot 5*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/cdecd3a8-8392-453d-a7f7-82ddda2b147c)

#### 1.2.2 Extra Resource Size
One image (`Just black Bg imageTop_1628667062.7856.j`) was identified as having an extra resource size.

*Screenshot 6*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/cce85f53-3771-41f9-b4d4-3a65256799ea)

#### 1.2.3 Slow Loading Resources
There are resources that took more than 1.0s to load.

*Screenshot 7*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/7d41b6b8-f6db-46e5-a73d-80a711ce2f5f)

#### 1.2.4 Download Blocking Resources
Several resources were found to be blocking the download:

- `actmarketingpixel.js`
- `openapi.js?116`
- `theme_gd_ru.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `HTMLHelper.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`   
- `btx.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `jquery.easie.min.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `AuthButtonWidget.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `strategies.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `jquery.validate.min.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `SearchFormWidget.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `DeliveryWidget.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`
- `utmEventManager.js?cache=5a6fa72bdfc8007242bf089feb2ff92203bc8762`

#### 1.2.5 Something Else
Unfortunately, the task did not provide specific information for this section. However, based on the network analysis, potential issues could include unoptimized images, unused JavaScript, and so forth.

### 1.3 Screenshots of Non-Optimal Places
Screenshots of the non-optimal places found were taken and included in the corresponding sections of the report.

## 2. Performance Tab Analysis

### 2.1 Page Loading Profile

The page loading profile was written and saved to a file.

### 2.2 Performance Metrics

| Event                | Time (ms)  |
|----------------------|------------|
| First Paint          | 1707.5     |
| First Contentful Paint | 1707.5     |
| DOMContentLoaded Event | 2955.6     |
| Largest Contentful Paint | 3090.6     |
| Onload Event         | 6050.5     |

### 2.3 LCP DOM Element

The DOM element on which the LCP occurs is an image tag with the class "contentImage__image".
```html
<img loading="lazy" itemprop="image" src="/images/finansovyy-kontrol.jpg" width="600" height="408" data-url="/images/finansovyy-kontrol.jpg" alt= "" title="" class="contentImage__image">
```

*Screenshot*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/0104cd1c-bcdb-4889-9c74-c1277a2ccc6e)

### 2.4 Document Processing Stages

The time spent in different stages of document processing was measured. Here is a detailed breakdown:

![Processing Stages](https://github.com/Almasx/Yandex-Tooling/assets/58309601/dc0ecee6-2ba8-4e8a-8f10-456f53edc7b7)

## 3. Coverage Tab Analysis

### 3.1 Screenshot After Page Load

*Screenshot*  
![](https://github.com/Almasx/Yandex-Tooling/assets/58309601/4e749a03-7ac8-445f-b779-e0e9da28feaa)

### 3.2 Unused CSS

During page load, 539 kB of CSS was unused out of a total of 762 kB.

### 3.3 Unused JS

During page load, 2.3 MB of JS was unused out of a total of 3.8 MB.

| Resource Type | Used | Unused | Total |
|---------------|------|--------|-------|
| CSS           | 223 kB | 539 kB | 762 kB |
| JS            | 1.5 MB | 2.3 MB | 3.8 MB |
