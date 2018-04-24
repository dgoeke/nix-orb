# nix-orb

Early proof of concept of orb feature.  This `nix/build` orb compiles nix expressions and stores the results.

Example:
```yaml
  sample-nix-workflow:
    jobs:
      - nix/build:
          cache-key: hello-haskell
          execute: /root/project/result/bin/hello-haskell
```

This looks for and builds `default.nix` in the local directory, caches/restores the `/nix` directory with the named `cache-key`
parameter.  After building, it executes a binary named in the `execute` parameter.

This repo include a sample "Hello World" Haskell project along with a nix expression for building it.
