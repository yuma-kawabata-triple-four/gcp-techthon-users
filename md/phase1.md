## GET/POST疎通確認 [/check]

### GET疎通確認API [GET]

#### 処理概要

* GETの正しい情報を返せているかを確認する
* GETのrequestに対して、ステータスコード 200とメソッド名を返却する

+ Parameters

+ Response 200 (application/json)
    + Attributes
        + api_status_code: 200 (number, required) 
        + method: GET (string, required)
        
        
### POST疎通確認API [POST]

#### 処理概要

* POSTの正しい情報を返せているかを確認する
* POSTのrequestに対して、ステータスコード 200とメソッド名を返却する

+ Parameters

+ Response 200 (application/json)
    + Attributes
        + api_status_code: 200 (number, required) 
        + method: POST (string, required)
