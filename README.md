Atmega328p standalone "blink" project, using avr-hal (https://github.com/Rahix/avr-hal.git), not ruduino. 

Derived from the examples given in the avr-hal github repo. All credit goes there.

It works on the bare "chip" on a breadboard, no special hardware, except wires, a led and a resistor. 
Needs some form of programmer, of course, i use a "buspirate". But a raspberry pi would to the job.

And don't forget to read this:
https://book.avr-rust.org/

## Updated to new toolchain. 
Why? Rust-Analyzer of VSCode stopped working for me. (Toolchain too old)

Just changing the channel in rust-toolchain.toml wasn't enough,
the semantics in the configuration has been changed (and simplified)

- avr-atmega328p.json is obsolete. 
- .cargo/config.toml has 2 different entries in "build" section
- my flash script has to be adapted, as the output dir has changed.

For me, the changed toolchain has to be installed manually with the command 
>rustup toolchain install nightly-2025-03-04-x86_64-unknown-linux-gnu

A plain "nightly" toolchain would certainly do as well, (with apropriate changes in rust-toolchain.toml) but i prefer a fixed one, as before.