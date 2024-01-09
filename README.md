# shrink-model-footprint

## Quantization

**problem**

neural networks have billions of parameters

llama 2 - 7b parameters (smallest llama)

if every param is 32 bit → 28 GB storage needed

at inference, we need the params in memory

computers are slow at computing floating-point ops

**solution**

quantization converts FP numbers to integers (smaller footprint)

this does not mean rounding/truncating

speeds up computation as well

**advantages**

less memory required

latency reduces at inference time

less energy consumption (smartphones)

computer uses fixed numbers of bits to represent any data (number, char, color)

8 bits (byte), 16 bits (short), 32 bits (int), 64 bits (long)

python uses BigNum arithmetic (each number is stored as an array of numbers in base 2**30) which is done by CPython (python interpreter) that means if we want to speed up the operations, we are forced to use numbers in fixed format (32 bits)

most modern GPUs also support 16-bit floating point numbers with less precision

**deep dive into quantization**

aims to use integers instead of floating point numbers for weights and biases while maintaining the accuracy of the model

integers operations are much faster than floating point operations

quantize - dequantize

during quantization we usually lose some precision and model is not as accurate as it was before

**types**

1) asymmetric - symmentric
