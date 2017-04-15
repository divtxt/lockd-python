# lockd-python

Python client for the [lockd](https://github.com/divtxt/lockd) distributed lock service.

## Example Usage

This assumes a `lockd` server is running on the localhost at the default port.

```
~/wpy/lockd-python$ python
Python 2.7.10 (default, Oct 23 2015, 19:19:21)
[GCC 4.2.1 Compatible Apple LLVM 7.0.0 (clang-700.0.59.5)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from lockd import LockdClient
>>> lockd_client = LockdClient()
>>> lockd_client.is_locked("foo")
False
>>> lockd_client.lock("foo")
True
>>> lockd_client.lock("foo") # second lock attempt will fail
False
>>> lockd_client.is_locked("foo")
True
>>> lockd_client.unlock("foo")
True
>>>
```
