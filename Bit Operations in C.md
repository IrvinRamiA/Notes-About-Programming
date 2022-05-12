## Setting bit n

storage |= (1 << n);

0100_0010
OR
0000_1000
---------
0100_1010

## Clearing bit n

storage &= ~(1 << n);

0100_1010
AND  
1111_0111 
---------
0100_0010

## flipping bit n

storage ^= (1 << n);

01000010 01001010
XOR (y=1 if a=1 and b=0 or viceversa)
00001000 00001000 
-----------------
01001010 01000010

## Checking bit n

bit = storage & (1 << n);

0100_0010 0100_1010
AND
0000_1000 0000_1000
-------------------
0000_0000 0000_1000

## To check whether multiple bits are cleared, you'd typically use this somewhat more concise idiom:

if ((statusRegister & 0x00000102) == 0) {}
// or
if (!(statusRegister & 0x00000102)) {}

## You could also check whether multiple bits are set with:

if ((statusRegister & 0x00000102) == 0x00000102)
// or
if ((statusRegister | ~0x00000102) == ~0) {}
// or
if (!(~statusRegister & 0x00000102)) {}
