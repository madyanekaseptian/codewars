# Bit Counting
Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.

_Example_: The binary representation of `1234` is `10011010010`, so the function should return `5` in this case

## Solusi 1

Singkat, jelas, padat, but no fun.

```ts
function countBits(n: number): number {
  return n
    .toString(2)
    .split("")
    .map(Number)
    .filter((i) => i === 1).length;
}
```

## Solusi 2

Cara saya memecahkan kasus ini dengan cara agak panjang untuk melatih logika, [berdasarkan cara ini](references.md).
Pertama saya perlu mengonversi nilai integer menjadi biner (dalam bentuk objek array):

```ts
function convertIntegerToBinary(n: number): number[] {
  let result: number[] = [];
  let number = n;

  if (number < 0) throw new Error("Argument must be a non-negative integer");
  if (number === 0) return result;

  while (number > 0) {
    const quotinent = number % 2;
    result.unshift(quotinent)
    number = Math.floor(number / 2);
  }

  return result;
}
```

Kemudian saya perlu menghitung banyaknya angka 1 di dalam array tsb:

```ts
function countBits(n: number): number {
  let countBitOne = 0;
  const binary = convertIntegerToBinary(n);
  if (binary.length === 0) return 0;
  for (const digit of binary) {
    if (digit === 1) countBitOne++;
  }
  return countBitOne;
}
```
