---
id: 2p6c6xv3ru26yx2c39sno6g
title: Vector Copying
desc: ''
updated: 1641377055235
created: 1641377055235
---


### Vector copying

In this example `salePrices = origPrices;`

```cpp

const int   NUM_ELEMENTS = 4;         // Number of elements
vector<int> origPrices(NUM_ELEMENTS); // Original prices
vector<int> salePrices(NUM_ELEMENTS); // Sale prices
int i = 0;                            // Loop index

// Assign original prices
origPrices.at(0) = 10;
origPrices.at(1) = 20;
origPrices.at(2) = 30;
origPrices.at(3) = 40;

// Copy original prices to sales prices

salePrices = origPrices;
```

vector `salePrices` is empty and of size 0 until it copies every element in `origPrices`. This is a complete duplication and takes up twice the memory.
