---
layout: page
title: Products
permalink: /products/
---

<h3>Methods</h3>
* [Get Products](#get-products)
* [Get Product](#get-product)
* [Get Product Followers](#get-product-followers)
* [Add Product Follower](#post-product-follower)
* [Delete Product Follower](#delete-product-follower)
* [Get Product Comments](#get-product-comments)
* [Add Product Comment](#post-product-comment)
* [Get Product Wishlists](#get-product-wishlists)
* [Get Product Promotions](#get-product-promotions)
* [Get Product Scans](#get-product-scans)

<br/>

<h4 id="get-products">Get Products</h4>
HTTP Method: GET
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Products retrieved with success",
  "data": {
    "products": [
      {
        "id": "30",
        "name": "Footbal Boot",
        "description": "Adidas Footbal Boot",
        "price": "120.00",
        "old_price": null,
        "count_comments": "1",
        "count_followers": 0,
        "count_promotions": 0,
        "count_wishlists": "1",
        "photos": [
          "product/30/1.png",
          "product/30/2.png"
        ],
        "scans": [
          {
            "id": "2",
            "product_id": "30",
            "barcode": "0000000000000000000"
          }
        ],
        "brand": {
          "id": "7",
          "name": "Adidas",
          "image": "brand/7/image.png"
        }
      },
      ... ... 
    ],
    "paging": {
      "page": 1,
      "count": 16,
      "next_page": false,
      "page_count": 1
    }
  }
}
</pre>
<br/>

<h4 id="get-product">Get Product</h4>
HTTP Method: GET
<br/>
Endpoin
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/:product_id

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Product retrieved with success",
  "data": {
    "id": "30",
    "name": "Footbal Boot",
    "description": "Adidas Footbal Boot",
    "price": "120.00",
    "old_price": null,
    "count_comments": "1",
    "count_followers": 0,
    "count_promotions": 0,
    "count_wishlists": "1",
    "photos": [
      "product/30/1.png",
      "product/30/2.png"
    ],
    "categories": [
      {
        "id": "1",
        "name": "Men",
        "description": "Men"
      }
    ],
    "scans": [
      {
        "id": "2",
        "product_id": "30",
        "barcode": "0000000000000000000"
      }
    ],
    "brand": {
      "id": "7",
      "name": "Adidas",
      "image": "brand/7/image.png"
    }
  }
}
</pre>
<br/>

<h4 id="get-product-followers">Get Product Followers</h4>
HTTP Method: GET
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/followers/:product_id

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Product's followers retrieved with success",
  "data": {
    "id": "30",
    "name": "Footbal Boot",
    "description": "Adidas Footbal Boot",
    "price": "120.00",
    "followers": [
      {
        "id": "1",
        "username": "Salvador Martinha"
      },
      ... ...
    ]
  }
}
</pre>
<br/>

<h4 id="post-product-follower">Add Product Follower</h4>
HTTP Method: POST
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/follow


Payload Example
<pre>
{
  "product_id": 30,
  "user_id": 1
}
</pre>

Response Example
<pre>
{
  "code": 201,
  "status": "Created",
  "message": "User is now following this product",
  "data": {
    "user_id": 1,
    "product_id": 30
  }
}
</pre>
<br/>

<h4 id="delete-product-follower">Delete Product Follower</h4>
HTTP Method: POST
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/unfollow

Payload Example
<pre>
{
  "product_id": 30,
  "user_id": 1
}
</pre>

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Unfollow with success",
  "data": null
}
</pre>
<br/>

<h4 id="get-product-comments">Get Product Comments</h4>
HTTP Method: GET
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/comments/:product_id

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Product's comments retrieved with success",
  "data": {
    "id": "30",
    "name": "Footbal Boot",
    "description": "Adidas Footbal Boot",
    "price": "120.00",
    "comments": [
      {
        "id": "7",
        "comment": "amazing boots",
        "updated_at": "2015-06-16 00:58:22",
        "user": {
          "id": "5",
          "username": "miguel",
          "image": "user/5/image.png"
        },
        ... ...
      }
    ]
  }
}
</pre>
<br/>

<h4 id="post-product-comment">Add Product Comment</h4>
HTTP Method: POST
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/comment

Payload Example
<pre>
{
  "user_id": 1,
  "product_id": 30,
  "comment": "Greate"
}
</pre>

Response Example
<pre>
{
  "code": 201,
  "status": "Created",
  "message": "Comment created with success",
  "data": {
    "id": "9"
  }
}
</pre>
<br/>

<h4 id="get-product-wishlists">Get Product Wishlists</h4>
HTTP Method: GET
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/wishlists/:product_id

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Product's wishlists retrieved with success",
  "data": {
    "id": "30",
    "name": "Footbal Boot",
    "description": "Adidas Footbal Boot",
    "price": "120.00",
    "wishlists": [
      {
        "id": "18",
        "user_id": "5",
        "name": "shoes",
        "is_public": "1"
      }
    ]
  }
}
</pre>
<br/>

<h4 id="get-product-promotions">Get Product Promotions</h4>
HTTP Method: GET
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/promotions/:product_id

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Product's wishlists retrieved with success",
  "data": {
    "id": "30",
    "name": "Footbal Boot",
    "description": "Adidas Footbal Boot",
    "price": "120.00",
    "promotions": []
  }
}
</pre>
<br/>

<h4 id="get-product-scans">Get Product Scans</h4>
HTTP Method: GET
<br/>
Endpoint: http://wizzyshop.eddmi.com/index.php/api/product/scans/:product_id

Response Example
<pre>
{
  "code": 200,
  "status": "OK",
  "message": "Product's scans retrieved with success",
  "data": {
    "id": "30",
    "name": "Footbal Boot",
    "description": "Adidas Footbal Boot",
    "price": "120.00",
    "scans": [
      {
        "id": "2"
      }
    ]
  }
}
</pre>
<br/>