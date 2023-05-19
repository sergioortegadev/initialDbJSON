# Simple E Commerce Initial DB

## Entity List

1. Products [products](#products)
1. Products Categories [products_categories](#product_category)
1. Customer [customers](#customers)
1. Customer Addresses [customer_addresses](#customer_addresses)
1. Customer IVA [customer_iva](#customer_iva)
1. Addresses Cities [addresses_cities](#customer_cities)
1. Addresses Provincias [addresses_states](#customer_states)
1. Addresses Countries [addresses_countries](#customer_countries)
1. Sales [sales](#sales)
1. Sellers [sellers](#sellers)

---

## Entities

## products

1. product_id : number **[PK]**
1. bar_code : number **[isUnique]**
1. category [products_categories] : number **[FK]**
1. tags : string[]
1. product_name : string
1. description : string
1. price : number
1. stock : number
1. images : string[]

---

## customers

1. customers_id : number **[PK]**
1. name : string
1. last_name : string
1. phone_number : number
1. mail : string **[isUnique]**
1. cuit : number **[isUnique]**
1. iva [customer_iva] : number **[FK]**
1. organization : string
1. address [customer_addresses] : number **[FK]**

---

## [ customer_addresses ]

1. address_id : number **[PK]**
1. customer_id [customers] : number **[FK]**
1. street_address : string
1. number_address : number
1. zip_postal_code : number
1. city [addresses_cities] : number **[FK]**
1. state_province [addresses_states] : number **[FK]**
1. country [addresses_countries] : number **[FK]**

---
