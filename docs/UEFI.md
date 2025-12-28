# UEFI

## EFI Boot Services Table

UEFI がメモリに配置した各種サービスを提供する関数のポインタを含んだ構造体。

### `locate_protocol()`

EFI System Table に `locate_protocol()` の関数ポインタが登録されている。

`locate_protocol()` 関数にプロトコルの GUID を渡すことで、そのプロトコルへのポインタを得ることができる。

### `get_memory_map()`

## プロトコル

各プロトコルには GUID が割り当てられている。

## EFI Graphics Output Protocol

フレームバッファのアドレスが含まれている。
