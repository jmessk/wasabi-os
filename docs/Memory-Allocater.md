# Memory Allocater

## First Fit Allocater

- alignment: 32 B
- 割り当てサイズは 2 の冪乗に繰り上げる。
- 割り当ての最小単位を `Header` 構造体のサイズと同等 (32 B) とする。これにより、alignment の計算が楽になる。
