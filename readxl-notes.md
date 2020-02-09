## Notes for readxl
[readxl package](https://readxl.tidyverse.org/index.html)  
The readxl package makes it easy to get data out of **Excel** and **into R**.  
designed to work with _tabular_ data  

**Formats supported**:  
`.xls` & `xlsx`  

**读取**: `read_excel()` reads both xls and xlsx files  
```r
xlsx_example <- readxl_example("datasets.xlsx")
```
**获取sheets名称**: `excel_sheets()` list the sheets names  

### `read_excel()`重要参数
* **sheet** 指定读取的sheet; Specify a worksheet **by name or number**.  
```r
read_excel(xlsx_example, sheet = 4)  
read_excel(xlsx_example, sheet = "chickwts")  
```
* **n_max** 读取行数  
```r
read_excel(xlsx_example, n_max = 3)
```
* **range** 读取单元格 
```r
read_excel(xlsx_example, range = "C1:E4")
read_excel(xlsx_example, range = cell_rows(1:4)) # 读取1-4行
read_excel(xlsx_example, range = cell_cols("B:D")) # 读取B到D列
read_excel(xlsx_example, range = "mtcars!B1:D5")  # specify sheet
```  

### 关于缺失值  
* 如果excel文件中空值为空白，则无需处理；  
* 如果空值为特定数字或字符标记，则在读取时设置`na`参数  
```r
read_excel(xlsx_example, na = "setosa")
```
Some other similar existing package:  
* gdata  
* xlsx  
* xlsReadWrite  
