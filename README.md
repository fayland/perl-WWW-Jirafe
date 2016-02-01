# NAME

WWW::Jirafe - Jirafe API

# SYNOPSIS

    use WWW::Jirafe;

    my $jirafe = WWW::Jirafe->new(
        site_id => 123,
        access_token => 'token_from_https://account.jirafe.com/accounts/settings/site/123/tokens/',
    );

    my $params = decode_json('{
        "id": "1234abc",
        "active_flag": true,
        "change_date": "2013-06-17T15:15:53.000Z",
        "create_date": "2013-06-17T15:15:53.000Z",
        "email": "john.doe@gmail.com",
        "first_name": "John",
        "last_name": "Doe",
        "name": "John Doe"
    }');
    my $res = $jirafe->customer($params);

# DESCRIPTION

WWW::Jirafe is

## METHODS

### batch

[http://docs.jirafe.com/api/batch\_endpoint/](http://docs.jirafe.com/api/batch_endpoint/)

### cart

[http://docs.jirafe.com/api/cart\_endpoint/](http://docs.jirafe.com/api/cart_endpoint/)

    my $params = decode_json('{
        "id": "8797436543019",
        "create_date": "2013-06-17T15:16:10.000Z",
        "change_date": "2013-06-17T15:16:15.000Z",
        "subtotal": 99.85,
        "total": 99.85,
        "total_tax": 4.75,
        "total_shipping": 0.0,
        "total_payment_cost": 0.0,
        "total_discounts": 0.0,
        "currency": "USD",
        "cookies": {},
        "items": [
            {
                "id": "8797371007020",
                "create_date": "2013-06-17T15:16:11.000Z",
                "change_date": "2013-06-17T15:16:11.000Z",
                "cart_item_number": "1",
                "quantity": 1,
                "price": 99.85,
                "discount_price": 0.0,
                "product": {
                    "id": "8796107014145",
                    "create_date": "2013-03-28T19:46:39.000Z",
                    "change_date": "2013-03-28T19:50:58.000Z",
                    "is_product": true,
                    "is_sku": true,
                    "catalog": {
                        "id": "electronicsProductCatalog",
                        "name": "Electronics Product Catalog"
                    },
                    "name": "PowerShot A480",
                    "code": "1934793",
                    "brand": "Canon",
                    "categories": [
                        {
                            "id": "8796098461838",
                            "name": "Digital Compacts"
                        },
                        {
                            "id": "8796099248270",
                            "name": "Canon"
                        }
                    ],
                    "images": [
                        {
                            "url": "http://yourstore.com/images/the_photo.jpg"
                        }
                    ]
                }
            }
        ],
        "previous_items": [
        ],
        "customer": {
            "id": "abc123",
            "create_date": "2013-06-17T15:16:11.000Z",
            "change_date": "2013-06-17T15:16:11.000Z",
            "email": "foo@example.com",
            "first_name": "Jane",
            "last_name": "Doe"
        },
        "visit": {
            "visit_id": "1234",
            "visitor_id": "4321",
            "pageview_id": "5678",
            "last_pageview_id": "8765"
        }
    }');

    my $res = $jirafe->cart($params);

### category

[http://docs.jirafe.com/api/category\_endpoint/](http://docs.jirafe.com/api/category_endpoint/)

### customer

[http://docs.jirafe.com/api/customer\_endpoint/](http://docs.jirafe.com/api/customer_endpoint/)

    my $params = decode_json('{
        "id": "1234abc",
        "active_flag": true,
        "change_date": "2013-06-17T15:15:53.000Z",
        "create_date": "2013-06-17T15:15:53.000Z",
        "email": "john.doe@gmail.com",
        "first_name": "John",
        "last_name": "Doe",
        "name": "John Doe"
    }');

    my $res = $jirafe->customer($params);

### employee

[http://docs.jirafe.com/api/employee\_endpoint/](http://docs.jirafe.com/api/employee_endpoint/)

### order

[http://docs.jirafe.com/api/order\_endpoint/](http://docs.jirafe.com/api/order_endpoint/)

    my $params = decode_json('{
        "order_number": "123456789",
        "cart_id": "123456789",
        "status": "placed",
        "order_date": "2013-06-17T15:16:10.000Z",
        "customer": {
            "id": "abc123",
            "create_date": "2013-06-17T15:16:11.000Z",
            "change_date": "2013-06-17T15:16:11.000Z",
            "email": "foo@example.com",
            "first_name": "Jane",
            "last_name": "Doe"
        },
        "visit": {
            "visit_id": "1234",
            "visitor_id": "4321",
            "pageview_id": "5678",
            "last_pageview_id": "8765"
        }
    }');

    my $res = $jirafe->order($params);

### product

[http://docs.jirafe.com/api/product\_endpoint/](http://docs.jirafe.com/api/product_endpoint/)

    my $params = decode_json('{
        "id": "8796107014145",
        "create_date": "2013-03-28T19:46:39.000Z",
        "change_date": "2013-03-28T19:50:58.000Z",
        "is_product": true,
        "is_sku": true,
        "catalog": {
            "id": "electronicsProductCatalog",
            "name": "Electronics Product Catalog"
        },
        "name": "PowerShot A480",
        "code": "1934793",
        "brand": "Canon",
        "categories": [
            {
                "id": "8796098461838",
                "name": "Digital Compacts"
            },
            {
                "id": "8796099248270",
                "name": "Canon"
            }
        ],
        "images": [
            {
                "url": "http://yourstore.com/images/the_photo.jpg"
            }
        ]
    }');

    my $res = $jirafe->product($params);

### cost

[http://docs.jirafe.com/api/cost\_endpoint/](http://docs.jirafe.com/api/cost_endpoint/)

### inventory

[http://docs.jirafe.com/api/inventory\_endpoint/](http://docs.jirafe.com/api/inventory_endpoint/)

### heartbeat

[http://docs.jirafe.com/api/heartbeat\_endpoint/](http://docs.jirafe.com/api/heartbeat_endpoint/)

# AUTHOR

Fayland Lam <fayland@binary.com>

# COPYRIGHT

Copyright 2016- Fayland Lam

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO
