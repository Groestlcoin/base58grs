# base58

[![PyPI Version][pypi-image]](https://pypi.python.org/pypi?name=base58grs&:action=display)
[![PyPI Downloads][pypi-downloads-image]](https://pypi.python.org/pypi?name=base58grs&:action=display)

Base58 and Base58Check implementation compatible with what is used by the
groestlcoin network.

Starting from version 2.0.0 **python2 is no longer supported** the 1.x series
will remain supported but no new features will be added.


## Command line usage

    $ printf "hello world" | base58grs
    StV1DL6CwTryKyV

    $ printf "hello world" | base58grs -c
    3vQB7B6MrGQZaxCpm9RU5

    $ printf "3vQB7B6MrGQZaxCpm9RU5" | base58grs -dc
    hello world

    $ printf "4vQB7B6MrGQZaxCpm9RU5" | base58grs -dc
    Invalid checksum


## Module usage

    >>> import base58grs
    >>> base58grs.b58encode(b'hello world')
    b'StV1DL6CwTryKyV'
    >>> base58grs.b58decode(b'StV1DL6CwTryKyV')
    b'hello world'
    >>> base58grs.b58encode_check(b'hello world')
    b'3vQB7B6MrGQZaxCpm9RU5'
    >>> base58grs.b58decode_check(b'3vQB7B6MrGQZaxCpm9RU5')
    b'hello world'
    >>> base58grs.b58decode_check(b'4vQB7B6MrGQZaxCpm9RU5')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
      File "base58.py", line 89, in b58decode_check
        raise ValueError("Invalid checksum")
    ValueError: Invalid checksum


[pypi-image]: https://img.shields.io/pypi/v/base58grs.svg?style=flat
[pypi-downloads-image]: https://img.shields.io/pypi/dm/base58grs.svg?style=flat
