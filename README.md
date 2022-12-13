# Welcome PayFabric Partners! 

This is an overview of EVO’s payment engine, PayFabric, as well as an outline of basic partner usage and implementation steps designed to provide the fastest route to market.


# [PayFabric®](https://github.com/PayFabric/Portal/tree/master/PayFabric) 

PayFabric Support can assist with create a PayFabric account with partner portal access. All the partner needs to do is activate their PayFabric account & set their preferred password. Please reach out to support@payfabric.com in order to have partner access provisioned. 

# PayFabric Partner Portal

•	The PayFabric Partner Portal provides ability to manage and control all aspects of its merchants, including Configurations, as well as Device credentials to gain API access.

•	The partner controls Configuration profiles, which dictates the settings on all merchants.

 [PayFabric Partner Portal User Guide](https://github.com/RJ-Washington/PayFabric-Partners/files/10178567/PayFabric-Partner-Guide.docx)
 

# New Merchants

•	Each new merchant will inherit settings from the partners Configuration profile.

•	**Each merchant is required to have their own [Device credentials](https://www.payfabric.com/API/Help/Api/POST-Merchant-merchantId-Device) for accessing the merchant’s account via APIs.**

•	Technical Documentation: [API Authentication](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Authentication.md) 

# Implementation

•	**Payment Wallets**

o	Each wallet record (credit card or bank account) is stored under a Customer Number unique to the merchant.

o	Full Wallet APIs are available to obtain a list of wallet records (so you don’t have to store them) as well as removal.

o	Technical Documentation: [Credit Card / eCheck Wallet](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Wallets.md#credit-card--echeck-wallet)

•	**Payment Intent**

o	First create a Transaction record as an intent to process a payment, optionally (but recommended) to include [Level II & Level III](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Level%202%20and%20Level%203%20Fields.md) transaction data for B2B payments.

o	The payment intent (Transaction record) can be processed using different methods.

o	Technical Documentation: [Create a Transaction](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#create-a-transaction)

•	**Processing using Payment API**

o	The Payment API can be used to process a Transaction with an existing saved wallet.

o	Include the Card object along with the ID for the wallet record when you create the Transaction, then invoke the “/transaction/process” API to process payment.

o	Technical Documentation: [Process a Transaction](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Transactions.md#process-a-transaction)

•	**Processing using Hosted Page**

o	While PayFabric offers different hosted pages, EVO recommends the Mobile Responsive Hosted Payment Page (MRHPP) – to be confirmed after more in-depth design meeting with your development team.
 
o	The MRHPP is loaded into an iFrame through our JavaScript SDK.  It offers “Save for later use” to meet compliance (only save when needed), as well as alternative payments such as Google Pay and Apple Pay.

o	Submitting the form will initiate payment processing.

o	Technical Documentation: [JavaScript SDK](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/JavaScript%20SDK.md)
![MRHPP](https://user-images.githubusercontent.com/109090573/206205716-5725007b-10a2-4b26-a65e-334d96b9a89b.png)
•	**Styling and Full Control Over Hosted Pages**

o	As part of the Configuration settings, a Theme can be used to insert your own CSS and JavaScript to give you full control over the hosted page even when it’s embedded in an iFrame.

o	Possible use case includes hiding the form submission button from the hosted page and control form submission from your own page.

o	Technical Documentation: [Themes](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Themes.md)
![Themes](https://user-images.githubusercontent.com/109090573/206207176-c98b4941-c084-4615-b454-0de25fed8aab.png)

