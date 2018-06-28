# Проверка эффективности КМП/наивного алгоритма

 - Варианты длин текста `text` для тестов - *2048, 8192, 32768, 131072, 524288, 2097152*. 

 - Варианты длин подстроки `pattern` для тестов - от *2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048*.

Для каждой пары (`pattern`,`text`) было проведено по 10 тестов со случайными строками заданной длины. Результат в таблице - среднее значение. 

`P \ T` - Длина строки `pattern` \ Длина строки `text`  


## Таблица 1 - Количество сравнений 

Первое число в ячейке - количество сравнений для наивного поиска, второе число - для КМП:  

| P \ T|              2048  |              8192  |             32768  |            131072  |            524288  |           2097152  |
|-----:|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|
|    2 |    2125;     2127  |    8502;     8504  |   34021;    34023  |  136121;   136123  |  544462;   544464  | 2177807;  2177809  |
|    4 |    2132;     2135  |    8519;     8513  |   34069;    34024  |  136302;   136105  |  545142;   544351  | 2180955;  2177736  |
|    8 |    2125;     2137  |    8515;     8516  |   34060;    34026  |  136282;   136099  |  545205;   544430  | 2181087;  2177845  |
|   16 |    2114;     2141  |    8512;     8530  |   34050;    34032  |  136287;   136113  |  545265;   544480  | 2180974;  2177803  |
|   32 |    2098;     2159  |    8493;     8544  |   34059;    34072  |  136266;   136136  |  545204;   544466  | 2180870;  2177734  |
|   64 |    2063;     2191  |    8456;     8574  |   33998;    34078  |  136238;   136173  |  545177;   544487  | 2180978;  2177882  |
|  128 |    2002;     2261  |    8378;     8630  |   33931;    34148  |  136172;   136235  |  545064;   544528  | 2181005;  2177977  |
|  256 |    1859;     2385  |    8253;     8770  |   33812;    34293  |  136086;   136409  |  544929;   544650  | 2180732;  2178023  |
|  512 |    1601;     2659  |    7983;     9038  |   33533;    34545  |  135794;   136653  |  544733;   544987  | 2180426;  2178272  |
| 1024 |    1066;     3189  |    7461;     9576  |   33009;    35080  |  135238;   137160  |  544229;   545540  | 2179984;  2178886  |
| 2048 |       1;     4252  |    6389;    10636  |   31958;    36158  |  134218;   138269  |  543090;   546542  | 2178821;  2179842  |

## Таблица 2 - Эффективный алгоритм

В ячейке отображается название алгоритма, справившегося за наименьшее число сравнений для данного теста, и разница в количестве сравнений: 

| P \ T|              2048  |              8192  |             32768  |            131072  |            524288  |           2097152  |
|-----:|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|
|    2 | Naive -         2  | Naive -         2  | Naive -         2  | Naive -         2  | Naive -         2  | Naive -         2  | 
|    4 | Naive -         3  |  KMP  -         6  |  KMP  -        45  |  KMP  -       197  |  KMP  -       791  |  KMP  -      3219  | 
|    8 | Naive -        12  | Naive -         1  |  KMP  -        34  |  KMP  -       183  |  KMP  -       775  |  KMP  -      3242  | 
|   16 | Naive -        27  | Naive -        18  |  KMP  -        18  |  KMP  -       174  |  KMP  -       785  |  KMP  -      3171  | 
|   32 | Naive -        61  | Naive -        51  | Naive -        13  |  KMP  -       130  |  KMP  -       738  |  KMP  -      3136  | 
|   64 | Naive -       128  | Naive -       118  | Naive -        80  |  KMP  -        65  |  KMP  -       690  |  KMP  -      3096  | 
|  128 | Naive -       259  | Naive -       252  | Naive -       217  | Naive -        63  |  KMP  -       536  |  KMP  -      3028  | 
|  256 | Naive -       526  | Naive -       517  | Naive -       481  | Naive -       323  |  KMP  -       279  |  KMP  -      2709  | 
|  512 | Naive -      1058  | Naive -      1055  | Naive -      1012  | Naive -       859  | Naive -       254  |  KMP  -      2154  | 
| 1024 | Naive -      2123  | Naive -      2115  | Naive -      2071  | Naive -      1922  | Naive -      1311  |  KMP  -      1098  | 