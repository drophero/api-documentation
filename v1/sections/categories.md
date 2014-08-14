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

- <code>POST /v1/category/del</code> 

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


## Getting all my categories

- <code>GET /v1/category</code> will return all current categories related to the requester store account.

```JSON
[
	{
		id: "0",
		name: "Default Category",
		parent_id: "0"
	},
	{
		id: "2",
		name: "",
		parent_id: "1"
	},
	{
		id: "3",
		name: "Perfumes 1.5",
		parent_id: "2"
	},
	{
		id: "4",
		name: "Subcategoria 1",
		parent_id: "3"
	},
	{
		id: "5",
		name: "Cosmetica 1",
		parent_id: "2"
	}
]
```
