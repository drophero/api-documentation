Order Management
================

This interface will allow you to send your app orders and keep these in sync with his Status on DropHero.

**Be careful, by sending orders to DropHero we will retire the proper amount of money from your account, so be sure you have taken the money or you are sure you will be paid.**

## Sending Orders

- <code>POST /v1/orders/new</code> send orders to DropHero to process. This JSON data must be serialized and attached to the request into a new variable called <code>data</code>.

```JSON
{
	"100000001":{
		"idordershop":"100000001",
		"status":"1","2","3","4",
		"buyer_name":" ",
		"buyer_address":"sin calle",
		"buyer_postcode":"08080",
		"buyer_city":"sin ciudad",
		"buyer_country":"ES",
		"buyer_phone":"93888555222",
		"buyer_message":"",
		"buyer_vatin":"",
		"buyer_shipping_name":"",
		"buyer_shipping_address":"",
		"buyer_shipping_postcode":"",
		"buyer_shipping_city":"",
		"buyer_shipping_country":"",
		"buyer_shipping_phone":"",
		"shipping_price":"5.0000",
		"currency":"EUR",
		"order_total":"25.7800",
		"selled_items":{
			"5":{
				"iditem":"5554",
				"qty":"1.0000",
				"row_total":"17.1700",
				"row_total_incl_tax":"20.7800",
				"item_selling_price":"17.1700",
				"item_selling_discount":"0.0000",
				"item_selling_tax":"21.0000", 
				"idshippingmode":"1",
				"item_tax_amount":"3.6100"
				}
		}
	}
}
```

| field                    | Description  |  Included in bill printing   |  Control      |
| ------------------------ | -------------| -------------| -------------|
| idordershop              | Your own id for this order     | No | Required     |
| status                   | Regular status (see table below)     | No | Required     |
| buyer_name               | Buyer name for this order     | Yes | Required     |
| buyer_address            | Buyer address for this order (will be used as shipping address)      | Yes | Required     |
| buyer_postcode           | Buyer postcode      | Yes | Required     |
| buyer_city               | Buyer city      | Yes | Required     |
| buyer_country            | Buyer country     | Yes | Required     |
| buyer_phone              | Buyer phone      | Yes |      |
| buyer_message            | Buyer related messages for preparation and shipping purposes     | No |      |
| buyer_vatin            | Buyer tax id (card id), spanish nif...     | Yes |   Required   |
| buyer_shipping_name               | Buyer shipping name for this order     | Yes | Required     |
| buyer_shipping_address            | Buyer shipping address for this order      | Yes | Required     |
| buyer_shipping_postcode           | Buyer shipping postcode     | Yes | Required     |
| buyer_shipping_city               | Buyer shipping city     | Yes | Required     |
| buyer_shipping_country            | Buyer shipping country     | Yes | Required     |
| buyer_shipping_phone              | Buyer phone      | Yes |      |
| shipping_price           | The shipping price you're charging to this client     | Yes | Required     |
| currency                 | ISO 4217 currency name (EUR, USD, GBP...)    | Yes | Required     |
| order_total              | The total order amount you're charging to this client  | Yes | Required     |

| selled_items                    | Description  | Included in bill printing   |  Control      |
| ------------------------ | -------------| -------------| -------------|
| iditem                   | iditem from local DropHero subscription    | No | Required     |
| qty                      | Qty of this product     | Yes | Required     |
| row_total                | Total price for this qty of item (without taxes)  | Yes | Required     |
| row_total_incl_tax       | Total price for this qty of item (with taxes)     | Yes | Required     |
| item_selling_price       | Price for 1 unit of this product     | Yes | Required     |
| item_selling_discount    | Discount applied to this product     | Yes | Required     |
| item_selling_tax         | Percentage amount of tax applied to this product     | Yes | Required     |
| item_tax_amount          | Amount of tax applied to this product      | Yes | Required     |
| idshippingmode           | Shipping mode picked by the buyer in your app    | No | Required     |

## Get order status

- <code>GET /v1/orders</code> will return current order status for all orders related to requester account.

## Get specific order status

- <code>GET /v1/orders/idordershop</code> will return current order status a given idordershop.

Order status:

| status   | Description              |
| -------: | ------------------------ |
| 1        | Processing order         |
| 2        | Cancelled                |
| 3        | Partially sent           |
| 4        | Sended (Fully processed) |

