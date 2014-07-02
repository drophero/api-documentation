Subscription Management
=======================

## Get subscriptions

- <code>GET /v1/subscribed</code> will return all current subscriptions and deleted subscriptions related to requester account.

```JSON
{
    "0": {
        "iditem": "5554",
        "product_name": "Producte test 1",
        "ean": "1",
        "qty": null,
        "status": null,
        "selling_price": "6.0000",
        "suggested_retail_price": null,
        "weight": null,
        "description_short": null,
        "description_long": null,
        "img_url": null,
        "rma_policy": null,
        "tax_amount": "21",
        "wholesaler": [
            {
                "idwholesaler": "1",
                "wholesaler_name": "Empresa de test",
                "wholesaler_country": "ES"
            }
        ],
        "shipping": [
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "1",
                "shipping_price": "7.4000"
            },
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "2",
                "shipping_price": "2.4000"
            }
        ],
        "local_categories": [
            "2"
        ],
        "payments": [
            {
                "payment_area_iso": "ES",
                "payment_name": "cash_delivery",
                "payment_charge": "2.5000"
            }
        ]
    },
    "1": {
        "iditem": "5555",
        "product_name": "Producte test 2",
        "ean": "2",
        "qty": null,
        "status": null,
        "selling_price": "6.0000",
        "suggested_retail_price": null,
        "weight": null,
        "description_short": null,
        "description_long": null,
        "img_url": null,
        "rma_policy": null,
        "tax_amount": "21",
        "wholesaler": [
            {
                "idwholesaler": "1",
                "wholesaler_name": "Empresa de test",
                "wholesaler_country": "ES"
            }
        ],
        "shipping": [
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "1",
                "shipping_price": "7.4000"
            },
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "2",
                "shipping_price": "2.4000"
            }
        ],
        "local_categories": [
            "5"
        ],
        "payments": 0
    },
    "deleted": [
        "5559",
        "5557"
    ]
}
```

## Get subscriptions from timestamp

- <code>GET /v1/subscribed/from/**int**</code> will return all current subscriptions and deleted subscriptions related to requester account from a point on time tu current (time to epoch/GMT).

Example:

```
http://api.drophero.com/v1/subscribed/from/1382116367
```
This call will return all subscriptions from: Fri, 18 Oct 2013 17:12:47 GMT

This call will return the same fields as basic <code>subscribed</code> call.

**We strongly recommend the use of <code>subscibed/from</code> instead of his basic form. Using this call will allow you to optimize the amount of traffic from your servers.**

```JSON
{
    "0": {
        "iditem": "5554",
        "product_name": "Producte test 1",
        "ean": "1",
        "qty": null,
        "status": null,
        "selling_price": "6.0000",
        "suggested_retail_price": null,
        "weight": null,
        "description_short": null,
        "description_long": null,
        "img_url": null,
        "rma_policy": null,
        "tax_amount": "21",
        "wholesaler": [
            {
                "idwholesaler": "1",
                "wholesaler_name": "Empresa de test",
                "wholesaler_country": "ES"
            }
        ],
        "shipping": [
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "1",
                "shipping_price": "7.4000"
            },
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "2",
                "shipping_price": "2.4000"
            }
        ],
        "local_categories": [
            "2"
        ],
        "payments": [
            {
                "payment_area_iso": "ES",
                "payment_name": "cash_delivery",
                "payment_charge": "2.5000"
            }
        ]
    }
}
```