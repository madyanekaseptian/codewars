# [How to convert decimal to binary](https://www.rapidtables.com/convert/number/decimal-to-binary.html?x=1234)

Divide the number by 2 repeatedly: 

1. Divide the number by 2.
2. The remainder (0 or 1) is the next bit, starting from the rightmost bit (bit 0).
3. Divide the integer quotient by 2 again.
4. Repeat until the quotient is 0. Read the remainders from the last one to the first one.

## Example #1

Convert 1310 to binary:

|Division by 2|Quotient|Remainder  <br>(bit)|Bit #|
|---|---|---|---|
|13 ÷ 2|6|1|0|
|6 ÷ 2|3|0|1|
|3 ÷ 2|1|1|2|
|1 ÷ 2|0|1|3|

Result: $13_{10} = 1101_2$