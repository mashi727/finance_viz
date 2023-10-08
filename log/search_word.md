# これは何？

文字列の中に、文字列が含まれていることを確認した際のメモです。

## 状況

株式データのテクニカル指標にてヒストグラムやローソク表示を行いますが、その際の幅は株価の記録間隔に応じて変更しないと表示が崩れてしまいます。
ファイル名から株価の記録間隔がわかるようにcsvのデータを作成していますので、ファイル名に1minなどの時間が含まれているかを調べて、ヒストグラムなどの幅を決定する際に使用する。


## 結論

```python
if '1min' in FilePath.data_filename:
    FinData.duration = '1min'
elif '5min' in FilePath.data_filename:
    FinData.duration = '5min'
elif '15min' in FilePath.data_filename:
    FinData.duration = '15min'
elif '30min' in FilePath.data_filename:
    FinData.duration = '30min'
elif '60min' in FilePath.data_filename:
    FinData.duration = '60min'
else:
    FinData.duration = '60min_over'
```

とした。

