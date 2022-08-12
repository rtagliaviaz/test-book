# AMM 
---

Atrix allocates all tokens deposited into its liquidity pools into Serum based on a constant product equation. Atrix utilizes this equation to create a number of open orders on Serum which are updated as swaps and trades are performed. In the future, distributions may be updated according to on-chain oracles. Atrix will also run cranks for liquidity pools, to ensure Atrix-placed Serum orders are always up to date, as most projects will likely not have the resources to manage Serum liquidity on their own.

```code
x * y = k
x = amount of token A
y = amount of token B
k = constant
```