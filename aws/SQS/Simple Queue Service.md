**Amazon Simple Queue Service (Amazon SQS)** is a message queuing service. 

Using Amazon SQS, you can send, store, and receive messages between software components, without losing messages or requiring other services to be available. In Amazon SQS, an application sends messages into a queue. A user or service retrieves a message from the queue, processes it, and then deletes it from the queue.

### **Example: Fulfilling an order**

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/y8UXj-I9TSCFF4_iPa0gPw_57c347cc1e3d432b8553665d9bc49150_SQS_1.png?expiry=1611446400000&hmac=sygxCGWyyt28kVp_FelFCAY2Gezb5NWFKhWsOjhceJ8)

Suppose that the coffee shop has an ordering process in which a cashier takes orders, and a barista makes the orders. Think of the cashier and the barista as two separate components of an application. 

First, the cashier takes an order and writes it down on a piece of paper. Next, the cashier delivers the paper to the barista. Finally, the barista makes the drink and gives it to the customer.

When the next order comes in, the process repeats. This process runs smoothly as long as both the cashier and the barista are coordinated.

What might happen if the cashier took an order and went to deliver it to the barista, but the barista was out on a break or busy with another order? The cashier would need to wait until the barista is ready to accept the order. This would cause delays in the ordering process and require customers to wait longer to receive their orders.

As the coffee shop has become more popular and the ordering line is moving more slowly, the owners notice that the current ordering process is time consuming and inefficient. They decide to try a different approach that uses a queue.

### **Example: Orders in a queue**

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/j4F0N9soTamBdDfbKB2pXQ_d4548eb733f24c7f89fa1256637d0da6_SQS_2.jpg?expiry=1611446400000&hmac=cAEEbeu4NO5svgt3-IAF310A4z7lrE6rknWPd9d6Dy8)

Recall that the cashier and the barista are two separate components of an application. A message queuing service such as Amazon SQS enables messages between decoupled application complements.

In this example, the first step in the process remains the same as before: a customer places an order with the cashier. 

The cashier puts the order into a queue. You can think of this as an order board that serves as a buffer between the cashier and the barista. Even if the barista is out on a break or busy with another order, the cashier can continue placing new orders into the queue. 

Next, the barista checks the queue and retrieves the order.

The barista prepares the drink and gives it to the customer. 

The barista then removes the completed order from the queue. 

While the barista is preparing the drink, the cashier is able to continue taking new orders and add them to the queue.