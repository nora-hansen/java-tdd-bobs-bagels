# Bob's Bagels Domain Model

````dtd
1.
As a member of the public,
So I can order a bagel before work,
I'd like to add a specific type of bagel to my basket.
````

| Classes | Methods                  | Member Variables         | Scenario                  | Results/Output                                                                           |
|---------|--------------------------|--------------------------|---------------------------|------------------------------------------------------------------------------------------|
| Basket  | addToBasket(String type) | ArrayList<String> basket | Bagel type exists         | Bagel is added to list, message "Successfully added to basket" is displayed. Return true |
|         |                          |                          | Bagel type does not exist | An error message is displayed, e.g. "Bagel type does not exist". Return false            |
|         |                          |                          |                           |                                                                                          |


````dtd
2.
As a member of the public,
So I can change my order,
I'd like to remove a bagel from my basket.
````

| Classes | Methods                       | Member Variables         | Scenario                    | Results/Output                                                                                   |
|---------|-------------------------------|--------------------------|-----------------------------|--------------------------------------------------------------------------------------------------|
| Basket  | removeFromBasket(String type) | ArrayList<String> basket | Bagel type is in basket     | Bagel is removed from list, message "Successfully removed from basket" is displayed. Return true |
|         |                               |                          | Bagel type is not in basket | An error message is displayed, e.g. "Bagel type is not in basket". Return false                  |


````dtd
3.
As a member of the public,
So that I can not overfill my small bagel basket
I'd like to know when my basket is full when I try adding an item beyond my basket capacity.
````

max (Int, max amount of items allowed in a basket)

| Classes | Methods                  | Member Variables         | Scenario           | Results/Output                                                     |
|---------|--------------------------|--------------------------|--------------------|--------------------------------------------------------------------|
| Basket  | addToBasket(String type) | ArrayList<String> basket | Basket is full     | Do not add bagel, display message which should be "Basket is full" |
|         |                          | String message           | Basket is not full | Add bagel like normal. message is "Successfully added to basket"    |

````dtd
4.
As a Bob's Bagels manager,
So that I can expand my business,
I’d like to change the capacity of baskets.
````

| Classes | Methods                            | Member Variables | Scenario      | Results/Output                                                |
|---------|------------------------------------|------------------|---------------|---------------------------------------------------------------|
| Basket  | changeBasketCapacity(int capacity) | int max          | Capacity > 0  | Change value of max                                           |
|         |                                    |                  | Capacity == 0 | Ask manager if they want capacity to be 0, allowing no items. |
|         |                                    |                  | Capacity < 0  | Display error message "Basket capacity cannot be negative"    |

````dtd
5.
As a member of the public
So that I can maintain my sanity
I'd like to know if I try to remove an item that doesn't exist in my basket.
````

| Classes | Methods                      | Member Variables         | Scenario               | Results/Output                                 |
|---------|------------------------------|--------------------------|------------------------|------------------------------------------------|
| Basket  | removeFromBasket(String type | ArrayList<String> basket | Bagel is not in basket | Display message to user "Bagel does not exist" |
|         |                              |                          | Bagel is in basket     | Remove bagel                                   |

````dtd
6.
As a member of the public, 
To keep track of my actions,
I'd like to see the items I currently have in my basket
````

| Classes | Methods         | Member Variables         | Scenario         | Results/Output                           |
|---------|-----------------|--------------------------|------------------|------------------------------------------|
| Basket  | listBasketItems | ArrayList<String> basket | Basket size > 0  | Items are listed.                        |
|         |                 |                          | Basket size == 0 | "No items, basket empty"                 |
|         |                 |                          | Basket < 0       | "Error: Basket size is negative \(how?)" |

````dtd
7.
As a member of the public,
So that I don't feel like I have to commit,
I'd like to empty my basket of all its items at once
````

| Classes | Methods       | Member Variables         | Scenario         | Results(Output                                                                      |
|---------|---------------|--------------------------|------------------|-------------------------------------------------------------------------------------|
| Basket  | emptyBasket() | ArrayList<String> basket | Basket size > 0  | Basket size is now 0; A message is displayed to inform the user. Return true;       |
|         |               |                          | Basket size == 0 | Basket is not emptied since it is empty. Message is displayed to user. Return false |

````dtd
8.
As a member of the public,
So I don't get confused,
I'd like to see Bob's Bagels' contact information
````

| Classes | Methods                       | Member Variables                               | Scenario                  | Results/Outputs                                       |
|---------|-------------------------------|------------------------------------------------|---------------------------|-------------------------------------------------------|
| Basket  | getContactInfo(String option) | String email<br/>Int number<br/>String address | option is "e-mail         | Bob's Bagels' e-mail is showed and nothing else       |
|         |                               |                                                | option is number          | Bob's Bagels' phone number is showed and nothing else |
|         |                               |                                                | option is address         | Bob's Bagels' address is showed and nothing else      |
|         |                               |                                                | option is an empty string | All of Bob's Bagels' contact information is displayed |
