##  商品在庫詳細API [/stock/{id}]

### 商品在庫詳細 [GET]

#### 処理概要

* 商品在庫テーブルから、urlの{id}と同じidを持つ商品在庫情報を返却する - Response①
* 商品在庫テーブルに、urlの{id}と同じidを持つ商品在庫情報が存在していなかった場合、api_status_code: 404 を返却する - Response②

+ Parameters
    + id: 1 (number, required) - 在庫商品ID

+ Response 200 (application/json)
    + Attributes - Response①
        + status_code: 200 (number, required)
        + method: GET (string, required)
        + data (object)
            + id: 2 (number, required) - 商品在庫id
            + name: chocolate (string, required) - 商品在庫名称
            + price: 200 (number, required) - 商品在庫価格
            + on_sale: true (boolean, required) - 商品在庫販売可否
            + stock: 100 (number, optional) - 商品在庫数
            + discount: 0 (number, optional) - 商品在庫値引き額
            
+ Response 200 (application/json)
    + Attribute - Response②
        + status_code: 404 (number, required) 
        + method: GET (string, required)
        + data: {}


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
