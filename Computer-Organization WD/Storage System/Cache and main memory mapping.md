## Cache和主存的映射方式

### 全相联映射(随意放)

> 假设某个计算机的主存地址空间大小为256MB, 按照字节编址, 其数据Cache有8个Cache行, 行长为64B
> <br> Cache的总大小为512B, 256M=2^28, 主存的地址共28位, 2^28/2^6=2^22, 主存块号共22位, 块内地址共6位
> CPU访问主存地址1...1101 001110:
> 1. 主存地址的前22位, 对比Cache中所有块的标记
> 2. 若标记匹配且有效位=1, 则Cache命中, 访问块内地址为001110的单元
> 3. 若未命中或有效位=0, 则正常访问主存

![](https://github.com/Ricolxwz/Computer-Organization-408/blob/main/Computer-Organization%20WD/Storage%20System/IMG/Cache%20and%20main%20memory%20mapping1.png)

### 直接映射(只能放固定位置)

主存块在Cache中的位置=主存块号%Cache总块数, 缺点是其他地方有空闲Cache块, 但是8号主存块不能使用

主存块号%(2^3), 相当于留下最后三位二进制数(若Cache总块数=2^n, 则主存块号末位n位直接反映它在Cache中的位置), 将主存块号的其余作为标记即可

> CPU访问主存地址0...01000 001110: 
> 1. 根据主存块号的后3位确定Cache行
> 2. 若主存块号的前19位与Cache标记匹配且有效位=1, 则Cache命中, 访问块内地址为001110的单元
> 3. 若未命中或者有效位=0, 则正常访问主存

### 组相联映射(可放到特定分组)

所属分组=主存块号%分组数

主存块号%2^2, 相当于留下最后两位

> CPU访问主存地址1...1101001110: 
> 1. 根据主存块号的后2位确定所属分组号
> 2. 若主存块号的前20位与分组内的某个标记匹配且有效位=1, 则Cache命中, 访问块内地址为001110的单元
> 3. 若未命中或者有效位=0, 则正常访问