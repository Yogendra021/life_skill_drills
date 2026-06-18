# What is Apache kafka

Apache Kafka is a distributed, fault-tolerant, horizontally scalable event streaming platform.

In simple terms, Apcahe kafka is centralized system for parallel processing and distribution of event or messages.

### Where it is helpful in our business ?

Let suppose in our business a user have placed order and after placing the order we are required to do these things listed below :
* Save Order
* Send Email
* Update Inventory
* Generate Invoice
* Update Analytics

All of these at the same time and if we will try it do normally in our current Node.js backend system we have to do something like as folows:

* createOrder();
* sendEmail();
* updateInventory();
* generateInvoice();
* updateAnalytics();

So, here you can see like this code will execute synchronously one by one and if any process is slow the processes after it will also get delayed and here the Apache kafka comes into the picture and introduces ***decoupling***. 

Now we just have to run one single command due to apache kafka:
* OrderCreated();

and it will notify about event by user to all other respective services like save order, send email, update inventory, Generate invoice and Update analystics parallely.



## What is actually sent?

### Same JSON.

#### Without Kafka:

* {
  "orderId": 101
}

#### With Kafka:

* {
  "eventType": "OrderCreated",
  "orderId": 101
}  

The difference is not the message.

The difference is who owns delivery and distribution.

Apache also best at recovering the all past events and save all of them , so if any chance we need to check the past event by users or our service get down Apache will automatically handles it and continue from where it stopped previously.

---

#### Official Documentation of Apache kafka :
<https://kafka.apache.org/43/getting-started/introduction/>