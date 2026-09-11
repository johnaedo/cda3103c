---
share_cda3103c: "true"
site-folder: docs/Supplementary Material
---

Each control signal asks a question about what the instruction (opcode) does:

| Signal                                  | Question                                                                     | Purpose                                               | Values                                                                                                                                                                                                                                      |
| --------------------------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `RegDst`                                | Am I an R-Type instruction?                                                  | Select the destination register number                | ∘ `0`: I'm **not** an R-Type instruction, so the write destination register is specified by the `2nd register field`  <br>∘ `1`: I **am** an R-Type instruction, so the write destination register is specified by the `3rd register field` |
| `RegWrite`                              | Am I writing to a register?                                                  | Enable writing of register                            | ∘ `0`: I'm **not** writing to a register<br>∘ `1`: I **am** writing to a register                                                                                                                                                           |
| `ALUSrc`                                | Is my second input coming from Sign Extend? (Is my second input a constant?) | Select the 2nd operand for ALU                        | ∘ `0`: My second input is coming from the register file, so use the`2nd register field`  <br>∘ `1`: My second input is a constant from an immediate instruction, so take it from `Sign Extend`                                              |
| `ALUcontrol` or `ALUop` in your project | What is the ALU doing?                                                       | Select the operation to be performed by the ALU       | see `ALUcontrol` table                                                                                                                                                                                                                      |
| `MemRead`                               | Am I reading from memory?                                                    | Enable reading of data memory                         | ∘ `0`: I'm **not** reading from memory  <br>∘ `1`: I **am** reading from memory                                                                                                                                                             |
| `MemWrite`                              | Am I writing to memory?                                                      | Enable writing of data memory                         | ∘ `0`: I'm **not** writing to memory<br>∘ `1`: I **am**  writing to memory                                                                                                                                                                  |
| `MemToReg`                              | Am I reading from memory?                                                    | Select the result to be written back to register file | ∘ `0`: I'm **not** reading from memory, so the value being written to the register is ALU result  <br>∘ `1`: I **am** reading from memory, so write memory data back to the register                                                        |
| `Branch`                                | Am I a branch instruction?                                                   | Select the next `$PC` value                           | ∘ `0`: I'm **not** a branch instruction, so `$PC + 4`  <br>∘ `1`:  I **am** a branch instruction:  `($PC + 4)+(offset x 4)`                                                                                                                 |
| `Jump`                                  | Am I a jump instruction?                                                     | Select the next `$PC` value                           | ∘ `0`: I'm **not** a jump instruction: `$PC + 4`  <br>∘ `1`: I **am** a branch instruction: `$PC[31..28] : (offset x 4)`                                                                                                                    |
## Alternately...

| Signal     | Set to 1 if the opcode is... |
| ---------- | ---------------------------- |
| `RegDst`   | _R-Format_                   |
| `ALUSrc`   | `lw` OR `sw`                 |
| `MemToReg` | `lw`                         |
| `RegWrite` | _R-Format_ OR `lw`           |
| `MemRead`  | `lw`                         |
| `MemWrite` | `sw`                         |
| `Branch`   | `beq`                        |
| `Jump`     | `j` OR `jal`                 |
| `ALUop1`   | _R-Format_                   |
| `ALUop0`   | `beq`                        |