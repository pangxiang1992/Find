# Track E-Commerce Activity

TongDao makes it easy to analyze the revenue you make from individual customers. By tracking user e-commerce activity, you can compare revenue across different customer segments and calculate customer lifetime value.

## Track a Simple Order
```java
String name = "VIP Package";
float price = 10.0f;
Currency currency = Currency.getInstance("CNY");
 
tongDao.trackPlaceOrder(name, price, currency);
```
<br>
## Track an Order with Quantity
```java
String name = "Month plan";
float price = 5.0f;
Currency currency = Currency.getInstance("CNY");
int quantity = 2;
 
tongDao.trackPlaceOrder(name, price, currency, quantity);
```
<br>
## Track an Order with Multiple Products and Quantities
```java
TdProduct product = new TdProduct();
product.setName("E-reader");
product.setPrice(100.0f);
 
TdOrderLine orderLine = new TdOrderLine();
orderLine.setProduct(product);
orderLine.setQuantity(2);
 
ArrayList<TdOrderLine> orderLines = new ArrayList<TdOrderLine>();
orderLines.add(orderLine);
 
TdOrder order = new TdOrder();
order.setCurrency(Currency.getInstance("CNY"));
order.setOrderId("abcdef");
order.setTotal(200.0f);
order.setOrderLines(orderLines);
tongDao.trackPlaceOrder(order);
```
<!-- 
<br>
## Track the View of a Product Category
```java
String category = "electronics";
tongDao.trackViewProductCategory(category);
```
<br>
## Track the View of a Product
```java
TdProduct product = new TdProduct();
product.setName("E-reader");
product.setPrice(100.0f);
tongDao.trackViewProduct(product);
```
 -->
<!-- 
<br>
## Track Adding a Product to the Cart
```java
Currency currency = Currency.getInstance("CNY");
TdProduct product = new TdProduct();
product.setName("E-reader");
product.setPrice(100.0f);
product.setCurrency(currency);
 
TdOrderLine orderLine = new TdOrderLine();
orderLine.setProduct(product);
orderLine.setQuantity(2);
 
// Track one order line
tongDao.trackAddCart(orderLine);
 
// Or track multiple
ArrayList<TdOrderLine> orderLines = new ArrayList<TdOrderLine>();
orderLines.add(orderLine);
tongDao.trackAddCart(orderLines);
```
<br>
## Track Removing a Product from a Cart
```java
Currency currency = Currency.getInstance("CNY");
TdProduct product = new TdProduct();
product.setName("E-reader");
product.setPrice(100.0f);
product.setCurrency(currency);
 
TdOrderLine orderLine = new TdOrderLine();
orderLine.setProduct(product1);
orderLine.setQuantity(2);
 
// Track one order line
tongDao.trackRemoveCart(orderLine);
 
// Or track multiple
ArrayList<TdOrderLine> orderLines = new ArrayList<TdOrderLine>();
orderLines.add(orderLine);
tongDao.trackRemoveCart(orderLines);
```
 -->