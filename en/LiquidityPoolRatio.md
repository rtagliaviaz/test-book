# Liquidity Pool Ratio
---

How does a pool's token ratio (internal price) work, and why is it sometimes not exactly the market price?

Let's take the example of the SOL-USDC pool. Serum markets each have their own minimum size requirement for an order. For example, the SOL/USDC market requires a minimum order size of 0.1 SOL. When this pool was first created, we deposited around $3k worth of liquidity. Let's say the market price was 162 USDC per SOL. It turns out that using only $3k worth of liquidity, orders very close to the market price, according to xy=k, did not pass the 0.1 SOL threshold to be placed, so they weren't placed. But orders further out in price, say at $150 and $175, were placed. So this means that the Atrix internal pool price will only be updated if those orders further out are filled.

So in this situation, as more liquidity is added and SOL price changes to fill existing orders, the Serum market's 0.1 SOL threshold will be met and orders closest to market price will be placed, and therefore price will follow the market very closely.

This is why $20k worth of liquidity was added initially to both the ETH-USDC and BTC-USDC pools. As according to xy=k and Serum market minimum order size requirements, those will need a little bit more liquidity to be accurate. But we only needed to add $2k to the SRM-USDC pool for the same accuracy.