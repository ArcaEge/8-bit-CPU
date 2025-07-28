# 8-bit CPU

A custom 8-bit CPU architecture designed in Logisim, aimed at (mostly) having feature parity with the 6502. It has a 16-bit address bus and I've allocated the first 32KiB to ROM, 16KiB to RAM and 16KiB to I/O.
## Architecture
### Memory map

### Registers
| Register | Register number | Description                                                                                   |
| -------- | --------------- | --------------------------------------------------------------------------------------------- |
| ACC      | TBD             | Accumulator, stores ALU output                                                                |
| JBH      | TBD             | Higher 8 bits of the 16-bit jump buffer. Overwrites the program counter on a jump instruction |
| JBL      | TBD             | Lower 8 bits of the 16-bit jump buffer. Overwrites the program counter on a jump instruction  |
| MAH      | TBD             | Memory address register, upper 8 bits                                                         |
| MAL      | TBD             | Memory address register, lower 8 bits                                                         |
| MDR      | TBD             | Memory data register, contents of the RAM at the specified address                            |
| OPR      | TBD             | Operand register, stores the operand of the current instruction. Read-only                    |
| STP      | TBD             | Stack pointer                                                                                 |
| STR      | TBD             | Status register, flags mapped to a register. Read-only, set/reset flags directly to modify    |
### Flags
| Flag                      | Code    | Flag number | Description                                                                        |
| ------------------------- | ------- | ----------- | ---------------------------------------------------------------------------------- |
| Carry                     | CFL     | TBD         | Set if the last operation caused an underflow from bit 0 or an overflow from bit 7 |
| Overflow                  | OFL     | TBD         | Set if the arithmetic operation overflowed and produced an invalid result          |
| Interrupt disable         | IDF     | TBD         | Enables/disables IRQs                                                              |
| Zero                      | ZFL     | TBD         | Set if the accumulator is zero, read-only                                          |
| Negative                  | NFL     | TBD         | Bit 7 of the accumulator, read-only. Write to accumulator directly to modify       |
| Accumulator 0-6           | AF0-AF6 | TBD         | Bits 0 to 6 of the accumulator, read-only. Write to accumulator directly to modify |
| General purpose flags 0-3 | GP0-GP3 | TBD         | General purpose, aren't automatically set/reset by operations                      |
### Instruction classes
| Instruction           | Opcode   | Description                                                                                                                |
| --------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------- |
| No-op                 | 00000000 | No-op, waits for \[TBD] clock cycles                                                                                       |
| Accumulator operation | TBD      | Forwards the operation to the accumulator                                                                                  |
| Move                  | TBD      | Sets the value of a register to the value of another                                                                       |
| Set flag state        | TBD      | Sets, resets or toggles a flag                                                                                             |
| Jump                  | TBD      | Sets the program counter value to the value of the 16-bit jump buffer                                                      |
| Increment/Decrement   | TBD      | Increments/decrements a register. Can use same opcode but different operand to determine whether to increment or decrement |
|                       | TBD      |                                                                                                                            |
| Compare               | TBD      |                                                                                                                            |
| Branch conditional    | TBD      | Branches if flag is/isn't set                                                                                              |
