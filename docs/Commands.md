# Commands

## UEFI

- Build for target `x86_64-unknown-uefi`

  ```bash
  cargo build --target x86_64-unknown-uefi
  ```

- Copy executable to directory

  ```bash
  cp target/x86_64-unknown-uefi/debug/wasabi.efi mnt/EFI/BOOT/BOOTX64.EFI
  ```

- Run with QEMU

  ```bash
  qemu-system-x86_64 -bios third_party/ovmf/RELEASEX64_OVMF.fd -drive format=raw,file=fat:rw:mnt
  ```
