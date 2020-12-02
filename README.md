# Poet generation

## 项目介绍

本项目是唐诗风格的诗歌生成，分为诗歌补全和藏头诗生成。训练数据为[唐诗](https://github.com/chinese-poetry/chinese-poetry)五万余首。

## 模型结构与思路

思路：目标是需要训练出诗歌的语言模型。使用字级别的LSTM模型，记诗歌为长度n的字符串s，则s[0:(n-1)]为输入，s[1:n]为输出

模型结构：输入->embedding层->LSTM->线性层->输出

## Demo:

1.诗歌补全

```python
import poet_model
start_words = '九江'
results = poet_model.generate(start_words)
print(''.join(i for i in results))
```

输出完整诗歌：

九江天外碧凝深，酒后醒余一遍空。

飞动碧虚千片动，水声鱼在百花中。

2.藏头诗

```python
results = poet_model.cang_tou(start_words)
print(results)
```

输出藏头诗：

九重天子春常乐，百县宫娃蕙不浓。 

江上山头云火重，太湖楼下杜门开。