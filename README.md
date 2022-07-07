# solana-bug-example-1

This is an example of how the new release of solana (1.11+) breaks local bpf builds.

Un/comment the Good and bad sections in `Cargo.toml` to view the error,

```
error: could not compile `crossbeam-epoch`

Caused by:
  process didn't exit successfully: `rustc --crate-name crossbeam_epoch --edition=2018 /Users/pete/.cargo/registry/src/github.com-1ecc6299db9ec823/crossbeam-epoch-0.9.5/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts --crate-type lib --emit=dep-info,metadata,link -C opt-level=3 -C embed-bitcode=no --cfg 'feature="alloc"' --cfg 'feature="lazy_static"' --cfg 'feature="std"' -C metadata=06757660a1a3615f -C extra-filename=-06757660a1a3615f --out-dir /Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps --target bpfel-unknown-unknown -L dependency=/Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps -L dependency=/Users/pete/dev/solana-bug-test/target/release/deps --extern cfg_if=/Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps/libcfg_if-74a5831ff37c822e.rmeta --extern crossbeam_utils=/Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps/libcrossbeam_utils-df5413d712a29e1d.rmeta --extern lazy_static=/Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps/liblazy_static-d48ccaf13996ae26.rmeta --extern memoffset=/Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps/libmemoffset-9e10e82b18b2e6b6.rmeta --extern scopeguard=/Users/pete/dev/solana-bug-test/target/bpfel-unknown-unknown/release/deps/libscopeguard-bfa5273ebeb78c31.rmeta --cap-lints allow -C lto=no` (signal: 11, SIGSEGV: invalid memory reference)
```
