ssh-doom
==========

I have modified the original [https://github.com/Snawoot/ssh-tarpit](ssh-tarpit) to this: ssh-doom, where yes, it sends forkbomb sequences, instead of randomness.  Am I evil?  Also: in the future I may utilize this code to make the honeypot WORSE.  Such is, for programming adventures!

## WARNING: DO NOT HOST THIS ON YOUR PUBLIC VPS: I believe this is ILLEGAL, but I don't actually know
### USE AT YOUR __OWN__ DISCRETION, I AM NOT RESPONSIBLE FOR YOUR ACTIONS!!!

## Requirements

* Python 3.5.3+

## Installation

### From source

Run within source directory:

```
pip3 install .
OR:
pipx install .
```

## Usage

Synopsis:

```
$ ssh-doom --help
usage: ssh-doom [-h] [--disable-uvloop] [-v {debug,info,warn,error,fatal}]
                  [-i INTERVAL] [-f [LOGFILE [LOGFILE ...]]] [-a BIND_ADDRESS]
                  [-p BIND_PORT] [-D]

SSH doom that slowly sends an endless banner

optional arguments:
  -h, --help            show this help message and exit
  --disable-uvloop      do not use uvloop even if it is available (default:
                        False)
  -v {debug,info,warn,error,fatal}, --verbosity {debug,info,warn,error,fatal}
                        logging verbosity (default: info)
  -i INTERVAL, --interval INTERVAL
                        interval between writes in seconds (default: 2.0)
  -f [LOGFILE [LOGFILE ...]], --logfile [LOGFILE [LOGFILE ...]]
                        file(s) to log to. Empty string argument represents
                        stderr. Flag without arguments disables logging
                        completely. Default is stderr only. (default: [''])

listen options:
  -a BIND_ADDRESS, --bind-address BIND_ADDRESS
                        bind address (default: 127.0.0.1)
  -p BIND_PORT, --bind-port BIND_PORT
                        bind port (default: 2222)
  -D, --dualstack       force dualstack socket mode. Sets socket IPV6_V6ONLY
                        option to 0 (default: False)

```

## Notes:

* I'm not sure that ipv6 works, it didn't on my debian, consider using only ipv4 if it gives error, then adjusting your firewall as necessary.  
