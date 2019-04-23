## word, token化(一个word可以分成多token;word-pieces)互相转换索引



```python
"""
例子：example.doc_tokens=["I","maked","dvd's"]
 转换为tokens=["I","make","###d","dvd","###'s"]
 
"""
        tok_to_orig_index = []   ##### [0,1,1,2,2] 
        orig_to_tok_index = []   ##### [0,1,3]
        all_doc_tokens = []      ##### tokens=["I","make","###d","dvd","###'s"]
        for (i, token) in enumerate(example.doc_tokens):
            orig_to_tok_index.append(len(all_doc_tokens))
            sub_tokens = tokenizer.tokenize(token)
            for sub_token in sub_tokens:
                tok_to_orig_index.append(i)
                all_doc_tokens.append(sub_token)
```
