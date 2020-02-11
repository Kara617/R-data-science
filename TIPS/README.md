### A tip a day  

### 字符串String  
* 首字母大写  
```r
library(stringr)

str_to_title("abc")
# Abc
```

### ggplot2画图  
* 去掉ggplot2网格线  
```r
p + theme_bw() +
    theme(
      panel.grid = element_blank()
    )
```
