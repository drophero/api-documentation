Shipping Management
===================

## Get shipping methods

- <code>GET /v1/shipping</code> will return all available shipping methods on DropHero. Every subscribed item will be related to any <code>idshippingmode</code> of this list:

```JSON
[
{
idshippingmode: "1",
shipping_area_iso: "ES",
shipping_name: "MRW 24 horas",
shipping_description: "Envío al día siguiente",
shipping_transit_hours: "24"
},
{
idshippingmode: "2",
shipping_area_iso: "ES",
shipping_name: "Correos",
shipping_description: "Envío regular 1 semana",
shipping_transit_hours: "168"
}
]
```