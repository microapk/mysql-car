# 데이터베이스 2025

https://nano5.notion.site/Spring-Data-JPA-MySQL-1abdaf211d42817581b9e3dd2ed9d21f?pvs=4

```mermaid
erDiagram
    Manufacturer ||--o{ Car : "제조"
    Car ||--o{ RecentSearch : "검색"

    Manufacturer {
        BIGINT manufacturer_id PK "제조사 ID"
        VARCHAR name "제조사명"
        VARCHAR country "국가"
    }

    Car {
        BIGINT car_id PK "자동차 ID"
        VARCHAR name "모델명"
        BIGINT manufacturer_id FK "제조사 ID"
        INT release_year "출시 연도"
        INT price_min "최소 가격"
        INT price_max "최대 가격"
        ENUM fuel_type "연료 종류"
        ENUM car_size "차종"
        BOOL heated_seat "열선 시트"
        BOOL cooling_seat "통풍 시트"
        BOOL auto_drive "자율 주행"
    }

    RecentSearch {
        BIGINT search_id PK "검색 ID"
        BIGINT user_id "사용자 ID"
        BIGINT car_id FK "자동차 ID"
        DATETIME searched_at "검색 시각"
    }
