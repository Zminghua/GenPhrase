File listing:
----------------------------
- anymalign.py: anymalign算法
- filter.py: 自定义过滤脚本
- filter_conf.json: 过滤规则配置文件
- run_align.sh: 启动脚本
- options: anymalign算法参数说明
- README.md


Description
----------------------------
本程序的目标是以平行语料作为输入，输出高质量的平行短语对。包括两个阶段：抽取和过滤，通过run_align.sh来控制运行的流程。
首先，anymalign.py执行抽取过程；其次，filter.py根据filter_conf.json中的配置，完成过滤操作。


File format
----------------------------
##### 1. 平行语料
分离的文本文件，对应的行互为翻译

源文件
```
He is one of my friends.
She put a bunch of flowers by the edge of the table.
```
目标文件
```
他是我的朋友。
她把一束花放在桌边。
```

##### 2. 短语对齐文件
每行是一对短语，包括5个字段：源短语，目标短语，词汇权重，翻译概率和频率，以 \t 分隔
```
a bunch of flowers \t 一束花 \t 0.98 0.86 \t 1.0 0.5 \t 1276
```
其中词汇权重和翻译概率均包含源到目标和目标到源的两个值，以空格分隔


Usage
----------------------------
##### Requirements
- numpy
- json

```
$ git clone https://github.com/AtmanCorp/data-process.git
$ cd data-process/data_process/gen_phrase/
$ ./run_align.sh <source> <target>

```


Contact
----------------------------
* 张明华
* zhangmh1993@163.com
* Atman Corp

