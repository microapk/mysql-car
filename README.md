# 데이터베이스 2025


```mermaid
erDiagram
    Car {
        INT car_id PK
        VARCHAR name
        INT release_year
        VARCHAR manufacturer_name
        VARCHAR manufacturer_country
        INT price_min
        INT price_max
        VARCHAR fuel_type
        VARCHAR car_size
        TINYINT heated_seat
        TINYINT cooling_seat
        TINYINT auto_drive
    }

    UsedCar {
        INT used_car_id PK
        VARCHAR car_model_name
        VARCHAR manufacturer_name
        VARCHAR manufacturer_country
        INT year
        INT mileage
        INT price
        VARCHAR used_condition
        VARCHAR fuel_type
        VARCHAR car_size
        TINYINT heated_seat
        TINYINT cooling_seat
        TINYINT auto_drive
    }

    Comparison {
        INT comparison_id PK
        INT user_id
        INT car_id FK
        INT used_car_id FK
        DATETIME compared_at
    }

    Comparison }o--|| Car : "compares new car"
    Comparison }o--|| UsedCar : "compares used car"
