pyPromise
=========

Promise/A+ implementation for concurrent Python sweetness

```python
from pypromise import promise

@promise
def io_something(dir):
    return list_dir(dir)

def cb(value):
    print value

io_something('/hi').then(cb)

dirs = ['/i', '/promise', '/you']
promises = []
for d in dirs:
    promises.append(io_something(d))

for p in promises:
    print p.result() # Blocks until ready

```
