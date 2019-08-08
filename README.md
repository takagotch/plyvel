### plyvel
---
https://github.com/wbolster/plyvel

```py
with db.write_batch() as wb:
  for i in xrange(100000):
    wb.put(bytes(i), bytes(i) * 100)

with db.write_batch() as wb:
  wb.put(b'key-1', b'value-1')
  raise ValueError("Something went wrong!")
  wb.put(b'key-2', b'value-2')

with db.write_batch(transaction=True) as wb:
  wb.put(b'key-3', b'value-3')
  raise ValueError("Something went wrong!")
  wb.put(b'key-4', b'value-4')

db.put(b'key', b'first-value')
```

```py
with db.iterator() as it:
  for k, v in it:
    pass
it.seek_to_start()
```

```
```
