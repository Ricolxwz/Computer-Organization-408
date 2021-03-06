## 进位计数制

### r进制计数法

- r进制: $K_nK_{n-1}...K_2K_1K_0K_{-1}K_{-2}...K_{-m}=K_n\times r^n+K_{n-1}\times r^{n-1}+...+K_2\times r^2+K_1\times r^1+K_0\times r^0+K_{-1}\times r^{-1}+K_{-2}\times r^{-2}+...+K_{-m}\times r^{-m}$
- 基数: 每个数码位所用到的不同符号的个数, r进制的基数为r 

### 任意进制转十进制

- $K_nK_{n-1}...K_2K_1K_0K_{-1}K_{-2}...K_{-m}=K_n\times r^n+K_{n-1}\times r^{n-1}+...+K_2\times r^2+K_1\times r^1+K_0\times r^0+K_{-1}\times r^{-1}+K_{-2}\times r^{-2}+...+K_{-m}\times r^{-m}$

### 二进制转八进制和十六进制

- 二进制转八进制: 3位为一组, 每组转换成对应的八进制符号
- 二进制转十六进制: 4位为一组, 每组转换成对应的十六进制符号

### 八进制和十六进制转二进制

- 八进制转二进制: 每位八进制对应3位二进制
- 十六进制转二进制: 每位十六进制对应4位二进制

### 常用进制的书写方式

- 二进制: $(1010101000001010)_2\quad 1010101000001010B$
- 八进制: $(1652)_8$
- 十六进制: $(1652)_{16}\quad 1652H\quad Ox1652$
- 十进制: $(1652)_{10}\quad 1652D$

### 十进制转化为任意进制

#### 除基取余法证明(整数部分)

1. $\frac{K_n\times r^n+K_{n-1}\times r^{n-1}+...+K_2\times r^2+K_1\times r^1+K_0\times r^0}{r}=K_n\times r^{n-1}+K_{n-1}\times r^{n-2}+...+K_2\times r^1+K_1\times r^0...K_0$(余数)
2. 令$K_n\times r^{n-1}+K_{n-1}\times r^{n-2}+...+K_2\times r^1+K_1\times r^0=x$
3. $K_n\times r^n+K_{n-1}\times r^{n-1}+...+K_2\times r^2+K_1\times r^1+K_0\times r^0$可表示为$rx+K_0$
4. 由于$K_0∊[0, r-1], 所以\frac{rx+K_0}{r}$所得的商为$x$, 余数为$K_0$
5. 用得到的商除以r, 依次得到余数$K_n$

#### 乘积取整法证明(小数部分)

1. $(K_{-1}\times r^{-1}+K_{-2}\times r^{-2}+...+K_{-m}\times r^{-m})\times r=K_{-1}\times r^{0}+K_{-2}\times r^{-1}+...+K_{-m}\times r^{-(m-1)}$
2. 得到的整数部分$K_{-1}\times r^{0}$为$K_{-1}$的值
3. 将剩下的小数部分$K_{-2}\times r^{-1}+...+K_{-m}\times r^{-(m-1)}$乘以$r$, 得到$K_{-2}$的值
4. 用得到的小数部分乘以$r$, 依次得到$K_{-m}$

若小数部分的无论经过多少次的乘法都无法得到准确的二进制表示, 则要保留一定的精度(不是每个十进制的小数都能用二进制精确的表示, 但是任意一个二进制的小数都可以用十进制小数表示)

### 真值和机器数

在计算机中, 常常采用数的符号和数值一起编码的方法来表示数据. 常用的有原码、反码、补码、移码

- 真值: 复合人类习惯的数字
- 机器数: 数字实际存到机器里面的形式, 正负号需要被“数字化”