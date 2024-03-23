# Vagrant

## Vagrant for M1 MacOS

There are two common options to run vagrant on Mac:

- VMWare Fusion as provider
  - references: [Installing Vagrant on Apple Silicon Macs (M1, M1X, etc)](https://gist.github.com/fatso83/49980bbf065022d36c3a42369479a8df)
- qemu as provider
  - references: [Do M1 Mac Dream of x86 Linux?](https://medium.com/@TETRA2000/do-m1-mac-dream-of-x86-linux-117478fc9623)


The following example shows how to use qemu as the provider:

```bash
brew install qemu
vagrant plugin install vagrant-qemu
vagrant init -m perk/ubuntu-22.10-arm64
vagrant up
```
