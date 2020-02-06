# Payment on testing environments

## Use fake cards

At Kapten, we have chosen Adyen as our Payment Service Provider (PSP). 

On testing environments, there is no need to use your real credit card.

Instead, visit this link: https://docs.adyen.com/development-resources/test-cards/test-card-numbers

and chose the desired credit card for your test.

Some examples:

|*Card Type*     |*Card number*       |*Expiry date* |*CVC/CID*     |
|----------------|--------------------|--------------|--------------|
|Visa            |4035 5010 0000 0008 |03/2030       |737           |
|Visa            |4977 9494 9494 9497 |03/2030       |737           |
|Mastercard      |5136 3333 3333 3335 |03/2030       |737           |
|Mastercard      |5555 4444 3333 1111 |03/2030       |737           |

## 3-DS

*3-D Secure* is an additional security step aimed to verify online credit/debit card transactions. 

When 3-DS is activared, the card holder need to enter an additional information such as a password or a dynamic one-time password in order to validate a payment or to add a new credit card.

There are specific testing cards which can trigger this 3-DS step.

Those cards can be found at this link: https://docs.adyen.com/development-resources/test-cards/test-card-numbers#test-3d-secure-2-authentication

Some examples:

|*Card Type*     |*Card number*       |*Expiry date* |*CVC/CID*     |
|----------------|--------------------|--------------|--------------|
|Visa            |4917 6100 0000 0000 |03/2030       |737           |
|Mastercard      |5454 5454 5454 5454 |03/2030       |737           |

## Apple Pay

*Apple Pay has already been configured on all the test devices we are using.*

If you want to add another Apple Pay test card in the Wallet app, follow the link bellow. 
Under the section `Test Cards for Apps and the Web` you will find a list of all Apple Pay test cards: https://developer.apple.com/apple-pay/sandbox-testing/

Some examples:

|*Card Type*     |*Card number*       |*Expiry date* |*CVC/CID*     |
|----------------|--------------------|--------------|--------------|
|Visa            |4761 2622 6000 4228 |11/2022       |940           |
|Mastercard      |5204 2477 5000 1505 |11/2022       |111           |