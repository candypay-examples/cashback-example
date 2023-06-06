# Cashback Example server

This is a base example server that lets you implement SPL token cashback through webhooks after each successful payment. For more details, head over to [Docs.](https://docs.candypay.fun/checkout/webhooks.html)

## Deployment
1. Fork the repo and make sure to change these [4 params](https://github.com/candypay-examples/cashback-example/blob/a78c908b109a2c5863bdb311a20bd49192bc553b/src/cashback.ts#L20-L33),
  - `tokenAddress` : Mint Address of SPL token which will be used as cashback
  - `tokenDecimal` : Decimals of that token
  - `cashback` : Amount of tokens to cashback for each $1 spent
  - `connection` : Use custom RPC for reliable and fast experience 
 
2. Deploy the repo on a server platform like [Railway](https://railway.app/dashboard) 
3. Copy URL of the deployed server and head over to [CandyPay dashboard](https://candypay.fun/settings). In the bottom of settings page, create a new webhook service entering name, description and URL of the server.
4. On creation a `webhook secret` key will be generated, copy the secret key and add as env in the server
```
WEBHOOK_SECRET= 'webhook secret key' 
SOLANA_PRIVATE_KEY= 'private key of solana wallet that will fund cashback tokens and gas fees'
```  
5. Add envs and redploy the server, and the cashback system is ready to go into action!

