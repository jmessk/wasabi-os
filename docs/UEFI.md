# UEFI

## EFI Boot Services Table

UEFI がメモリに配置した各種サービスを提供する関数のポインタを含んだ構造体。

- `locate_protocol()`

    関数にプロトコルの GUID を渡すことで、そのプロトコルへのポインタを得ることができる。

- `get_memory_map()`

    メモリマップの情報を受け取ることができる。

## プロトコル

各プロトコルには GUID が割り当てられている。

## EFI Graphics Output Protocol

フレームバッファのアドレスが含まれている。

## Memory Map

`get_memory_map()` 関数からは、Memory Descripter の配列が返される。この配列は要素ごとにサイズが異なり、次の要素を得るためには、`MemoryDescriptor` 構造体の `size` フィールドを加算する必要がある。

### Memory Type

- `ACPI_MEMORY_NVS`  
   ACPI がスリープ周りの処理に使うための領域（OS は使用禁止）
- `ACPI_RECLAIM_MEMORY`  
   ACPI テーブルが置かれている領域（OS は ACPI テーブルを全部読み終わったら自由に使ってよい）
- `BOOT_SERVICES_CODE` / `BOOT_SERVICES_DATA`  
   UEFI の Boot Services で使われるコードとデータ
- `CONVENTIONAL_MEMORY`  
   通常の読み書きに使えるメモリ
- `LOADER_CODE`  
   ローダ（つまり WasabiOS）のコードが置かれている領域
- `RESERVED`  
   何らかの事情で予約されている OS は使用できない領域
- `RUNTIME_SERVICES_CODE` / `RUNTIME_SERVICES_DATA`  
   UEFI の Runtime Services で使われるコードとデータ
