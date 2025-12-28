# Serial

## Ports

各シリアルポートのアドレスは、昔からのハードウェア規約で決まっている。

| ポート名 | I/O address | IRQ |
| -------- | ----------- | --- |
| COM1     | 0x3F8       | 4   |
| COM2     | 0x2F8       | 3   |
| COM3     | 0x3E8       | 4   |
| COM4     | 0x2E8       | 3   |

## x86

x86 では、I/O 専用の命令として、`in` と `out` がある。

```asm
out dx, al
```

- dx: データを書き込むポートのアドレス
- al: 書き込むデータ

Rust のインラインアセンブリの例:

```rust
pub fn write_io_port_u8(port: u16, data: u8) {
    unsafe {
        asm!("out dx, al",
            in("al") data,
            in("dx") port)
    }
}
```

- `in("al") data`: `al` の値を `data` に格納する。
- `in("dx") port`: `dx` の値を `port` に格納する。
