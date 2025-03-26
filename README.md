# Eli Array Minkoff

I am a passionate computer nerd, with a degree in Computer Networking and Cybersecurity. I often like to learn by doing, and almost always share what I create publicly.

Beyond maintaining my own personal computer network, which I host various websites from - mainly my personal Nextcloud system, I like to work on projects that help me push the boundaries of my knowledge about technology.

## Projects

### `eambfc` and `eambfc-rs`

My main project since May 2024 has been [`eambfc`](https://github.com/eliminmax/eambfc), alongside its counterpar, [`eambfc-rs`](https://github.com/eliminmax/eambfc-rs). What started as an attempt to help me learn C and later Rust by implementing a compiler for Urban Müller's infamous programming language, has turned into a deep dive into the POSIX and C standards and its pitfalls, tooling and testing frameworks for C and Rust, the oddities of different instruction set architectures, and the Linux system call ABI.

`eambfc` runs on any POSIX.1-2008 compliant system, and `eambfc-rs` runs on any supported Rust.

Both can output binaries for x86_64, 64-bit ARM, IBM z/architecture mainframes, and 64-bit RISC-V, all targeting the Linux syscall ABI.

### Tech journal

While working towards my degree, I maintained a tech journal about the different technologies I studied. Since graduating, I've maintained it, migrating from a GitHub wiki to a self-hosted [MkDocs-powered site](https://tech-docs.earrayminkoff.tech/)

### Tiny Clear Elf

My real first foray into machine code, and an exploration of taking debloating to its extreme, this project involved creating an alternative implementation of the `clear` command, which clears a terminal and its scrollback, using nothing more than a minimalistic hex editor and a lot of documentation and debugging tools. [The repo](https://github.com/eliminmax/tiny-clear-elf) has implementations for every architecture officially supported by Debian Bookworm or Trixie, as well as explanations about how they work.

The current Tiny Clear Elf `clear` implementation for amd64 is only 1.01% of the size of the Debian Bookworm build of the ncurses `clear` implementation, and only uses 4.35% of the number of system calls to run - not to mention, the ncurses implementation uses multiple dynamically-loaded libraries. If I wanted to be unfair and count them as part of the size, Tiny Clear Elf's `clear` is a mere 0.0069% the size.

That said, of course, it's not a fair comparison. The ncurses clear looks at the terminfo database for the terminal identified by the $TERM environment variable, and chooses the right sequence for that, while I just write a 6-byte sequence that works on every terminal I've tested it on, but might not work on others. Still, the point is to take debloating to an extreme, not to be practical or cover all use cases. And while one person's bloat may be another's needed feature, this is one case where I actually use my `clear` instead of the ncurses clear on all of my systems, and one of the first things I do when setting up a new Linux system is now installing the appropriate Tiny Clear Elf binary for the architecture.

### Colortest

This is a project I sometimes come back to while bored. I try to create a program that prints the following pattern to the terminal, using ANSI escape sequences and XTerm color codes:

![colortest pattern](https://github.com/eliminmax/colortest/blob/main/colortest_output.png).

It's a way to dip my toes into different languages - going at least a bit beyond "Hello, world", into basic control flow and function creation.

As of March 2025, there are 46 different implementations in a wide variety of languages, including domain-specific languages like AWK and jq, popular scripting languages such as Python and JavaScript, various JVM languages, system programming languages like Rust, C, and Zig, functional languages like Haskell, OCaml, and Elixir, esoteric languages like Befunge, Rockstar, and one with a name that can't be repeated in polite company, and historic languages like COBOL, Forth, and Fortran.

Provided access to adequate language documentation, I can usually get a new version written within 30-120 minutes.
