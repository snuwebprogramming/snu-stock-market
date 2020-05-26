# snu-stock-market

## snu stock market에 오신걸 환영합니다. 이 마켓은 코스피를 추종하는 snu-코스피 상품과, 나스닥을 추종하는 snu-나스닥 상품. 두가지를 판매하고 있습니다. 여러분은 두 주식을 사고 팔 수 있는 웹 클라이언트를 제작해야 합니다.


# 서버

서버는 다음과 같은 api 를 제공합니다.

## /login [:post]

### request

- id
- password

* 코드 아카데미 계정 주소를 전송했던 이메일 주소로 각자의 id,password가 전송될 것입니다.

### response

- key
로그인이 성공할 때마다, key가 변경되서 제공 됩니다.

## /order_books [:GET]

### request

- code
* kospi, nasdaq 두 값 중 하나를 입력하시면 됩니다.

### response

[
  orderBook: {price, quantity, side},
  orderBook: {price, quantity, side},
  ...
]

* orderBook는 가장 최근 거래 가 기준으로, 최대 10개까지 제공됩니다. side는 buy, sell 두 개만 존재합니다.


## /order [:post] :auth_required

### request
- price
- quantity
- side

* 구매/판매를 요청합니다.

### response
{orderId, price, quantity, side}

* 성공한 오더 객체를 전송합니다.


## /orders [:get]  :auth_required

본인이 요청한 order 목록을 요청합니다.

##

