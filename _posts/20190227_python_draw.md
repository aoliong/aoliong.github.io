# Python 画图笔记


## 结合pandas.DataFrame.plot和figure/add_subplot来精确把握图像位置

使用dataframe.plot画图是很方便的，只把数据整理到一个dataframe里，直接调用plot就可以把图像画出来，再进行简单的修饰就很漂亮了。

```python
import pandas as pd

df = pd.DataFrame({"A":[2,3,1], "B":[1,2,2]})
ax = df[['A', 'B']].plot(figsize=(10,4))
ax.set_title('标题')
ax.set_ylabel('Y')
ax.set_xlabel('X');
```

但是，当想控制多个子图的位置时，只使用dataframe.plot就不够了。

先理解一下axes和figure的概念，参考[这里](https://www.zhihu.com/question/51745620)。搞清楚这两个概念后，就可以结合起来使用了。

```python
import pandas as pd
import matplotlib.pyplot as plt

fig=plt.figure()
axes1 = fig.add_subplot(1,2,1)
axes2 = fig.add_subplot(1,2,2)
df1 = pd.DataFrame({"A":[2,3,1], "B":[1,2,2]})
df2 = pd.DataFrame({"C":[4,2,3]})

ax = df1[['A', 'B']].plot(figsize=(10,4), ax=axes1)
ax.set_title('标题1')
ax.set_ylabel('Y')
ax.set_xlabel('X')

ax = df2[['C']].plot(figsize=(10,4), ax=axes2)
ax.set_title('标题2')
ax.set_xlabel('X');
```
