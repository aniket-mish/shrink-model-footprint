# shrink-model-footprint

## Quantization

**problem**

nn have billions of parameters

llama 2 - 7b parameters (smallest llama)

If every param is 32 bit → 28 GB storage needed

At inference, we need the params in memory

Computers are slow at computing floating-point ops

**solution**

quantization converts FP numbers to integers (smaller footprint)

it does not mean rounding/truncating

speeds up computation as well

**advantages**

less memory required

latency reduces at inference time

less energy consumption (smartphones)

computer uses fixed numbers of bits to represent any data (number, char, color)

8 bits (byte), 16 bits (short), 32 bits (int), 64 bits (long)

python uses BigNum arithmetic (each number is stored as an array of numbers in base 2**30) which is done by CPython (python interpreter) that means if we want to speed up the operations, we are forced to use numbers in fixed format (32 bits)
