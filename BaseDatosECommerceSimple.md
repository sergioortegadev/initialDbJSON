# Simple E Commerce Initial DB

## Entity List

1. Products [products](#1-products-data-entity)
1. Products Categories [products_categories](#2-products_categories-catalog-entity)
1. Customer [customers](#3-customers-de)
1. Customer Addresses [customer_addresses](#4-customer_addresses-de)
1. Customer IVA [customer_iva](#5-customer_iva-ce)
1. Addresses Cities [addresses_cities](#6-addresses_cities-ce)
1. Addresses Provincias [addresses_states](#7-addresses_states-ce)
1. Addresses Countries [addresses_countries](#8-addresses_countries-ce)
1. Sales [sales](#9-sales-de)
1. Sellers [sellers](#10-sellers-ce)
1. Sellers Areas [sellers_areas](#11-sellers_areas-ce)
1. Payment Methods [payment_methods](#12-payment_methods-ce)
1. Stores [stores](#13-stores-ce)

---

## Entities

## 1 products **[Data Entity]**

1. product_id : INT AUTO **[PK]**
1. bar_code : INT **[UQ]**
1. product_category_id [products_categories] : INT **[FK]**
1. tags : VARCHAR(255) (Debería ser un array de VARCHAR(30) )
1. product_name : VARCHAR(100)
1. description : TEXT
1. product_price : FLOAT
1. stock : INT
1. images : VARCHAR(255) (Debería ser un array de VARCHAR(30) )

## 2 products_categories **[Catalog Entity]**

1. product_category_id : INT AUTO **[PK]**
1. name : VARCHAR(30)

## 3 customers **[DE]**

1. customer_id : INT AUTO **[PK]**
1. name : VARCHAR(100)
1. last_name : VARCHAR(100)
1. phone_number : INT
1. mail : VARCHAR(100) **[UQ]**
1. cuit : VARCHAR(100) **[UQ]**
1. customer_iva_id [customer_iva] : INT **[FK]**
1. organization : VARCHAR(100)
1. customer_address_id [customer_addresses] : INT **[FK]**

## 4 customer_addresses **[DE]**

1. customer_address_id : INT AUTO **[PK]**
1. customer_id [customers] : INT **[FK]**
1. street_address : VARCHAR(100)
1. number_address : INT
1. zip_postal_code : VARCHAR(10)
1. addresses_city_id [addresses_cities] : INT **[FK]**
1. addresses_state_id [addresses_states] : INT **[FK]**
1. addresses_country_id [addresses_countries] : INT **[FK]**

## 5 customer_iva **[CE]**

1. customer_iva_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

## 6 addresses_cities **[CE]**

1. addresses_city_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

## 7 addresses_states **[CE]**

1. addresses_state_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

## 8 addresses_countries **[CE]**

1. addresses_country_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

## 9 sales **[DE]**

1. sale_id : INT AUTO **[PK]**
1. date : DATE
1. store_id [stores] : INT **[FK]**
1. seller_id [sellers] : INT **[FK]**
1. customer_id [customers] : INT **[FK]**
1. product_id [products] : INT (Debería ser un array de INT) **[FK]**
1. product_price [products] : FLOAT (Debería ser un array de FLOAT) **[FK]**
1. amount : FLOAT
1. payment_method_id [payment_methods] : INT **[FK]**
1. delivered : BOOLEAN
1. observation : TEXT

## 10 sellers **[CE]**

1. seller_id : INT AUTO **[PK]**
1. name : VARCHAR(100)
1. sellers_area_id [sellers_areas] : INT **[FK]**

## 11 sellers_areas **[CE]**

1. sellers_area_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

## 12 payment_methods **[CE]**

1. payment_method_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

## 13 stores **[CE]**

1. store_id : INT AUTO **[PK]**
1. name : VARCHAR(50)

---

## Relaciones

1. Un **product** _pertenece_ a un **products_categories** _(1 a 1)_
1.

---

## Reglas de Negocio

## products

1. Crear el registro de un producto
1. Leer el registro de un producto dada una condición en particular
1. Leer todos los registros de la entidad productos
1. Modificar los datos de un producto dada una condición en particular.
1. Eliminar el registro de un producto dada una condición en particular
