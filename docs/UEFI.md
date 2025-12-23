# UEFI

## プロトコル

各プロトコルには GUID が割り当てられている。

### `locate_protocol()`

EFI System Table に `locate_protocol()` の関数ポインタが登録されている。

`locate_protocol()` 関数にプロトコルの GUID を渡すことで、そのプロトコルへのポインタを得ることができる。

## EFI Graphics Output Protocol

フレームバッファのアドレスが含まれている。