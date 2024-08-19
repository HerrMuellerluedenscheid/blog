Flashing the Nucleo Board Fails

Running into this issue?

```
❯ cargo run --bin blinky
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.26s
     Running `probe-rs run --chip STM32L031K6Tx target/thumbv6m-none-eabi/debug/blinky`
Error: An error with the flashing procedure has occurred.

Caused by:
    No flash memory contains the entire requested memory range 0x080000B8..0x0800BA48.
```

The memory layout should be already set by "memory.x is provided automatically if you pass the memory-x feature".

If it doesn't fit in the smaller flash, build with --release to enable optimizations

Credits go to `dirbaio` on embassy matrix chat!