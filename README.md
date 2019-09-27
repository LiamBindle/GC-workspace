# GC-workspace

This is my personal workspace for GC dev. The main feature of this workspace is it can debug GC-Classic and GCHP remotely with the VS Code IDE.

Steps for remote GEOS-Chem debugging:
1. I establish an SSH tunnel between my localhost and a remote compute node (through the login node via a `ProxyJump`)
2. Run `gdbserver` on the remote compute node and connect it to port `27182`
3. In VS Code on my local machine, I attach gdb to port `27182` (which is the `gdbserver` at the other end of the tunnel).

I use the following VS Code extensions:
- C/C++
- C++ Intellisense
- CMake
- ctagsx
- Fortran Breakpoint Support
- Modern Fortran
- Native Debug
- vscode-icons

## Useful for other people
The `.vscode` directory has scripts for setting up VSCode to launch GDB and attach it to the tunnel. The `gdbserver_gchp` script launches gdbserver and the tunnel on the node-side.
