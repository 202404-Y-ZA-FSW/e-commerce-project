# Mini Project: E-commerce API

## Instructions

### Collaboration requirements

Please don't split the code. Write every line of code together. In each group, every person should understand every line of code.

### Overview

In this project, you will be using Node, Express, MongoDB and Mongoose in order to create an e-commerce backend app. This app will have 2 types of users: admins of the shop and customers.

We will work through this project in versions. these versions will be as following:
1. E-commerce admin features
2. Customer features
3. Authentication
4. Tests
5. Deployment

We may add or remove few versions as we progress through the project during the bootcamp.

### Functional requirements

The requirements will update in each version and you will add to the work you did the in previous version so make sure you write clean code, also, this is why you see requirements titled as Version N.

**Attention**: All types of validation and error handling should be taken in-consideration in all requests.

#### Version 1 Requirements
In this version we will make sure everything is setup and working from the database to Express server and their connection. Then we will start working on all the admin features and requirements as following:
- First of all, you need to define your `shop-item` schema, it should at least have these fields (the data types and other validation criterias will be left for you to decide on):
  - title
  - image
  - price
  - description
  - availableCount
  - genre or category

Now, after setting up the model, let's start working on the requests.

_Note: admin routes start with `/admin`._

- The admin should be able to add new shop items.
- The admin should be able to update the details of a shop item, such as description, price, available count, etc.
- The admin should be able to delete one or more items from the items list.
- The admin should be able to search for shop items based on different properties.

#### Version 2 Requirements
Having the project running and admin being able to play around with the shop items, it is time to add the customer features.

Customer routes start with _`/customer`_.

**Note**: _Continue working on the same project. Please don't create a new repo or project and copy all your work from v1 to the new project. Work on the same codebase from v1._

Requirements are:
- Customer is able to get all shop items and filter according to category and price range (for example, items that range in price from 10$ to 50$).
- Customer should be able to search for items.
- A customer is able to add an item to their cart, by sending a request to `/cart` with the customer ID, item ID and quantity requested. Make sure you check there are enough or remaining items in the inventory before adding to the cart. Adding to cart should also decrement the quantity in the shop items inventory.
- After the customer has added items to their cart, they will need to checkout and order, so create a request to the endpoint `/checkout` where you will need to calculate the bill for all the items in the cart and create an `order` object with all order items and bill total and return it to the customer. The cart for that customer should be empty after they order.
- Customer should be able to get the information of a single item.

Model requirements:
- For these operations, you will need to define a new model for the `customer`.
- And another one for the `cart`. The `cart` can be embedded or referenced inside the `customer` model.
- You will also need to define another new model for the customer orders, let's call it `order`. We will have all the customer orders in there after they checkout.

**Note**: _You can create a few dummy records on your customers collection to test out your API routes. Once we implement authentication in an upcoming version, we will use the customer data created after signup/signin. Each customer can have id, name, gender, ..._
