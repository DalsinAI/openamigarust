# Plan

The single plan for OpenAmigaRust. Each PR that finishes a step updates it.

| Step | What | Status |
| --- | --- | --- |
| 1 | A correct 68040 compiler: LLVM M68k fixes, Rust 1.97.0 built on them (amigachrome-stoves `rust-m68k`) | Done, 22 Oct 2026 |
| 2 | Load Rust programs on AmigaOS: elf.library (amigachrome-guest `libraries/openelf`) | Done, 22 Oct 2026 |
| 3 | `amiga-sys`: exec, dos and the other OS libraries callable from Rust, with register-based library calls | Not started |
| 4 | An AmigaOS 3.x target (`m68k-amigaos`): its own target spec, startup code, `alloc` on exec pools, the 68040 and soft float by default, the large code model | Not started |
| 5 | `std` for AmigaOS: files, time, environment and threads through dos.library and exec | Not started |
| 6 | Hunk output, so programs need no elf.library | Not started |
