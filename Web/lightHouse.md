# LightHouse

LightHouse는 google에서 제공하는 품질 개선 자동화 도구이다

성능, 접근성, SEO 측면에서 도움을 줄 수 있다

LightHouse 크롬 익스텐션을 다운로드하여 검사를 진행하면 검사 결과를 json, html 등으로 저장할 수 있다

- 성능 : 성능은 6가지 기준으로 검사된다
  - 메인 스레드 작업 최소화
  - JS 실행시간 감소
  - 사용하지 않는 코드 삭제
  - javascript payload 감소시키기
- 예상치 못한 레이아웃 이동
  - 내 경우에는 이미지의 원래 사이즈가 아닌 사이즈를 지정하여 점수가 줄어들었다

## SEO 평가

패이지가 검색 엔진 순위에 최적화 되어있는지 여부를 검사한다

- title 요소
- `<meta name="description">`
- 링크에 대한 명확한 텍스트
- 유효한 언어 설정
- 유효한 표준 링크
- 이미지 요소의 alt 속성
