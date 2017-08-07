# legos.nmap

[![Travis](https://img.shields.io/travis/bbriggs/legos.nmap.svg)]() [![PyPI](https://img.shields.io/pypi/pyversions/legos.nmap.svg)]() [![PyPI](https://img.shields.io/pypi/v/legos.nmap.svg)]() [![PyPI](https://img.shields.io/pypi/wheel/legos.nmap.svg)]() [![PyPI](https://img.shields.io/pypi/l/legos.nmap.svg)]() [![PyPI](https://img.shields.io/pypi/status/legos.nmap.svg)]()

Run nmap scans from chat! This is a terrible idea and I can't recommend it to anyone, but if you decide that this is something that sounds fun, I won't stop you.

## Installation

`pip3 install legos.nmap` will grab this package and the Legobot required to run it.

## Example

```python
import threading
from Legobot.Lego import Lego
from legos.nmap import LegoNmap
from Legobot.Connectors.Slack import Slack
from Legobot.Legos.Help import Help

# Initialize lock and baseplate
lock = threading.Lock()
baseplate = Lego.start(None, lock)
baseplate_proxy = baseplate.proxy()

# We need some sort of chat medium to communicate with it
baseplate_proxy.add_child(Slack, token='aaaabbbbcccc')

# Add children
baseplate_proxy.add_child(Help)
baseplate_proxy.add_child(LegoNmap)
```

### Commands

The Nmap Lego is triggered by the `!nmap` prefix. Example: `!nmap simple google.com 443` will scan `google.com` on 443/tcp.


#### Simple

`!nmap simple {host(s)} {port(s)}`

Examples:
  - `!nmap simple 127.0.0.1 22`
  - `!nmap simple 192.168.1.0/24 80` 
  - `!nmap simple 192.168.1.1 21-23,80,443`

#### OS

`!nmap os {host(s)}`

Performs OS fingerprinting and returns best guess. Only returns the first guess, not subsequent ones.

Examples:
  - `!nmap os 127.0.0.1`
  - `!nmap os 192.168.1.0/24`

## Contributing

As always, pull requests and issues are welcome.
