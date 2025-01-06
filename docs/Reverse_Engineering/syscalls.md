# System Calling Conventions
```bash
man syscall
```
System calls sit in between the user and kernel space. They are the mechanism used by the user space to request a service from the kernel.

## syscall Invocation Chart

| Arch/ABI      | Instruction | System call # | Ret val | Ret val2  | Error |
|---------------|-------------|---------------|---------|-----------|-------|
| **i386**      | int $0x80   | eax           | eax     | edx       | -     |
| **x86-64**    | syscall     | rax           | rax     | rdx       | -     |
| **arm64**     | svc #0      | w8            | x0      | x1        | -     |
| **mips**      | syscall     | v0            | v0      | v1        | a3    |

## syscall Argument Passing Chart

| Arch/ABI      | arg1 | arg2 | arg3 | arg4 | arg5 | arg6 | arg7 |
|---------------|------|------|------|------|------|------|------|
| **i386**      | ebx  | ecx  | edx  | esi  | edi  | ebp  | -    |
| **x86-64**    | rdi  | rsi  | rdx  | r10  | r8   | r9   | -    |
| **arm64**     | x0   | x1   | x2   | x3   | x4   | x5   | -    |
| **mips**      | a0   | a1   | a2   | a3   | a4   | a5   | -    |
