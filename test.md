```flow
st=>start: Start
spaceSt=>operation: 5个空域候选
timeSt=>operation: 2个时域候选
space2=>operation: 最多选出4个
time2=>operation: 最多选出1个
remove=>operation: 去冗余候选
judgeK1=>condition: 候选输K<最大候选数？
judgeK2=>condition: 候选输K<最大候选数？
B=>operation: 加组合双向预测候选（B帧）
zero=>operation: 加0运动矢量候选
en=>end: 形成合并候选列表，候选数=最大候选数

st->spaceSt->space2->remove
st->timeSt->time2->remove
remove->judgeK1
judgeK1(no)->B->judgeK2(no)->zero->en
judgeK1(yes)->en
judgeK2(yes)->en
```
