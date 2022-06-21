# Create payment
Endpoint: `/createPayment`

Body:
```json
{
  "additional_info":"here you can put any infos, will be used in the webhook, so you can put the id for example of your customer", *
  "address":"mmFzJnZ5RjVfAFPjbJfnu2djZ2iRrSR3Vg", *
  "webhook_url":"https://diamond-trade.vip/payment", *
  "minimum_confirmations":4,
  "price":0.003, *
  "satoshi-per-byte":6,
  "exact":false,
}
```
Note: if `exact` is false, it'll let the customer send for example 28$ on a 30$ product, ~5% error allowed. If it's on true, he'll have to resend the 2$.

Response:
```json
{
  "expire":1645134736212,
  "payment_info":{
    "payment_id":"sMoDboa7MVlOW561miXKtm34xMsS2a6Y",
    "price":0.003,
    "address":"myRdLgqkvvT3MR7sHVGyTNG2kBZanHYViX",
    "send_to":"mmFzJnZ5RjVfAFPjbJfnu2djZ2iRrSR3Vg" 
  }
  "settings":{
    "satoshi-per-byte":6,
    "webhook_url":"https://diamond-trade.vip/payment",
    "minimum_confirmations":4
  }
}
```

Webhook Content:
```json
{
  "payment_id":"sMoDboa7MVlOW561miXKtm34xMsS2a6Y",
  "additional_info":"here you can put any infos, will be used in the webhook, so you can put the id for example of your customer"  
}
```
