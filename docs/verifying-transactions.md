---
id: verifying-transactions
title: Roqqu Documentation
sidebar_label: Verifying Transactions
---

## Verifying Transactions
After completing the initialization and the customer has made
a payment, you'll need to verify the status of the payment
before you give value to the customer. 

There are two ways to do this, either by using the <code>Roqqu API</code>
from your backend or by using <code>Webhooks</code> to trigger an
action from your backend.

### Method 1. Using the Roqqu API
Immediately after a payment is made and confirmed, the page redirects
to your return url 
set during initialization, this request will 
contain the transaction reference which you should
use in performing the check.

<!--DOCUSAURUS_CODE_TABS-->
<!--NodeJS-->
```js
console.log('Hello, world!');
```
<!--PHP-->
```php
print('Hello, world!')
```

<!--Curl-->
```curl
#include <stdio.h>

int main() {
   printf("Hello World!");
   return 0;
}
```

<!--C#-->
```c#
program HelloWorld;
begin
  WriteLn('Hello, world!');
end.
```

<!--END_DOCUSAURUS_CODE_TABS-->