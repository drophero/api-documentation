Subscription Management
=======================

## Get subscriptions

- <code>GET /v1/subscriptions</code> will return all subscriptions related to requester account.

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
    "2": {
        "iditem": "5556",
        "product_name": "Producte test 3",
        "ean": "3",
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
                "shipping_price": "14.0000"
            },
            {
                "shipping_area_iso": "ES",
                "idshippingmode": "2",
                "shipping_price": "3.2000"
            }
        ],
        "local_categories": [
            "6"
        ],
        "payments": 0
    },
    "3": {
        "iditem": "5558",
        "product_name": "Producte test 5",
        "ean": "5",
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
        "payments": 0
    },
    "4": {
        "iditem": "5560",
        "product_name": "Producte test 7",
        "ean": "7",
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
                "shipping_price": "1.4000"
            }
        ],
        "local_categories": [
            "2"
        ],
        "payments": 0
    },
    "deleted": [
        "5559",
        "5557"
    ]
}
```