# ABISignatureBruteforcer
ETH ABI Signature Bruteforcer

## Build
`go build`

## Usage
```
Usage:
  ABISignatureBruteforcer [flags]

Flags:
  -h, --help            help for ABISignatureBruteforcer
  -s, --name string     name of your function that needs to be bruteforced. use * as placeholder [hello_world_*(uint,address)]. Parenthesis needed!
  -t, --target string   target signature, use * as wildcard for any byte. i.e: 0x000000**
```

Example in order to find a matching function signature for signature hash 0x5928afaa:

```
./ABISignatureBruteforcer -s "*()" -t 0xe21e5940
```

This shall find a matching signature in just a few seconds.
Every dot output represents 1 million attempts.
Since the search space is 2^32, it will on average take a bit over 2 billion attempts (thus ~2000 dots) to find a matching signature for a fully defined signature hash.