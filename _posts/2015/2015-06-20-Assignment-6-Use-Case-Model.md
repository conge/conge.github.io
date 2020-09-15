---
layout: post
title: "Assignment 6 Use Case Model"
date: "2015-06-20 07:38:25"
categories: 计算机科学
excerpt: "Use Case Model Author: 1 Use Case Diagram This is a use case diagram of ..."
auth: conge
---
* content
{:toc}

# Use Case Model


**Author**:  \<Qingyang Li\>

## 1 Use Case Diagram

**This is a use case diagram of the EZShop system with all the actors and use cases for the system**
 
![UseCaseUml_TopLevel_small.png](/assets/images/计算机科学/118382-424bbbcd9c6f3373.png))


## 2 Use Case Descriptions

There are two subtype of user actor for the EZShop system (the app), one is customer and the other is cashier. Customer uses the system to login, manage the itemlist in the shopping cart, generate QR Code for checking out. and the cashier helps the customer interacting with the payment subsystem of the EZshop system at the checkout point. The cashier can update the shopping cart when necessary. Only cashiers can process payment.

The use cases are listed below.

| ID    | Use Case Name       | Primary actor    |
|:------|:-------------------:| :---------------:|
| 1     | user authentication | Customer/Cashier |
| 2     | shopping            | Customer       |
| 3     | view shopping cart  | Customer/Cashier |
| 4     | add item            | Customer/Cashier |
| 5     | remove item         | Customer/Cashier |
| 6     | add coupon          | Customer/Cashier |
| 7     | remove coupon       | Customer/Cashier |
| 8     | check out           | Customer/Cashier |
| 9     | payment             | Cashier          |

### 1. User authentication

- *Requirements: existing QR code to login to the system*
- *Pre-conditions: Valid user QR code*
- *Post-conditions: Valid user information created, the shopping App launched*
- *Scenarios: User Launch the QR code scanner; Read the customer card’s QR code; Suitably initialize the customer’s information based on the information read; The shopping App will be launched if the user is a customer; the payment subsystem will be launched if the user is a cashier.*

### 2. Shopping

- *Requirements: customer launches the shopping mode UI by scanning an existing QR code ID.*
- *Pre-conditions: Valid user information (first name, last name, Zip code, email address), no shopping cart exists*
- *Post-conditions: A shopping cart initialized with an empty Item list*
- *Scenarios: The system goes back to " User authentication" if valid user info is not available; The system will go to the next use case "view shopping cart" if there is already an shopping cart existed and a valid user is presented; if there is valid user info but no shopping cart, a new shopping cart will be initialized with an empty item list in it.*

### 3. view shopping cart

- *Requirements: user can browse the item list in the shopping cart. User can start to add/remove item/coupon here*
- *Pre-conditions: existing shopping cart*
- *Post-conditions: None*
- *Scenarios: A customer or a cashier views the shopping cart to go over and confirm the item list matches what the customer is buying. If a mismatch is identified, the customer or cashier can take action to update the shopping cart by call use case of adding/removing items/coupon.*

### 4. add item

- *Requirements: user adds an item to the item list in the shopping cart by scanning the QR code of the item*
- *Pre-conditions: Valid item QR code, existing shopping cart*
- *Post-conditions: item list updated with the new item*
- *Scenarios: customer can add item when in shopping mode; cashier can add item at the checkout if the customer failed to add the item to the shopping cart. Optionally, user can provide the number items to be added to the item list to save some scanning time.*

### 5. remove item

- *Requirements: user removes an item from the item list in the shopping cart by scanning the QR code of the item*
- *Pre-conditions: Valid item QR code, existing non-empty shopping cart, item is in the item list*
- *Post-conditions: item list updated with the item removed*
- *Scenarios: customer can remove item when in shopping mode; cashier can remove item at the checkout if the customer failed to remove the item to the shopping cart or wanted to return the item before checkout. Optionally, user can provide the number items to be removed from the list to save some scanning time. In this case, the number provided must be no larger than the number of items in the system, otherwise an error message will pop up and the system will cancel this action and return to its previous state.*

### 6. add coupon

- *Requirements: user adds an coupon to the item list in the shopping cart by scanning the QR code of the coupon*
- *Pre-conditions: Valid coupon QR code, existing shopping cart*
- *Post-conditions: coupon list updated with the new coupon*
- *Scenarios: customer can add coupon when in shopping mode or s/he can hand the coupon to a cashier. Cashier can add coupon at the checkout. The operation will success when all pre-conditions are met. The item list will not update when the coupon is invalid, the corresponding item is not in the shopping cart or the shopping cart is empty*

### 7. remove coupon

- *Requirements: user adds an item to the item list in the shopping cart by scanning the QR code of the item*
- *Pre-conditions: Valid coupon QR code, existing shopping cart, the coupon is on the list of the shopping cart*
- *Post-conditions: coupon list updated with the coupon removed*
- *Scenarios: customer can remove coupon in shopping mode when s/he removes the corresponding item of the coupon; cashier can remove coupon at the checkout when the customer returned the corresponding item. When the coupon is not in the shopping cart, the system should provide error message to notify the users.*

### 8. check out

- *Requirements: When the customer finishes shopping, the system takes the user information, shopping cart information, price, taxes and generate a QR code to use at checkout*
- *Pre-conditions: valid customer information, items and coupons lists*
- *Post-conditions: QR code which encodes customer information, items and coupons lists, the total value of the cart, computed from the items in the items list and the coupons in the coupons list with taxes applied.*
- *Scenarios: A customer can press the “Pay” button on the app’s screen to finishes shopping and the app will generate a __payment QR code__ that encodes (1) the customer’s information, (2) the items and coupons lists, and (3) the total value of the cart, computed taking into account the items in the items list (including whether they are alcoholic beverages or not) and the coupons in the coupons list.*

### 9. payment

- *Requirements: The cashier will scan the payment QR code generated by the customer and retrieve all the information it encoded (customer information, items list, coupons list, total value of the cart). The cashier then confirms the information against what the customer has. Then the cashier will process the payment.*
- *Pre-conditions: valid payment QR code.*
- *Post-conditions: None*
- *Scenarios: Cashier can check items and coupons in customer's basket against the list of the items and coupons in the system. If there is any mistake or mismatch, cashier can correct it by editing the shopping cart. If everything is OK, cashier can take payment by credit or check which will use credit payment service and check payment service, respectively. If the customer chooses to pay in cash, the cashier can handle the transaction without further interaction with the system.*
