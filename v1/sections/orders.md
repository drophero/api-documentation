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

| field                    | Description  | Control      |
| ------------------------ | -------------| -------------|
| idordershop              | Required     | Required     |
| status                   | Required     | Required     |
| buyer_name               | Required     | Required     |
| buyer_address            | Required     | Required     |
| buyer_postcode           | Required     | Required     |
| buyer_city               | Required     | Required     |
| buyer_country            | Required     | Required     |
| buyer_phone              | Required     |      |
| buyer_message            | Required     |      |
| shipping_price           | Required     | Required     |
| currency                 | Required     | Required     |
| order_total              | Required     | Required     |
| selled_items             | Required     | Required     |

| selled_items                    | Description  | Control      |
| ------------------------ | -------------| -------------|
| iditem                   | Required     | Required     |
| qty                      | Required     | Required     |
| row_total                | Required     | Required     |
| row_total_incl_tax       | Required     | Required     |
| item_selling_price       | Required     | Required     |
| item_selling_discount    | Required     | Required     |
| item_selling_tax         | Required     | Required     |
| idshippingmode           | Required     | Required     |
| item_tax_amount          | Required     | Required     |

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