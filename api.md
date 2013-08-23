# API

For the time being, our product is in private beta. If you'd like to try it out, please [leave us your email address](http://bitswipe.com).

## Quick start
Following code will create a payment of 1 BTC.

```
$ curl https://api.bitswipe.com/payments   \
       -XPOST                              \
       -u username:password                \
       -H 'Content-Type: application/json' \
       -d '{"amount": "1"}'
```

## Current API endpoints

  * Production - https://api.bitswipe.com
  
## Resources

Bitswipe API is a JSON REST API organized around resources. There are following resources:

  * [Payment](#payment)
  * [User](#user)
  
### Payment

Payment resource has the following properties:

  * `id` - string, unique payment ID
  * `amount` - string, payment amount
  * `user` - string, user this payment belongs to
  * `address` - string, Bitcoin address this payment should be paid to
  * `state` - string, either `'waiting'` - meaning that payment wasn't received yet, `'accepted'` - meaning that payment was accepted and will be sent to merchant during next payout or `'paid'` - meaning that the payment was paid out.
txid - string, Bitcoin transaction ID, assigned when payment is received