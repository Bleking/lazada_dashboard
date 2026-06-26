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


## 구련한 차트 5종


## AI 챗봇 테스트 결과 (질문 5개 + 답변 스크린샷)


## 어려웠던 점 & 해결 방법
