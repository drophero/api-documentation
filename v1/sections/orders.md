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
		"status":”1”,”2”,”3”,”4”,
		"buyer_name":" ",
		"buyer_address":"sin calle",
		"buyer_postcode":"08080",
		"buyer_city":"sin ciudad",
		"buyer_country":"ES",
		"buyer_phone":"93888555222",
		"buyer_message":"",
		"shipping_price":"5.0000",
		"currency":"EUR",
		"order_total":”25.7800”,
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
| status                   | Regular status (see table above)     | No | Required     |
| buyer_name               | Buyer name for this order     | Yes | Required     |
| buyer_address            | Buyer address for this order (will be used as shipping address)      | Yes | Required     |
| buyer_postcode           | Buyer postcode (will be used as shipping postcode)     | Yes | Required     |
| buyer_city               | Buyer city (will be used as shipping postcode)     | Yes | Required     |
| buyer_country            | Buyer country (will be used as shipping postcode)     | Yes | Required     |
| buyer_phone              | Buyer phone (will be used as shipping contact phone)     | Yes |      |
| buyer_message            | Buyer related messages for preparation and shipping purposes     | No |      |
| shipping_price           | The shipping price you're charging to this client     | Yes | Required     |
| currency                 | EUR or DLR     | Yes | Required     |
| order_total              | The total order amount you're charging to this client  | Yes | Required     |

| selled_items                    | Description  | Included in bill printing   |  Control      |
| ------------------------ | -------------| -------------| -------------|
| iditem                   | Required     | No | Required     |
| qty                      | Required     | Yes | Required     |
| row_total                | Required     | Yes | Required     |
| row_total_incl_tax       | Required     | Yes | Required     |
| item_selling_price       | Required     | Yes | Required     |
| item_selling_discount    | Required     | Yes | Required     |
| item_selling_tax         | Required     | Yes | Required     |
| item_tax_amount          | Required     | Yes | Required     |
| idshippingmode           | Required     | No | Required     |


## Deleting Categories

- <code>POST /v1/category/del</code> will return all current subscriptions and deleted subscriptions related to requester account.

This JSON data must be serialized and attached to the request into a new variable called <code>data</code>.

```JSON
{
	"2":{"id":"2"},
	"5":{"id":"5"},
	"6":{"id":"6"},
	"7":{"id":"7"},
	"8":{"id":"8"},
	"9":{"id":"9"},
	"10":{"id":"10"}
}
```

| field                    | Description  |
| ------------------------ | -------------|
| id                       | Required     |