 # Arcane
## Operating System in Rust

- [x] [A Freestanding Rust Binary](https://os.phil-opp.com/freestanding-rust-binAary/) : Created Rust executable that does not link the standard library and Makes it possible to run it on bare metal without an underlying operating system.
- [x] [A Minimal Rust Kernel](https://os.phil-opp.com/minimal-rust-kernel/) : Created Minimal 64-bit Rust Kernel for x86-architecture. Created a bootable disk image that prints "Hello World" to the screen.
- [x] [VGA Text Mode](https://os.phil-opp.com/vga-text-mode/) : Created Rust Module that encapsulates unsafety of writing to VGA text buffer through memory mapping address `0xb8000` and presents a safe and convenient interface to the outside through `print!` and `println!` macros.
- [x] [Testing](https://os.phil-opp.com/testing/) : Set up Rust's custom test framework for our rust kernel. Used to implement support for simple `#[test_case]` attribute. Using the `isa-debug-exit` device of QEMU, our test runner can exit QEMU after running the tests and report the test status. To print error messages to the console instead of the VGA buffer, we created a basic driver for the serial port. And explored intergration tests.
- [x] [CPU Exceptions](https://os.phil-opp.com/cpu-exceptions/) : Used `x86_64` crate to introduce Exception handling. Crate provides `x86-interrupt` calling convention and [InterruptDescriptorTable](https://docs.rs/x86_64/0.14.2/x86_64/structures/idt/struct.InterruptDescriptorTable.html) type which made handling process easier. Currently it just caught `breakpoint` exception (int3 instruction) and returns from it.
- [x] [Double Faults](https://os.phil-opp.com/double-fault-exceptions/) : Learned what a Double Fault is and under which conditions it occurs. Added Basic double fault handler that prints an error message and added integration test for it. Also enabled hardware-supported stack switching on double fault exceptions so that it also works on stack overflow. Also learned about TSS(Task State Segment), IST(Interrupt Stack Table) and GDT(Global Descriptor Table).
- [x] [Hardware Interrupts](https://os.phil-opp.com/hardware-interrupts/) : Enabled and handled External Interrupts. learned 8259 PIC and its primary/secondary layout, the remapping of the interrupt numbers, and the "end of interrupt" signal. Implemented handlers for the hardware timer and keyboard and added `hlt` instruction, which halts the CPU until the next interrupt.
- [ ] [Introduction to Paging](https://os.phil-opp.com/paging-introduction/)
- [ ] [Paging Implementation](https://os.phil-opp.com/paging-implementation/)
- [ ] [Heap Allocation](https://os.phil-opp.com/heap-allocation/)
- [ ] [Allocator Designs](https://os.phil-opp.com/allocator-designs/)
- [ ] [Async/Await](https://os.phil-opp.com/async-await/)
