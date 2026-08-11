# AOZ 클론 코딩 수정 내역 요약 (index.html)

이 문서는 `index.html` 파일에서 최근 수정 및 개선된 항목들을 정리한 노트입니다. 내용을 확인하시고 이해하셨다면 자유롭게 삭제하셔도 됩니다.

---

## 1. 언어 설정 2차 메뉴 구조 개선 (`user-item04`)

* **기존 코드 (오류):**
  ```html
  <li class="user-item user-item04"><a href="#" title="언어설정">
      <img src="./image/Language.svg" alt="Language">
      <div>한국어
  </a></li>
  ```
  * `<div>` 태그가 닫히지 않았음 (`</div>` 누락).
  * `<a>` 태그 내부로 `<div>`가 잘못 포함되어 `style.css`의 `.user-item04 > div` 직계 자식 선택자(Direct Child Selector)에 선택되지 않음.

* **수정 후 (정상):**
  ```html
  <li class="user-item user-item04">
      <a href="#" title="언어설정">
          <img src="./image/Language.svg" alt="Language">
      </a>
      <div>한국어</div>
  </li>
  ```
  * `<a>` 태그와 `<div>` 태그를 `<li>` 안에서 나란히 분리하여 HTML 구조 안정성 확보.
  * `.user-item04 > div` 선택자가 `<div>한국어</div>`를 정확하게 가리키게 되어 마우스 호버 시 2차 메뉴가 정상 노출됨.

---

## 2. 브랜드 소개 섹션 줄바꿈 태그 표준화 (`section02`)

* **기존 코드 (오류):**
  ```html
  AOZ는 FRAGRANCE SPACE 라는</br>
  ```
  * `</br>` 형태는 올바른 HTML 빈 태그(Void element) 표기법이 아님.

* **수정 후 (정상):**
  ```html
  AOZ는 FRAGRANCE SPACE 라는<br>
  ```
  * 표준 HTML 줄바꿈 태그인 `<br>`로 올바르게 수정됨.

---

## 3. 일반상품 리스트 클래스명 고유화 (`section05`)

* **기존 코드 (오류):**
  ```html
  <div class="product01">1</div>
  <div class="product02">2</div>
  <div class="product03">3</div>
  <div class="product04">4</div>
  <div class="product04">5</div> <!-- 중복 -->
  <div class="product04">6</div> <!-- 중복 -->
  ...
  ```
  * 5번~12번 상품 카드의 클래스명이 모두 `product04`로 동일하게 중복 작성됨.

* **수정 후 (정상):**
  ```html
  <div class="product01">1</div>
  <div class="product02">2</div>
  <div class="product03">3</div>
  <div class="product04">4</div>
  <div class="product05">5</div>
  <div class="product06">6</div>
  <div class="product07">7</div>
  <div class="product08">8</div>
  <div class="product09">9</div>
  <div class="product010">10</div>
  <div class="product011">11</div>
  <div class="product012">12</div>
  ```
  * 각 상품 아이템마다 고유한 클래스명(`product05` ~ `product012`)이 부여되어 향후 개별 스타일 지정 시 용이해짐.
