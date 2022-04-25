## Spring-JPA01

### 사용 기술 

Spring Boot, JPA, H2 DB


###  웹사이트 기능 

 - 사용자 회원가입
 - 상품 등록, 재고 확인
 - 상품 주문
 - 주문 조회, 취소

###  API 서버 기능

 - @GetMapping("api/members")    
 회원 정보 조회
<pre><code>응답 예시

{
    "count": 2,
    "data": [
        {
            "name": "memberA"
        },
        {
            "name": "memberB"
        }
    ]
}
</code></pre>
<hr>

 - @PostMapping("/api/members")    
 회원 가입  
<pre><code>요청 예시

{
    "name":"memberC"
}
</code></pre>

<pre><code>응답 예시

{
    "id": 15
}
</code></pre>
<hr>

 - @PutMapping("/api/members/{id}")   
 회원 정보 수정
<pre><code>요청 예시
/api/members/1

{
    "name":"memberNew"
}
</code></pre>

<pre><code>응답 예시

{
    "id": 1,
    "name": "memberNew"
}
</code></pre>
<hr>

 - @GetMapping("api/simple-orders")
<pre><code>응답 예시

[
    {
        "orderId": 4,
        "name": "memberNew",
        "orderDate": "2022-04-25T22:19:25.56284",
        "orderStatus": "ORDER",
        "address": {
            "city": "서울",
            "street": "상도로 147",
            "zipcode": "480-713"
        }
    },
    {
        "orderId": 11,
        "name": "memberB",
        "orderDate": "2022-04-25T22:19:25.667892",
        "orderStatus": "ORDER",
        "address": {
            "city": "부산",
            "street": "해운대로 48",
            "zipcode": "480-713"
        }
    }
]
</code></pre>
<hr>

 - @GetMapping("api/orders")

<pre><code>응답 예시

[
    {
        "orderId": 4,
        "name": "memberNew",
        "orderDate": "2022-04-25T22:19:25.56284",
        "orderStatus": "ORDER",
        "address": {
            "city": "서울",
            "street": "상도로 147",
            "zipcode": "480-713"
        },
        "orderItems": [
            {
                "itemName": "JPA1 BOOK",
                "orderPrice": 10000,
                "count": 1
            },
            {
                "itemName": "JPA2 BOOK",
                "orderPrice": 20000,
                "count": 2
            }
        ]
    },
    {
        "orderId": 11,
        "name": "memberB",
        "orderDate": "2022-04-25T22:19:25.667892",
        "orderStatus": "ORDER",
        "address": {
            "city": "부산",
            "street": "해운대로 48",
            "zipcode": "480-713"
        },
        "orderItems": [
            {
                "itemName": "SPRING1 BOOK",
                "orderPrice": 20000,
                "count": 3
            },
            {
                "itemName": "SPRING2 BOOK",
                "orderPrice": 40000,
                "count": 4
            }
        ]
    }
]
</code></pre>
<hr>

 - @GetMapping("api/orders?offset={offset}&?limit={limit}")
<pre><code>응답 예시
 /api/orders?offset=1&?limit=10

[
    {
        "orderId": 11,
        "name": "memberB",
        "orderDate": "2022-04-25T22:19:25.667892",
        "orderStatus": "ORDER",
        "address": {
            "city": "부산",
            "street": "해운대로 48",
            "zipcode": "480-713"
        },
        "orderItems": [
            {
                "itemName": "SPRING1 BOOK",
                "orderPrice": 20000,
                "count": 3
            },
            {
                "itemName": "SPRING2 BOOK",
                "orderPrice": 40000,
                "count": 4
            }
        ]
    }
]
</code></pre>
<hr>
