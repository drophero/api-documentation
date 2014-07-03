Categories Management
=====================

Here you'll find all API functions related to Category syncing between DropHero and any client app. This methods allow you to keep DropHero in sync with your app every time.

## Sending Categories

Any update on existing categories will rewrite the previous data on DropHero.

- <code>POST /v1/category/new</code> upload categories to DropHero. This JSON data must be serialized and attached to the request into a new variable called <code>data</code>.

Here you send your internal <code>id</code> for every catagory you have, as well as his name and his parent_id in order to indent them properly.

```JSON
{
	"2":{
		"id":"2","name":"Default Category","parent_id":1
		},
	"5":{
		"id":"5","name":"Botas","parent_id":4
		},
	"6":{
		"id":"6","name":"Zapatos","parent_id":4
		},
	"7":{
		"id":"7","name":"Camisas","parent_id":3
		},
	"8":{
		"id":"8","name":"Camisetas","parent_id":3
		},
	"9":{
		"id":"9","name":"Ropa interior femenina","parent_id":3
		},
	"10":{
		"id":"10","name":"Bragas","parent_id":9
		}
}
```

| field                    | Description  |
| ------------------------ | -------------|
| id                       | Required     |
| name                     | Required     |
| parent_id                | Required     |

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