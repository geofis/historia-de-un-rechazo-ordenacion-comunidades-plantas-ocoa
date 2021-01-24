Historia de un rechazo: Ordenación de comunidades plantas de Ocoa,
revisitado. Tabla de equivalencias entre códigos alfanuméricos y
numéricos
================

# Packages

``` r
library(tidyverse)
## ── Attaching packages ───────────────────────────────────────────── tidyverse 1.2.1 ──
## ✓ ggplot2 3.3.2     ✓ purrr   0.3.4
## ✓ tibble  3.0.3     ✓ dplyr   0.8.3
## ✓ tidyr   1.0.0     ✓ stringr 1.4.0
## ✓ readr   1.3.1     ✓ forcats 0.4.0
## ── Conflicts ──────────────────────────────────────────────── tidyverse_conflicts() ──
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

# Data

``` r
cm <- read.csv('data/d.mc.csv', row.names = 1, check.names = F)
colnames(cm) <- word(colnames(cm), 1, 2)
env <- read.csv('data/d.env.csv', row.names = 1, check.names = F)
```

# Equivalences

``` r
(equivalences_alphanum_num <- cm %>%
  rownames_to_column('codigo') %>%
  mutate(codigo_num = as.numeric(factor(codigo))) %>%
  select(codigo, codigo_num))
##     codigo codigo_num
## 1  CROB_01          1
## 2  CROB_02          2
## 3  ECMD_01          3
## 4  ECMD_02          4
## 5  ECMI_01          5
## 6  ELCA_02          6
## 7  ELVE_01          7
## 8  EPCA_01          8
## 9  EPCA_02          9
## 10 EPVE_01         10
## 11 LCCA_01         11
## 12 LCCA_02         12
## 13 LCCA_03         13
## 14  LCHv_1         14
## 15   LIv_1         15
## 16  LLCv_1         16
## 17  LLCv_2         17
## 18 LLTR_01         18
## 19 LMVE_01         19
## 20 LMVE_02         20
## 21 PVRO_01         21
## 22 PVRO_03         22
## 23 PVRO_04         23
equivalences_alphanum_num %>% write_csv('tabla-de-equivalencias.csv')
```
