# Project - Shopping_List

This is the Shopping List Projet ---->

In BackEnd ---
1. I have created 2 model's one for product and other for product's in List.
2. Created create , get , update api for product 
3. Created update , get , delete api's for list

In FrontEnd ---
1. The User will see the 2 DropDown's one for Fruits and Other for Vegetables 
2. User can select any one item/product to see it's details after that we can add change it's price to dollar also
3. After that we can increase or decrease the quantity and add it to the shopping list.
4. And we have button to see the shopping list.

### Models`
- Cart Model

```yaml
{ 
  name: {string, mandatory},
  category: {string, mandatory},
currencyFormat: {string, enum:[₹,$]}, 
  price: {Number, mandatory},
  totalPrice: {Number},
  totalQuntity:{Number},
  image:{type:String},
  isDeleted: {boolean, default: false},
  createdAt: {timestamp},
  updatedAt: {timestamp}
}
```

## cart API
### POST /CreateCart
- Create a cart document from request body. Get product details in request body only.
- Return HTTP status 201 on a succesful cart creation. Also return the cart document. The response should be a JSON object 
- Return HTTP status 400 for an invalid request with a response body 

### GET /getCart
- Returns cart in the collection that aren't deleted,
- Return the HTTP status 200 if any documents are found,
- If no documents are found then return an HTTP status 404 

### PUT /updateItems
- Update a cart by changing its
  - name
  - category
  - totalQuntity
  - totalPrice
- Make sure the unique constraints are not violated when making the update
- Check if the cart exists. If it doesn't, return an HTTP status 404 with a response body like [this]
- Return an HTTP status 200 if updated successfully with a body like
- Also make sure in the response you return the updated cart document. 

### DELETE /RemoveCart
- Check if the cart exists and is not deleted. If it does, mark it deleted and return an HTTP status 200 with a response body with status and message.
- If the cart document doesn't exist then return an HTTP status of 404 with a body like [this]
