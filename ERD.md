# 🍀 LuckEat - ERD 및 데이터베이스 구조  

LuckEat의 데이터베이스는 **마감할인 음식 및 예약 시스템을 효율적으로 관리**하도록 설계되었습니다.  

📌 **🔗 [ERD 확인하기 (ErdCloud)](https://www.erdcloud.com/d/tjEgEhZSnD3CGidce)**  

---

## **📌 ERD 다이어그램**  
![LuckEat ERD](ERD_이미지_URL_삽입)  

---

## **📌 주요 테이블 정의**  

### **🛍 users (사용자 테이블)**  
- `id` - 회원 ID  
- `role` - 회원 역할 (`buyer`, `seller`, `admin`)  
- `email` - 이메일  
- `password` - 암호화된 비밀번호  
- `nickname` - 닉네임 (고유값)  
- `created_at`, `updated_at`, `deleted_at`  

### **🏪 store (가게 테이블)**  
- `id` - 가게 ID  
- `user_id` - 가게 소유 회원 ID  
- `category_id` - 가게 카테고리 ID  
- `store_name` - 가게 이름  
- `address` - 주소  
- `contact_number` - 전화번호  
- `latitude`, `longitude` - 위도/경도  
- `weekday_close_time`, `weekend_close_time` - 마감 시간  
- `created_at`, `updated_at`, `deleted_at`  

### **🍽 product (마감할인 상품 테이블)**  
- `id` - 상품 ID  
- `store_id` - 가게 ID  
- `product_name` - 상품명  
- `original_price`, `discounted_price` - 원가 및 할인 가격  
- `is_open` - 판매 여부  
- `created_at`, `updated_at`, `deleted_at`  

### **⭐ review (리뷰 테이블)**  
- `id` - 리뷰 ID  
- `user_id` - 작성자 ID  
- `store_id` - 리뷰 대상 가게 ID  
- `rating` - 평점 (0~5)  
- `review_content` - 리뷰 내용  
- `review_image` - 리뷰 이미지  
- `created_at`, `updated_at`, `deleted_at`  

### **🔑 review_permission (리뷰 권한 테이블)**  
- `id` - 권한 ID  
- `store_id` - 가게 ID  
- `user_id` - 리뷰 작성 권한을 부여받은 회원 ID  
- `created_at`, `updated_at`, `deleted_at`  

### **🗂 category (카테고리 테이블)**  
- `id` - 카테고리 ID  
- `category_name` - 카테고리명  
- `created_at`, `updated_at`, `deleted_at`  

### **🔑 sessions (세션 테이블)**  
- `id` - 세션 ID  
- `user_id` - 회원 ID  
- `data` - 세션 데이터  
- `created_at`, `updated_at`, `expires_at`  

---

📌 **🔗 [API 명세서 확인하기](API.md)**  

