# 🔥 Bit Manipulation Cheatsheet for CP 🚀

This README includes commonly used bit manipulation tricks, formulas, and CP utilities. Bookmark this if you're grinding for Div2+ or acing your DSA prep!

---

## ✅ Basic Formulas

| Expression | Description |
|-----------|-------------|
| `x & 1` | Check if number is **odd** |
| `x % 2 == 0` | Check if number is **even** |
| `x << 1` | Multiply `x` by 2 |
| `x >> 1` | Divide `x` by 2 |
| `x ^ 1` | Flip the last bit of `x` |
| `x & (x - 1)` | Remove the **rightmost set bit** |
| `x & -x` | Isolate the **rightmost set bit** |
| `x | (x + 1)` | Turn on the **rightmost 0 bit** |
| `x & (x + 1)` | Turn off the **rightmost 0 bit** |
| `x ^ (1 << k)` | Toggle the **k-th bit** |
| `x & ~(1 << k)` | Clear the **k-th bit** |
| `x | (1 << k)` | Set the **k-th bit** |

---

## 🧠 Bit Tricks and Built-ins

| Use-case | Trick |
|----------|-------|
| Check if `x` is power of 2 | `x && !(x & (x - 1))` |
| Count set bits in `x` | `__builtin_popcount(x)` |
| Count trailing 0s | `__builtin_ctz(x)` |
| Count leading 0s | `__builtin_clz(x)` |
| Binary representation | `bitset<32>(x).to_string()` |
| Swap `a` and `b` (no temp) | `a ^= b; b ^= a; a ^= b;` |
| Check if `i-th` bit is set | `(x >> i) & 1` or `x & (1 << i)` |
| Get log2(x) | `31 - __builtin_clz(x)` |
| Get number of bits to represent x | `32 - __builtin_clz(x)` |

---

## 🔁 Submask Loop

```cpp
for (int sub = mask; sub; sub = (sub - 1) & mask) {
    // use sub
}


## check if the ith bit is set
### (x >> i) & 1   // OR
### x & (1 << i)
