```js

PUT /products
{
  "mappings": {
    "properties": {
      "product_id": { "type": "keyword" },
      "name": { "type": "text" },
      "description": { "type": "text" },
      "category": { "type": "keyword" },
      "price": { "type": "float" },
      "in_stock": { "type": "boolean" },
      "release_date": { "type": "date" },
      "tags": { "type": "keyword" }
    }
  }
}

POST /products/_doc/1
{
  "product_id": "P1001",
  "name": "Wireless Headphones",
  "description": "Noise-cancelling over-ear headphones.",
  "category": "Electronics",
  "price": 99.99,
  "in_stock": true,
  "release_date": "2023-09-10",
  "tags": ["audio", "wireless", "headphones"]
}

POST /products/_doc/2
{
  "product_id": "P1002",
  "name": "Gaming Laptop",
  "description": "High-performance laptop for gaming.",
  "category": "Computers",
  "price": 1299.00,
  "in_stock": false,
  "release_date": "2022-05-15",
  "tags": ["gaming", "laptop", "performance"]
}

GET /products/_search
{
  "query": {
    "match_all": {}
  }
}
GET /products/_mapping

PUT /customers
{
  "mappings": {
    "properties": {
      "customer_id": { "type": "keyword" },
      "name": { "type": "text" },
      "email": { "type": "keyword" },
      "address": {
        "properties": {
          "street": { "type": "text" },
          "city": { "type": "keyword" },
          "state": { "type": "keyword" },
          "zip": { "type": "keyword" }
        }
      },
      "join_date": { "type": "date" },
      "loyalty_tier": { "type": "keyword" }
    }
  }
}


PUT /orders
{
  "mappings": {
    "properties": {
      "order_id": { "type": "keyword" },
      "customer_id": { "type": "keyword" },
      "order_date": { "type": "date" },
      "status": { "type": "keyword" },
      "total_amount": { "type": "float" },
      "items": {
        "type": "nested",
        "properties": {
          "product_id": { "type": "keyword" },
          "product_name": { "type": "text" },
          "quantity": { "type": "integer" },
          "price": { "type": "float" }
        }
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "match_all": {}
  }
}



POST /products/_bulk
{"index": {"_id": "P1001"}}{"product_id": "P1001", "name": "Very X", "description": "Dream apply station card discussion technology design.", "category": "Gaming", "price": 1448.39, "in_stock": true, "release_date": "2023-02-28", "tags": ["gaming", "wireless", "4k", "eco"]}{"index": {"_id": "P1002"}}{"product_id": "P1002", "name": "Laugh Lite", "description": "Necessary mission trip religious including most record.", "category": "Books", "price": 150.04, "in_stock": true, "release_date": "2022-05-27", "tags": ["limited", "eco", "new"]}{"index": {"_id": "P1003"}}{"product_id": "P1003", "name": "Toward X", "description": "Whole serve writer score hope pass.", "category": "Books", "price": 296.82, "in_stock": false, "release_date": "2022-05-15", "tags": ["new", "discount", "portable"]}{"index": {"_id": "P1004"}}{"product_id": "P1004", "name": "Sell Pro", "description": "Scientist oil billion.", "category": "Mobile", "price": 1274.34, "in_stock": false, "release_date": "2025-01-03", "tags": ["wireless", "smart", "limited"]}{"index": {"_id": "P1005"}}{"product_id": "P1005", "name": "Series Lite", "description": "Voice reality enough friend.", "category": "Gaming", "price": 134.1, "in_stock": true, "release_date": "2022-12-19", "tags": ["smart"]}{"index": {"_id": "P1006"}}{"product_id": "P1006", "name": "Should X", "description": "War song off.", "category": "Books", "price": 54.8, "in_stock": true, "release_date": "2022-06-25", "tags": ["portable", "bestseller"]}{"index": {"_id": "P1007"}}{"product_id": "P1007", "name": "Significant Lite", "description": "Tell hotel clear order.", "category": "Home Appliances", "price": 148.42, "in_stock": false, "release_date": "2023-07-21", "tags": ["new", "smart"]}{"index": {"_id": "P1008"}}{"product_id": "P1008", "name": "Bill Plus", "description": "Recognize truth same people camera foot.", "category": "Computers", "price": 1423.01, "in_stock": true, "release_date": "2025-01-12", "tags": ["smart", "gaming", "eco"]}{"index": {"_id": "P1009"}}{"product_id": "P1009", "name": "At Max", "description": "Size short somebody.", "category": "Gaming", "price": 840.3, "in_stock": true, "release_date": "2024-03-27", "tags": ["bestseller", "portable", "gaming"]}{"index": {"_id": "P1010"}}{"product_id": "P1010", "name": "Change Max", "description": "Alone economic lose couple necessary cup feeling.", "category": "Home Appliances", "price": 363.16, "in_stock": true, "release_date": "2022-11-10", "tags": ["eco", "wireless"]}{"index": {"_id": "P1011"}}{"product_id": "P1011", "name": "Organization Lite", "description": "Mission cold each young.", "category": "Computers", "price": 188.66, "in_stock": false, "release_date": "2023-12-22", "tags": ["gaming", "limited", "bestseller", "4k"]}{"index": {"_id": "P1012"}}{"product_id": "P1012", "name": "Trouble Max", "description": "She contain follow site perform.", "category": "Books", "price": 242.48, "in_stock": true, "release_date": "2023-04-21", "tags": ["eco", "wireless", "4k", "gaming"]}{"index": {"_id": "P1013"}}{"product_id": "P1013", "name": "South X", "description": "That avoid actually remember minute.", "category": "Home Appliances", "price": 1407.08, "in_stock": true, "release_date": "2024-02-09", "tags": ["eco"]}{"index": {"_id": "P1014"}}{"product_id": "P1014", "name": "Difference Plus", "description": "Significant market process own move sort.", "category": "Gaming", "price": 1275.59, "in_stock": false, "release_date": "2025-01-04", "tags": ["smart", "discount", "portable", "bestseller"]}{"index": {"_id": "P1015"}}{"product_id": "P1015", "name": "Shake Plus", "description": "Baby resource finish wall.", "category": "Electronics", "price": 1089.95, "in_stock": true, "release_date": "2023-11-10", "tags": ["discount", "new", "4k", "gaming"]}{"index": {"_id": "P1016"}}{"product_id": "P1016", "name": "Total X", "description": "Point into art you most natural.", "category": "Mobile", "price": 40.91, "in_stock": true, "release_date": "2024-02-27", "tags": ["eco"]}{"index": {"_id": "P1017"}}{"product_id": "P1017", "name": "That X", "description": "Admit girl effort remain color standard trouble.", "category": "Gaming", "price": 973.41, "in_stock": true, "release_date": "2022-08-08", "tags": ["bestseller"]}{"index": {"_id": "P1018"}}{"product_id": "P1018", "name": "Rise Plus", "description": "Shoulder throw plant minute phone Congress.", "category": "Gaming", "price": 642.65, "in_stock": false, "release_date": "2023-07-20", "tags": ["portable", "bestseller", "new"]}{"index": {"_id": "P1019"}}{"product_id": "P1019", "name": "Away Max", "description": "Pass point should eat decide.", "category": "Books", "price": 1085.04, "in_stock": true, "release_date": "2024-03-17", "tags": ["wireless", "gaming", "bestseller", "smart"]}{"index": {"_id": "P1020"}}{"product_id": "P1020", "name": "Mention X", "description": "Effort main a art crime.", "category": "Gaming", "price": 688.9, "in_stock": true, "release_date": "2023-11-18", "tags": ["discount"]}

POST /customers/_bulk
{"index": {"_id": "C2001"}}{"customer_id": "C2001", "name": "Amber Ramirez", "email": "rachelwilliams@yahoo.com", "address": {"street": "9901 Emily Junction Apt. 056", "city": "East Stephanie", "state": "WY", "zip": "34686"}, "join_date": "2023-01-01", "loyalty_tier": "Gold"}{"index": {"_id": "C2002"}}{"customer_id": "C2002", "name": "Rachel Mccarty", "email": "murrayjoshua@simpson.com", "address": {"street": "904 Fernandez Isle", "city": "West Kathyland", "state": "OH", "zip": "48898"}, "join_date": "2021-04-09", "loyalty_tier": "Platinum"}{"index": {"_id": "C2003"}}{"customer_id": "C2003", "name": "Natalie Gonzalez", "email": "millerjeffrey@gmail.com", "address": {"street": "6947 Bauer Centers", "city": "East Heather", "state": "NC", "zip": "90098"}, "join_date": "2024-05-14", "loyalty_tier": null}{"index": {"_id": "C2004"}}{"customer_id": "C2004", "name": "Jessica Wang", "email": "zachary41@garcia.com", "address": {"street": "300 Allen Gardens Suite 957", "city": "Juliaport", "state": "IL", "zip": "97362"}, "join_date": "2021-02-21", "loyalty_tier": "Platinum"}{"index": {"_id": "C2005"}}{"customer_id": "C2005", "name": "Patricia Hernandez", "email": "russell78@moss-mendez.com", "address": {"street": "800 Hammond Plain", "city": "Christopherchester", "state": "NC", "zip": "85527"}, "join_date": "2021-01-22", "loyalty_tier": "Silver"}{"index": {"_id": "C2006"}}{"customer_id": "C2006", "name": "Caitlin Poole DVM", "email": "breannawood@delgado.com", "address": {"street": "6029 Cox Prairie", "city": "Jamesfurt", "state": "NJ", "zip": "33400"}, "join_date": "2024-03-11", "loyalty_tier": "Silver"}{"index": {"_id": "C2007"}}{"customer_id": "C2007", "name": "Andrew Conrad", "email": "jhanson@villegas.com", "address": {"street": "6349 Castillo Meadow", "city": "Valerieburgh", "state": "CO", "zip": "54945"}, "join_date": "2024-01-06", "loyalty_tier": "Silver"}{"index": {"_id": "C2008"}}{"customer_id": "C2008", "name": "Virginia Bradley", "email": "stephanie94@cooper.com", "address": {"street": "5793 Newton Harbor Apt. 786", "city": "East Thomas", "state": "ID", "zip": "86509"}, "join_date": "2020-02-25", "loyalty_tier": "Silver"}{"index": {"_id": "C2009"}}{"customer_id": "C2009", "name": "Marc Miller", "email": "robert94@conner.biz", "address": {"street": "23720 Christine Canyon Apt. 025", "city": "Mccoyview", "state": "MT", "zip": "87019"}, "join_date": "2020-10-01", "loyalty_tier": "Gold"}{"index": {"_id": "C2010"}}{"customer_id": "C2010", "name": "William Thompson", "email": "carterjames@yahoo.com", "address": {"street": "666 Rose Isle", "city": "Kirkshire", "state": "KY", "zip": "47071"}, "join_date": "2024-11-15", "loyalty_tier": "Platinum"}{"index": {"_id": "C2011"}}{"customer_id": "C2011", "name": "Michael Little", "email": "garciadouglas@gmail.com", "address": {"street": "57526 Taylor Ridge", "city": "Port Nancy", "state": "SD", "zip": "20072"}, "join_date": "2022-09-12", "loyalty_tier": "Gold"}{"index": {"_id": "C2012"}}{"customer_id": "C2012", "name": "Justin Villa", "email": "tcook@gmail.com", "address": {"street": "0260 Timothy Orchard", "city": "West Theresaborough", "state": "ME", "zip": "30063"}, "join_date": "2023-06-15", "loyalty_tier": "Platinum"}{"index": {"_id": "C2013"}}{"customer_id": "C2013", "name": "Teresa Miller", "email": "fschneider@patrick.biz", "address": {"street": "172 Davies Road", "city": "South Nicholasport", "state": "CA", "zip": "37704"}, "join_date": "2021-06-23", "loyalty_tier": "Silver"}{"index": {"_id": "C2014"}}{"customer_id": "C2014", "name": "Rachel Gonzalez", "email": "thomasshawn@gmail.com", "address": {"street": "0348 Williams Meadow", "city": "Nicholasport", "state": "NY", "zip": "49705"}, "join_date": "2020-12-07", "loyalty_tier": null}{"index": {"_id": "C2015"}}{"customer_id": "C2015", "name": "Sharon Green", "email": "grantjenna@gmail.com", "address": {"street": "6481 Jonathan Mill", "city": "North Williamton", "state": "NY", "zip": "12916"}, "join_date": "2020-11-23", "loyalty_tier": "Silver"}{"index": {"_id": "C2016"}}{"customer_id": "C2016", "name": "Melinda Cox", "email": "vcook@graham.com", "address": {"street": "75106 Brian Tunnel Apt. 077", "city": "North Sherry", "state": "NE", "zip": "72137"}, "join_date": "2022-06-07", "loyalty_tier": "Platinum"}{"index": {"_id": "C2017"}}{"customer_id": "C2017", "name": "Amy Brown", "email": "dnewton@hotmail.com", "address": {"street": "606 Montgomery Club Apt. 209", "city": "West Tarashire", "state": "FL", "zip": "66150"}, "join_date": "2024-10-17", "loyalty_tier": "Silver"}{"index": {"_id": "C2018"}}{"customer_id": "C2018", "name": "Diane Moore", "email": "sarahhatfield@harris.org", "address": {"street": "71730 Kristina Ville", "city": "East William", "state": "PA", "zip": "45596"}, "join_date": "2020-07-02", "loyalty_tier": "Platinum"}{"index": {"_id": "C2019"}}{"customer_id": "C2019", "name": "Heather Bennett", "email": "wilsonjenny@gmail.com", "address": {"street": "922 Steven Parkway Suite 190", "city": "West Kyle", "state": "IN", "zip": "70486"}, "join_date": "2024-05-26", "loyalty_tier": "Gold"}{"index": {"_id": "C2020"}}{"customer_id": "C2020", "name": "Jesse Wells", "email": "danielrichardson@yahoo.com", "address": {"street": "15996 Kristopher Green Apt. 220", "city": "Vasquezhaven", "state": "GA", "zip": "41647"}, "join_date": "2025-01-13", "loyalty_tier": "Platinum"}

POST /orders/_bulk
{"index": {"_id": "O3001"}}{"order_id": "O3001", "customer_id": "C2011", "order_date": "2023-12-17", "status": "Processing", "total_amount": 3273.15, "items": [{"product_id": "P1006", "product_name": "Should X", "quantity": 2, "price": 54.8}, {"product_id": "P1018", "product_name": "Rise Plus", "quantity": 1, "price": 642.65}, {"product_id": "P1009", "product_name": "At Max", "quantity": 3, "price": 840.3}]}{"index": {"_id": "O3002"}}{"order_id": "O3002", "customer_id": "C2012", "order_date": "2024-03-03", "status": "Processing", "total_amount": 8356.5, "items": [{"product_id": "P1005", "product_name": "Series Lite", "quantity": 3, "price": 134.1}, {"product_id": "P1019", "product_name": "Away Max", "quantity": 3, "price": 1085.04}, {"product_id": "P1015", "product_name": "Shake Plus", "quantity": 1, "price": 1089.95}, {"product_id": "P1017", "product_name": "That X", "quantity": 3, "price": 973.41}, {"product_id": "P1020", "product_name": "Mention X", "quantity": 1, "price": 688.9}]}{"index": {"_id": "O3003"}}{"order_id": "O3003", "customer_id": "C2020", "order_date": "2023-11-06", "status": "Shipped", "total_amount": 2043.76, "items": [{"product_id": "P1010", "product_name": "Change Max", "quantity": 1, "price": 363.16}, {"product_id": "P1009", "product_name": "At Max", "quantity": 2, "price": 840.3}]}{"index": {"_id": "O3004"}}{"order_id": "O3004", "customer_id": "C2011", "order_date": "2024-08-25", "status": "Delivered", "total_amount": 268.2, "items": [{"product_id": "P1005", "product_name": "Series Lite", "quantity": 2, "price": 134.1}]}{"index": {"_id": "O3005"}}{"order_id": "O3005", "customer_id": "C2012", "order_date": "2023-08-18", "status": "Cancelled", "total_amount": 392.52, "items": [{"product_id": "P1002", "product_name": "Laugh Lite", "quantity": 1, "price": 150.04}, {"product_id": "P1012", "product_name": "Trouble Max", "quantity": 1, "price": 242.48}]}{"index": {"_id": "O3006"}}{"order_id": "O3006", "customer_id": "C2018", "order_date": "2023-06-03", "status": "Cancelled", "total_amount": 8044.81, "items": [{"product_id": "P1020", "product_name": "Mention X", "quantity": 1, "price": 688.9}, {"product_id": "P1008", "product_name": "Bill Plus", "quantity": 3, "price": 1423.01}, {"product_id": "P1009", "product_name": "At Max", "quantity": 2, "price": 840.3}, {"product_id": "P1009", "product_name": "At Max", "quantity": 1, "price": 840.3}, {"product_id": "P1011", "product_name": "Organization Lite", "quantity": 3, "price": 188.66}]}{"index": {"_id": "O3007"}}{"order_id": "O3007", "customer_id": "C2002", "order_date": "2024-04-19", "status": "Delivered", "total_amount": 5598.17, "items": [{"product_id": "P1015", "product_name": "Shake Plus", "quantity": 3, "price": 1089.95}, {"product_id": "P1015", "product_name": "Shake Plus", "quantity": 2, "price": 1089.95}, {"product_id": "P1007", "product_name": "Significant Lite", "quantity": 1, "price": 148.42}]}{"index": {"_id": "O3008"}}{"order_id": "O3008", "customer_id": "C2019", "order_date": "2023-04-02", "status": "Shipped", "total_amount": 2423.3, "items": [{"product_id": "P1016", "product_name": "Total X", "quantity": 3, "price": 40.91}, {"product_id": "P1020", "product_name": "Mention X", "quantity": 1, "price": 688.9}, {"product_id": "P1011", "product_name": "Organization Lite", "quantity": 1, "price": 188.66}, {"product_id": "P1008", "product_name": "Bill Plus", "quantity": 1, "price": 1423.01}]}{"index": {"_id": "O3009"}}{"order_id": "O3009", "customer_id": "C2020", "order_date": "2024-05-13", "status": "Cancelled", "total_amount": 2644.81, "items": [{"product_id": "P1010", "product_name": "Change Max", "quantity": 3, "price": 363.16}, {"product_id": "P1006", "product_name": "Should X", "quantity": 1, "price": 54.8}, {"product_id": "P1020", "product_name": "Mention X", "quantity": 2, "price": 688.9}, {"product_id": "P1016", "product_name": "Total X", "quantity": 3, "price": 40.91}]}{"index": {"_id": "O3010"}}{"order_id": "O3010", "customer_id": "C2019", "order_date": "2023-11-10", "status": "Cancelled", "total_amount": 6209.43, "items": [{"product_id": "P1012", "product_name": "Trouble Max", "quantity": 1, "price": 242.48}, {"product_id": "P1015", "product_name": "Shake Plus", "quantity": 3, "price": 1089.95}, {"product_id": "P1004", "product_name": "Sell Pro", "quantity": 2, "price": 1274.34}, {"product_id": "P1007", "product_name": "Significant Lite", "quantity": 1, "price": 148.42}]}{"index": {"_id": "O3011"}}{"order_id": "O3011", "customer_id": "C2015", "order_date": "2023-10-14", "status": "Processing", "total_amount": 893.72, "items": [{"product_id": "P1002", "product_name": "Laugh Lite", "quantity": 2, "price": 150.04}, {"product_id": "P1003", "product_name": "Toward X", "quantity": 2, "price": 296.82}]}{"index": {"_id": "O3012"}}{"order_id": "O3012", "customer_id": "C2019", "order_date": "2023-07-03", "status": "Delivered", "total_amount": 4783.84, "items": [{"product_id": "P1013", "product_name": "South X", "quantity": 1, "price": 1407.08}, {"product_id": "P1020", "product_name": "Mention X", "quantity": 2, "price": 688.9}, {"product_id": "P1003", "product_name": "Toward X", "quantity": 3, "price": 296.82}, {"product_id": "P1005", "product_name": "Series Lite", "quantity": 2, "price": 134.1}, {"product_id": "P1009", "product_name": "At Max", "quantity": 1, "price": 840.3}]}{"index": {"_id": "O3013"}}{"order_id": "O3013", "customer_id": "C2007", "order_date": "2023-05-16", "status": "Delivered", "total_amount": 7461.18, "items": [{"product_id": "P1010", "product_name": "Change Max", "quantity": 3, "price": 363.16}, {"product_id": "P1004", "product_name": "Sell Pro", "quantity": 2, "price": 1274.34}, {"product_id": "P1004", "product_name": "Sell Pro", "quantity": 3, "price": 1274.34}]}{"index": {"_id": "O3014"}}{"order_id": "O3014", "customer_id": "C2019", "order_date": "2023-05-29", "status": "Shipped", "total_amount": 3259.94, "items": [{"product_id": "P1001", "product_name": "Very X", "quantity": 2, "price": 1448.39}, {"product_id": "P1010", "product_name": "Change Max", "quantity": 1, "price": 363.16}]}{"index": {"_id": "O3015"}}{"order_id": "O3015", "customer_id": "C2012", "order_date": "2024-03-25", "status": "Processing", "total_amount": 4420.41, "items": [{"product_id": "P1003", "product_name": "Toward X", "quantity": 2, "price": 296.82}, {"product_id": "P1014", "product_name": "Difference Plus", "quantity": 3, "price": 1275.59}]}{"index": {"_id": "O3016"}}{"order_id": "O3016", "customer_id": "C2005", "order_date": "2025-02-01", "status": "Processing", "total_amount": 3395.21, "items": [{"product_id": "P1001", "product_name": "Very X", "quantity": 1, "price": 1448.39}, {"product_id": "P1017", "product_name": "That X", "quantity": 2, "price": 973.41}]}{"index": {"_id": "O3017"}}{"order_id": "O3017", "customer_id": "C2004", "order_date": "2024-05-23", "status": "Delivered", "total_amount": 134.1, "items": [{"product_id": "P1005", "product_name": "Series Lite", "quantity": 1, "price": 134.1}]}{"index": {"_id": "O3018"}}{"order_id": "O3018", "customer_id": "C2010", "order_date": "2024-09-14", "status": "Processing", "total_amount": 2820.98, "items": [{"product_id": "P1009", "product_name": "At Max", "quantity": 3, "price": 840.3}, {"product_id": "P1002", "product_name": "Laugh Lite", "quantity": 2, "price": 150.04}]}{"index": {"_id": "O3019"}}{"order_id": "O3019", "customer_id": "C2016", "order_date": "2024-04-29", "status": "Delivered", "total_amount": 2382.24, "items": [{"product_id": "P1005", "product_name": "Series Lite", "quantity": 3, "price": 134.1}, {"product_id": "P1003", "product_name": "Toward X", "quantity": 3, "price": 296.82}, {"product_id": "P1010", "product_name": "Change Max", "quantity": 3, "price": 363.16}]}{"index": {"_id": "O3020"}}{"order_id": "O3020", "customer_id": "C2017", "order_date": "2023-06-25", "status": "Processing", "total_amount": 3269.85, "items": [{"product_id": "P1015", "product_name": "Shake Plus", "quantity": 3, "price": 1089.95}]}


GET /products/_search
{
  "query": {
    "match_all": {}
  }
}


GET /customers/_search
{
  "query": {
    "match_all": {}
  }
}

GET /orders/_search
{
  "query": {
    "match_all": {}
  }
}


GET /products/_doc/P1001

POST /products/_update/P1001
{
  "doc": {
    "price": 79.99
  }
}

GET /products/_doc/P1001

GET /customers/_doc/C2001

POST /customers/_update/C2001
{
   "doc": {
    "address": {
      "city": "San Francisco",
      "state": "CA"
    }
  }
}


GET /customers/_doc/C2001

POST /customers/_update/C2001
{
   "doc": {
    "pincode": 452011
  }
}

GET /customers/_doc/C2001

GET /products/_doc/P1001

POST /products/_update/P1001
{
  "script": {
    "source": "ctx._source.price *= params.factor",
    "lang": "painless",
    "params": {
      "factor": 1.05
    }
  }
}

GET /products/_doc/P1001



POST /products/_update/P1101
{
  "script": {
    "source": "ctx._source.price *= params.factor",
    "lang": "painless",
    "params": {
      "factor": 1.05
    }
  },
  "upsert": {
    "product_id": "P1101",
  "name": "Wireless Headphones 1",
  "description": "Noise-cancelling over-ear headphones.1",
  "category": "Electronics"
  }

}

GET /products/_doc/P1101

POST /products/_update/P1101
{
  "script": {
    "source": "ctx._source.remove('description')"
  }
}
GET /products/_doc/P1101

DELETE /products/_doc/P1001

GET /products/_doc/P1101

POST /products/_delete_by_query
{
  "query": {
    "term": {
      "product_id": "P1101"
    }
  }
}

GET /products/_doc/P1101

delete /employee1


GET /products/_doc/P1002

GET /products/_search
{
  "query": {
    "match": {
      "name": "Should X"
    }
  }
}

GET /products/_search
{
  "query": {
    "match": {
      "name": {
        "query": "Should X",
        "operator": "and"
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "term": {
      "category": "Electronics"
    }
  }
}

GET /products/_search
{
  "query": {
    "terms": {
      "category": ["Electronics", "Computers", "Appliances"]
    }
  }
}


GET /products/_search
{
  "query": {
    "range": {
      "price": {
        "gte": 50,
        "lte": 500
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "must": [
        { "term": { "category": "Electronics" } },
        { "range": { "price": { "lte": 500 } } }
      ],
      "filter": {
        "term": { "in_stock": true }
      }
    }
  }
}

GET /products/_search
{
  "_source": ["name", "price"],
  "query": {
    "match_all": {}
  }
}
GET /orders/_search

GET /orders/_search
{
  "query": {
    "range": {
      "order_date": {
        "gte": "now-30d/d",
        "lte": "now/d"
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "range": {
      "release_date": {
        "gte": "2023-01-01"
      }
    }
  }
}


GET /orders/_search
{
  "query": {
    "range": {
      "order_date": {
        "gte": "now-30d/d",
        "lte": "now",
        "time_zone": "-08:00"
      }
    }
  }
}

GET /orders/_search
{
  "size": 5,
  "sort": [
    { "order_date": "desc" }
  ]
}

GET /products/_search
{
  "sort": [
    { "release_date": "desc" }
  ]
}

GET /products/_search
{
  "query": {
    "bool": {
      "must_not": {
        "exists": {
          "field": "release_date"
        }
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "match": {
      "name": "Wired headphones"
    }
  }
}

GET /products/_search
{
  "query": {
    "match": {
      "name": {
        "query": "wireless headphones",
        "operator": "and"
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "match": {
      "description": {
        "query": "wireless noise-cancelling over-ear headphones",
        "minimum_should_match": "75%"
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "match": {
      "description": {
        "query": "wireless noise-cancelling over-ear headphones",
        "minimum_should_match": "100%"
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "match_phrase": {
      "description": "noise-cancelling headphones"
    }
  }
}

GET /products/_search
{
  "query": {
    "match_phrase": {
      "description": "noise-cancelling over"
    }
  }
}

GET /products/_search
{
  "query": {
    "match_phrase": {
      "description": {
        "query": "noise-cancelling headphones",
        "slop": 2
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "multi_match": {
      "query": "wireless",
      "fields": ["name", "description"]
    }
  }
}

GET /products/_search
{
  "query": {
    "multi_match": {
      "query": "wireless",
      "fields": ["name^2", "description"]
    }
  }
}

GET /products/_search
{
  "query": {
    "match": {
      "name": {
        "query": "wirless",
        "fuzziness": "AUTO"
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "term": {
      "category": "Electronics"
    }
  }
}


GET /products/_search
{
  "query": {
    "terms": {
      "category": ["Electronics", "Computers"]
    }
  }
}

GET /orders/_search
{
  "query": {
    "term": {
      "order_id": "O3007"
    }
  }
}

GET /customers/_search
{
  "query": {
    "term": {
      "email": "jhanson@villegas.com"
    }
  }
}

GET /products/_search
{
  "query": {
    "term": {
      "category": "electronics"
    }
  }
}

GET /products/_search
{
  "query": {
    "term": {
      "in_stock": true
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "filter": [
        { "term": { "category": "Electronics" } },
        { "term": { "in_stock": true } }
      ]
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "filter": {
        "term": { "category": "Computers" }
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "filter": {
        "terms": { "category": ["Electronics", "Mobile"] }
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "filter": {
        "range": {
          "price": {
            "gte": 50,
            "lte": 500
          }
        }
      }
    }
  }
}

GET /orders/_search
{
  "query": {
    "bool": {
      "filter": {
        "range": {
          "order_date": {
            "gte": "now-30d/d"
          }
        }
      }
    }
  }
}


GET /products/_search
{
  "query": {
    "bool": {
      "filter": {
        "exists": { "field": "release_date" }
      }
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "must": { "term": { "in_stock": true } },
      "must_not": { "term": { "category": "Books" } }
    }
  }
}

GET /products/_search
{
  "query": {
    "bool": {
      "should": [
        { "term": { "category": "Electronics" } },
        { "term": { "category": "Gaming" } }
      ],
      "minimum_should_match": 1
    }
  }
}


GET /products/_search
{
  "sort": [
    { "price": "asc" }
  ]
}



GET /products/_search
{
  "sort": [
    { "price": "desc" }
  ]
}

GET /products/_search
{
  "sort": [
    { "category": "asc" },
    { "price": "asc" }
  ]
}


GET /products/_search
{
  "sort": [
    {
      "release_date": {
        "order": "desc",
        "missing": "_last"
      }
    }
  ]
}

GET /products/_search
{
  "from": 0,
  "size": 10
}


GET /products/_search
{
  "from": 10,
  "size": 10
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "average_price": {
      "avg": {
        "field": "price"
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "total_products": { "value_count": { "field": "product_id" } },
    "min_price": { "min": { "field": "price" } },
    "max_price": { "max": { "field": "price" } },
    "total_sales": { "sum": { "field": "price" } }
  }
}


GET /products/_search
{
  "size": 0,
  "aggs": {
    "top_categories": {
      "terms": {
        "script": {
          "source": "doc['category'].value"
        },
        "size": 5
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "price_ranges": {
      "range": {
        "field": "price",
        "ranges": [
          { "to": 50 },
          { "from": 50, "to": 200 },
          { "from": 200 }
        ]
      }
    }
  }
}
GET /products/_search
{
  "size": 0,
  "aggs": {
    "in_stock_products": {
      "filter": { "term": { "in_stock": true } },
      "aggs": {
        "average_price": {
          "avg": { "field": "price" }
        }
      }
    }
  }
}

GET /orders/_search
{
  "size": 0,
  "aggs": {
    "high_value_orders": {
      "filter": {
        "range": {
          "total_amount": { "gte": 500 }
        }
      },
      "aggs": {
        "total_sales": { "sum": { "field": "total_amount" } }
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "in_stock_products": {
      "filter": {
        "term": { "in_stock": true }
      },
      "aggs": {
        "top_categories": {
          "terms": {
            "script": {
              "source": "doc['category'].value"
            },
            "size": 5
          }
        }
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "electronics_in_stock": {
      "filter": {
        "bool": {
          "must": [
            {
              "script": {
                "script": "doc['category'].value == 'Electronics'"
              }
            },
            {
              "term": { "in_stock": true }
            }
          ]
        }
      },
      "aggs": {
        "total_sales": { "sum": { "field": "price" } }
      }
    }
  }
}
GET /products/_search
{
  "size": 0,
  "aggs": {
    "price_distribution": {
      "histogram": {
        "field": "price",
        "interval": 50
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "price_distribution": {
      "histogram": {
        "field": "price",
        "interval": 50
      },
      "aggs": {
        "average_rating": {
          "avg": { "field": "price" }
        }
      }
    }
  }
}

GET /orders/_search
{
  "size": 0,
  "aggs": {
    "monthly_orders": {
      "date_histogram": {
        "field": "order_date",
        "calendar_interval": "month"
      }
    }
  }
}


GET /orders/_search
{
  "size": 0,
  "aggs": {
    "monthly_sales": {
      "date_histogram": {
        "field": "order_date",
        "calendar_interval": "month"
      },
      "aggs": {
        "total_sales": { "sum": { "field": "total_amount" } },
        "average_order_value": { "avg": { "field": "total_amount" } }
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "price_percentiles": {
      "percentiles": {
        "field": "price",
        "percents": [50, 75, 90, 95]
      }
    }
  }
}

GET /products/_search
{
  "size": 0,
  "aggs": {
    "price_percentile_rank": {
      "percentile_ranks": {
        "field": "price",
        "values": [150]
      }
    }
  }
}

`
