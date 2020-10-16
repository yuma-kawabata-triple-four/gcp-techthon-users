##  商品在庫詳細API [/stock/{id}]

### 商品在庫詳細 [GET]

#### 処理概要

* 商品在庫テーブルから、urlの{id}と同じidを持つ商品在庫情報を返却する
* 商品在庫テーブルに、urlの{id}と同じidを持つ商品在庫情報が存在していなかった場合、Response 404 を返却する

+ Parameters
    + id: 1 (number, required) - 在庫商品ID

+ Response 200 (application/json)
    + Attributes
        + status_code: 200 (number, required) 
        + method: GET (string, required)
        + data (object)
            + id: 1 (number, required) 
            + name: pen (string) 
            + price: 100 (number) 
            + on_sale: true (boolean) 
            + stock: 100 (number) 
            + discount: 0 (number) 
            
+ Response 404 (application/json)
    + Attribute
        + status_code: 404 (number, required) 
        + method: POST (string, required)


##  商品在庫一覧API [/stock/list{?min_stock}]

### 商品在庫一覧 [GET] 

#### 処理概要

* Stockテーブルから、条件に一致する商品在庫一覧を返却する
* min_stockは非必須項目。指定された際、在庫(stock)がこの数値以上存在しているものを返却する

+ Parameters
    + min_stock: 10 (number, optional) - 最小商品在庫数

+ Response 200 (application/json)
    + Attributes
        + status_code: 200 (number, required) 
        + method: POST (string, required)


##  商品在庫登録API [/stock/create]

### 商品在庫登録 [POST] 

#### 処理概要

* Stockテーブルに、新しくデータを登録する
* 新規データ登録時に、すでに登録したデータとidが重複した場合、400を返却する

+ Request (application/json)
    + Headers
        Accept: application/json
    + Attributes
        + id: 2 (number, required) - 商品在庫id
        + name: chocolate (string, required) - 商品在庫名称
        + price: 200 (number, required) - 商品在庫価格
        + on_sale: true (boolean, required) - 商品在庫販売可否
        + stock: 100 (number, optional) - 商品在庫数
        + discount: 0 (number, optional) - 商品在庫値引き額

+ Response 200 (application/json)
    + Attributes
        + status_code: 200 (number, required) 
        + method: POST (string, required)

+ Response 400 (application/json)
    + Attributes
        + status_code: 400 (number, required) 
        + method: POST (string, required)

##  商品在庫一括登録API [/stock/items/create]

### 商品在庫一括登録 [POST] 

#### 処理概要

* Stockテーブルに、新しくデータを一括登録する
* items として送られてきたリストのデータをDBにすべて登録する

+ Request (application/json)
    + Headers
        Accept: application/json
    + Attributes
        + items (array)
            + (object)
                + id: 2 (number, required) - 商品在庫id
                + name: chocolate (string, required) - 商品在庫名称
                + price: 200 (number, required) - 商品在庫価格
                + on_sale: true (boolean, required) - 商品在庫販売可否
                + stock: 100 (number, optional) - 商品在庫数
                + discount: 0 (number, optional) - 商品在庫値引き額

+ Response 200 (application/json)
    + Attributes
        + status_code: 200 (number, required) 
        + method: POST (string, required)


##  商品在庫更新API [/stock/update/{id}]

### 商品在庫更新 [POST] 

#### 処理概要

* Stockテーブルの{id}が一致するデータを更新する
* {id} が存在している場合は更新して200を返却, 存在していない場合は400を返却する

+ Parameters
    + id: 1 (number, required) - 在庫商品ID

+ Request (application/json)
    + Headers
        Accept: application/json
    + Attributes
        + name: chocolate (string, optional) - 商品在庫名称
        + price: 200 (number, optional) - 商品在庫価格
        + on_sale: true (boolean, optional) - 商品在庫販売可否
        + stock: 100 (number, optional) - 商品在庫数
        + discount: 0 (number, optional) - 商品在庫値引き額

+ Response 200 (application/json)
    + Attributes
        + status_code: 200 (number, required) 
        + method: POST (string, required)

+ Response 400 (application/json)
    + Attributes
        + status_code: 400 (number, required) 
        + method: POST (string, required)


##  商品在庫削除API [/stock/update/{id}]

### 商品在庫削除 [POST] 

#### 処理概要

* Stockテーブルの{id}が一致するデータを削除する
* {id} が存在している場合は削除して200を返却, 存在していない場合は400を返却する

+ Parameters
    + id: 1 (number, required) - 在庫商品ID

+ Request (application/json)
    + Headers
        Accept: application/json
    + Attributes

+ Response 200 (application/json)
    + Attributes
        + status_code: 200 (number, required) 
        + method: POST (string, required)

+ Response 400 (application/json)
    + Attributes
        + status_code: 400 (number, required) 
        + method: POST (string, required)




