# Sequence Diagram Walkthrough: Ecommerce System

## 📋 Problem Statement

> Ecommerce has been booming in Bangladesh, and especially with the pandemic, the demand for it has exponentially increased. A general case ecommerce runs as follows:
> 1. After a customer visits the site, they search for a product by typing its name, which is passed to the SearchEngine
> 2. The SearchEngine then fetches the products from the ProductsDatabase and serializes them in accordance with the relevance of the searched keywords and returns them to the customer
> 3. The customer selects an item which takes the user to the ProductPage
> 4. From the ProductPage, the customer adds the item to their cart which sends a request to the CustomerCart
> 5. After receiving the request, CustomerCart sends a request to the ProductsDatabase to check if the item is in stock, if the item is in stock, the product gets added to the CustomerCart otherwise an error is shown
> 6. Finally, the customer selects to check out, which sends a request to the CartCheckout where the customer has to enter their full name, email address, phone number and delivery address
> 7. If all the information has been entered correctly, a success message is shown, otherwise an error message is shown
>
> *Draw the sequence diagram for the above scenario.*

---


## Step 1: Identify the Objects
Based on the scenario, the entities are:
- **Customer**: The user of the site.
- **SearchEngine**: Handles finding products.
- **ProductsDatabase**: The data storage for products and stock.
- **ProductPage**: The interface for viewing a specific product.
- **CustomerCart**: Manages the items the user wants to buy.
- **CartCheckout**: Handles the final purchase process.

## Step 2: Trace the Messages
- Customer types product name -> SearchEngine
- SearchEngine fetches products from ProductsDatabase
- ProductsDatabase returns sorted products to SearchEngine
- SearchEngine shows products to Customer
- Customer selects item -> ProductPage
- Customer adds item to cart -> CustomerCart
- CustomerCart checks stock directly with ProductsDatabase
- CustomerCart shows success/error to Customer
- Customer enters info for checkout -> CartCheckout
- CartCheckout validates info and shows success/error to Customer

## Step 3: Spot the Fragments
- **`alt` for stock check**: When the `CustomerCart` requests a stock check from the `ProductsDatabase`, the outcome determines the next steps (in stock vs not in stock).
- **`alt` for checkout validation**: When the customer checks out, the entered information can be correct or incorrect, leading to a success or error message.

## Step 4: The Complete Diagram

```mermaid
sequenceDiagram
    actor Customer
    participant SearchEngine
    participant ProductsDatabase
    participant ProductPage
    participant CustomerCart
    participant CartCheckout

    Customer->>SearchEngine: searchProduct(name)
    SearchEngine->>ProductsDatabase: fetchProducts(keywords)
    ProductsDatabase-->>SearchEngine: returnSortedProducts()
    SearchEngine-->>Customer: displayProducts()
    
    Customer->>ProductPage: selectItem()
    
    Customer->>CustomerCart: addToCart(item)
    CustomerCart->>ProductsDatabase: checkStock(item)
    
    alt in stock
        ProductsDatabase-->>CustomerCart: stockAvailable
        CustomerCart-->>Customer: showSuccessMessage()
    else not in stock
        ProductsDatabase-->>CustomerCart: outOfStock
        CustomerCart-->>Customer: showErrorMessage()
    end
    
    Customer->>CartCheckout: checkout(fullName, email, phone, address)
    
    alt information entered correctly
        CartCheckout-->>Customer: showSuccessMessage()
    else information entered incorrectly
        CartCheckout-->>Customer: showErrorMessage()
    end
```

## Step 5: Self-Check
- [ ] Did I show the standard request-response flow for the search?
- [ ] Did I include the direct communication between `CustomerCart` and `ProductsDatabase` without routing it through the user?
- [ ] Did I use an `alt` block for the stock checking logic?
- [ ] Did I use an `alt` block for the final checkout validation?
