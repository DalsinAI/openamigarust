# OpenAmigaRust

Rust for the Amiga: programs written in Rust that run on AmigaOS 3.x on a
68040.

## Where it stands (23 October 2026)

- **The compiler works.** Stock Rust 1.97 builds 68k code that prints wrong
  numbers, hangs, and crashes the compiler. LLVM's M68k backend had six
  bugs, which are now fixed. The `rust-m68k` stove in
  [amigachrome-stoves](https://github.com/DalsinAI/amigachrome-stoves/tree/main/rust-m68k)
  builds Rust 1.97.0 on the fixed LLVM. Its output matches a PC's at every
  optimisation level.
- **Programs load through elf.library.** Rust builds a 68k ELF, and
  [elf.library](https://github.com/DalsinAI/amigachrome-guest/tree/main/libraries/openelf)
  loads it from the Shell. elf.library's `rust/hello` (`core` and `alloc` on an
  exec memory pool) has not been run on an Amiga yet; its fixture runs under
  qemu in elf.library's tests.
- **Not yet:** an AmigaOS target, the OS's libraries as Rust crates, and
  `std`. See [docs/PLAN.md](docs/PLAN.md).

## Building for the 68040

Install the stove (see its README), then build with its Cargo settings: soft
float and the large code model.

    RUSTC_BOOTSTRAP=1 cargo +rust-m68k build --release --target m68k-unknown-none-elf \
        --config /path/to/amigachrome-stoves/rust-m68k/cargo-config.toml \
        -Zbuild-std=core,alloc,compiler_builtins -Zbuild-std-features=compiler-builtins-mem

## Licence

MIT (see `LICENSE`). Copyright (c) 2026 AmigaChrome Team.

Designed, tested and delivered by The AmigaChrome Team.
