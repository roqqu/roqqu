---
id: initialization
title: Roqqu Documentation
sidebar_label: Initialization
---

## Initialization
To start receiving payments, you must first initialize the <code>roqqu.js</code>
file. 

>Please note that only businesses which have completed the
 compliance process and have been verified can accept payments. This is to ensure
 that every business using our infrastructure have been properly
 vetted for Anti-Money Laundering policies.
 

 ### Step 1. Load the JS file
 
<!--DOCUSAURUS_CODE_TABS-->
<!--HTML-->

```html
<script src="https://js.roqqu.com/v1/roqqu.js"></script>
```

<!--END_DOCUSAURUS_CODE_TABS-->

If the <code>roqqu.js</code> is intialized correctly you should
not see any error on your browser console.


 ### Step 2. Create the Roqqu container
 After loading the Roqqu JS file on the page, you'll need to
 create a container that will house the Roqqu elements when
 they load.
 
 <!--DOCUSAURUS_CODE_TABS-->
 <!--HTML-->
 
 ```html
 <div id="roqquContainer"></div>
 ```
 
 <!--END_DOCUSAURUS_CODE_TABS-->
 

 ### Step 3. Write the Roqqu function
 The next step is to write your initialization function and parse
 your load parameters. This code should be placed after the
 closing body tag at the end of the page in order for it to
 work.
 
 Here's a basic structure of the code to get it up and running.
 
 > Please note that the key to use with Roqqu JS is the public key and not the secret key
 
 
 <!--DOCUSAURUS_CODE_TABS-->
  <!--JavaScript-->
  
  ```js
  function payWithRoqqu(){
     var handler = roqqu.init({
         amount: 350,
         currency: 'usd',
         pay_options: 'btc, eth',
         description: 'Black pair of shoes',
         public_key: 'RQPUBK-xsk8cedf4kxakzrur9c8kkicbf6qiz',
         customer: 'lite2fine@gmail.com',
         return_url: 'https://roqqu.com/transaction/verify'
     });
     handler.load();
  }
  ```
  
 <!--END_DOCUSAURUS_CODE_TABS-->
 
 ### Configuration Options
 '*' indicates required parameters.
 | Option |      Description      |
 |----------|-------------|
 | <code>amount *</code> |  Amount in USD or NGN up to 2 decimal places. |
 | <code>currency</code> |    Currency charge should be performed in NGN or USD. Default is NGN   |
 | <code>public_key *</code> | This is your business public key as found on your Roqqu business account on your dashboard |
 | <code>customer *</code> | This is the email of your customer |
 | <code>description</code> | An explanation of what the charge is for |
 | <code>return_url</code> | URL to be redirected to after charge is complete (transaction reference will be sent to this URL as <code>GET</code> parameter) |
 | <code>pay_options</code> | The tokens you want to accept separated by comma, default is all |
 
 ### Step 4 - Setting the trigger button
 Next you'll need to attach the Javascript function to a button
 that will trigger the payment page.
 
 <!--DOCUSAURUS_CODE_TABS-->
   <!--HTML-->
   
   ```html
   <button onclick="payWithRoqqu()">Pay now</button>
   ```
   
  <!--END_DOCUSAURUS_CODE_TABS-->
  
  If you have done everything correctly, clicking the button
  should initialize the payment page based on the parameters
  you set during initialization.