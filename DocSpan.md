```python

"""
all_doc_tokens 滑動窗口分段,
輸出doc_spans是一系列滿足要求的分片，開始位置及長度
"""
import collections
_DocSpan=collections.namedtuple("DocSpan",["start","length"])
doc_spans=[]
start_offset=0

while start_offset<len(all_doc_tokens):
  length=len(all_doc_tokens)-start_offset
  if length>max_tokens_for_doc:
    length=max_tokens_for_doc
  doc_spans.append(_DocSpan(start=start_offset,length=length))
  if start_offset+length == len(all_doc_tokens):
    break
  start_offset +=min(length,doc_stride)

```
