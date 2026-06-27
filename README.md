# lazada_dashboard
인공지능사관학교 7기 Lazada 대시보드 프로젝트

## 프로젝트 소개
싱가포르의 온라인 쇼핑 업체인 라자다의 상품 데이터를 SQLite DB에 저장하고, 

Text-to-SQL 가드레일을 통해 SQL 실행 결과를 LLM 출력으로 자연어로 표현하고 

Gradio를 통해 사용자 친화적 대시보드를 만드는 프로젝트

## 데이터 정제 전후 비교
1) 모든 환율을 가장 많이 있던 인도네시아 루피아로(IDR) 변환
2) 색상 관련: 색상 목록(colors), 그리고 해당 제품의 색상(color) 열의 빈칸은 모두 NULL로 채움
3) 평점 관련: 판매자 평점(seller_ratings), 정시 배송률(seller_ship_on_time), 채팅 응답률(seller_chat_response) 열의 빈칸은 모두 NULL로 채움

## ERD 다이어그램
<img width="938" height="592" alt="image" src="https://github.com/user-attachments/assets/7307f2aa-e4da-4e24-b501-d7f544da4547" />


## 구련한 차트 5종
1. 총 상품 수, 총 셀러 수, 총 GMV, 평균 평점 차트
   
   <img width="1111" height="70" alt="image" src="https://github.com/user-attachments/assets/76cfd330-38af-464b-8333-e166f24b9b8b" />

2. 카테고리별 매출 TOP 10

   <img width="553" height="308" alt="image" src="https://github.com/user-attachments/assets/4d99fcf9-97b2-471f-acdc-f503597b357b" />

3. 슈퍼셀러 vs 일반셀러 비교 (그룹 막대)

   <img width="551" height="307" alt="image" src="https://github.com/user-attachments/assets/6169912a-b84a-4a48-8317-f9737360e4bb" />

4. 평점 분포 히스토그램

   <img width="553" height="304" alt="image" src="https://github.com/user-attachments/assets/944b90c5-7d40-4101-9555-21a29abed732" />

5. 베스트셀러 TOP 10 (테이블)

<img width="558" height="346" alt="image" src="https://github.com/user-attachments/assets/6abfbec9-94f0-4b82-993d-9aa23cbf0c51" />

## AI 챗봇 테스트 결과 (질문 5개 + 답변 스크린샷)

screenshot 폴더 참고

1. "가장 비싼 상품 5개 보여줘"

<img width="1109" height="208" alt="Lazada 관리자 대시보드 답변 1" src="https://github.com/user-attachments/assets/606df4d8-1e3a-4e97-bb30-a8c1f372bed1" />


2. "슈퍼셀러 중 매출이 가장 높은 셀러는?"

<img width="1112" height="182" alt="Lazada 관리자 대시보드 답변 2" src="https://github.com/user-attachments/assets/d31bc4eb-1cf8-4ee3-be57-6356ba93f7fa" />

3. "카테고리별 평균 평점이 가장 높은 카테고리는?"

<img width="1115" height="184" alt="Lazada 관리자 대시보드 답변 3" src="https://github.com/user-attachments/assets/6e382f92-cd3b-42d0-9c73-cf84478ddf10" />

4. "평점이 4.5 이상이면서 100건 이상 팔린 상품의 수"

<img width="1115" height="242" alt="Lazada 관리자 대시보드 답변 4" src="https://github.com/user-attachments/assets/9fdf0544-a2a6-4c6a-9d2e-c8b065b27a75" />

5. "Xiaomi 브랜드 상품의 평균 가격과 총 판매수량"

<img width="1113" height="380" alt="Lazada 관리자 대시보드 답변 5" src="https://github.com/user-attachments/assets/665422bf-e985-4826-bea6-3a908163540e" />


## 어려웠던 점 & 해결 방법
1. Gradio UI의 챗봇에서 질문이 쌓일 때마다 출력 답변에 이전 질문의 답변이 축적되어 출력되는 현상
   
   -> 해결 방안: history가 축적되고, 그것이 또 출력되는 것이 원인이었던 관계로 history 자체를 저장하지 않도록 함
