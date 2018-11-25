# Pokemon Book API



## 모든 포켓몬 조회

| 메소드 | 경로                                         | 설명             |
| ------ | -------------------------------------------- | ---------------- |
| GET    | /pokemons?offset={page_no}&limit={page_size} | 모든 포켓몬 조회 |

#### QueryString 설명

| Parameter |              설명              |   예시   |   값 범위   |
| :-------: | :----------------------------: | :------: | :---------: |
|  offset   |     시작 번호(기본값 = 0)      | offset=0 | 0 이상 정수 |
|   limit   | 가져올 데이터 갯수(기본값 = 3) | limit=3  | 1 이상 정수 |





### 요청 헤더

```http
Content-Type : application/json
```



### 응답 바디

#### 포켓몬 조회 성공

```json
{
    "status" : 200,
    "message" : "조회 성공",
    "data" : [
        {
            "pokemon_id" : 1,
            "pokemon_name" : "피카츄",
            "pokemon_type" : "번개",
            "pokemon_photo" : "사진 객체"
        },
        {
            "pokemon_id" : 2,
            "pokemon_name" : "파이리",
            "pokemon_type" : "불",
            "pokemon_photo" : "사진 객체"
        },
        {
            "pokemon_id" : 3,
            "pokemon_name" : "꼬부기",
            "pokemon_type" : "물",
            "pokemon_photo" : "사진 객체"
        }
    ]
}
```

#### 포켓몬 조회 실패

```json
{
    "status" : 400,
    "message" : "조회 실패",
    "data" : null
}
```

#### DB 에러

```json
{
    "status" : 600,
    "message" : "데이터베이스 에러",
    "data" : null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status" : 500,
    "message" : "서버 내부 에러",
    "data" : null
}
```





## 포켓몬 조회

| 메소드 | 경로                   | 설명        |
| ------ | ---------------------- | ----------- |
| GET    | /pokemons/{pokemon_id} | 포켓몬 조회 |



### 요청 헤더

```http
Content-Type : application/json
```



### 응답 바디

#### 포켓몬 조회 성공

```json
{
    "status" : 200,
    "message" : "조회 성공",
    "data" : {
        "pokemon_id" : 1,
        "pokemon_name" : "피카츄",
        "pokemon_type" : "번개",
        "pokemon_photo" : "사진 객체"
    }
}
```

#### 포켓몬 조회 실패

```json
{
    "status" : 400,
    "message" : "조회 실패",
    "data" : null
}
```

#### DB 에러

```json
{
    "status" : 600,
    "message" : "데이터베이스 에러",
    "data" : null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status" : 500,
    "message" : "서버 내부 에러",
    "data" : null
}
```





## 포켓몬 등록

| 메소드 |   경로    |    설명     |
| :----: | :-------: | :---------: |
|  POST  | /pokemons | 포켓몬 등록 |



### 요청 헤더

```http
Content-Type : multipart/form-data
```



### 요청 바디

```json
{
    "pokemon_name" : "피카츄",
    "pokemon_type" : "번개",
    "pokemon_photo" : "사진 객체"
}
```



### 응답 바디

#### 포켓몬 등록 성공

```json
{
    "status" : 201,
    "message" : "등록 성공",
    "data" : {
        "pokemon_id" : 1,
        "pokemon_name" : "피카츄",
        "pokemon_type" : "번개",
        "pokemon_photo" : "사진 객체"
    }
}
```

#### 포켓몬 등록 실패

```json
{
    "status" : 400,
    "message" : "등록 실패",
    "data" : null
}
```

#### DB 에러

```json
{
    "status" : 600,
    "message" : "데이터베이스 에러",
    "data" : null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status" : 500,
    "message" : "서버 내부 에러",
    "data" : null
}
```





## 포켓몬 수정

| 메소드 |          경로          |    설명     |
| :----: | :--------------------: | :---------: |
|  PUT   | /pokemons/{pokemon_id} | 포켓몬 수정 |



### 요청 헤더

```http
Content-Type : multipart/form-data
```



### 요청 바디

```json
{
    "pokemon_name" : "피카츄",
    "pokemon_type" : "번개",
    "pokemon_photo" : "사진 객체"
}
```



### 응답 바디

#### 포켓몬 수정 성공

```json
{
    "status" : 200,
    "message" : "수정 성공",
    "data" : {
        "pokemon_id" : 1,
        "pokemon_name" : "피카츄",
        "pokemon_type" : "번개",
        "pokemon_photo" : "사진 객체"
    }
}
```

#### 포켓몬 수정 실패

```json
{
    "status" : 400,
    "message" : "수정 실패",
    "data" : null
}
```

#### DB 에러

```json
{
    "status" : 600,
    "message" : "데이터베이스 에러",
    "data" : null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status" : 500,
    "message" : "서버 내부 에러",
    "data" : null
}
```





## 포켓몬 삭제

| 메소드 |          경로          |    설명     |
| :----: | :--------------------: | :---------: |
| DELETE | /pokemons/{pokemon_id} | 포켓몬 삭제 |



### 요청 헤더

```http
Content-Type : application/json
```



### 응답 바디

#### 포켓몬 삭제 성공

```json
{
    "status" : 200,
    "message" : "삭제 성공",
    "data" : null
}
```

#### 포켓몬 삭제 실패

```json
{
    "status" : 400,
    "message" : "삭제 실패",
    "data" : null
}
```

#### DB 에러

```json
{
    "status" : 600,
    "message" : "데이터베이스 에러",
    "data" : null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status" : 500,
    "message" : "서버 내부 에러",
    "data" : null
}
```