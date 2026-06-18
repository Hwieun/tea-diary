# 차 그림일기

차를 마신 뒤 다구를 고르고 색·맛·기분·함께한 사람을 적어 그림일기 카드로 간직하는 폰 전용 앱.

**데모:** https://hwieun.github.io/tea-diary/

## 목적

기능 완성이 아니라 **"이 서비스가 살아있으려면 어디로 가야 하는가"를 학습**하기 위한 MVP.
무빌드 단일 `index.html` + localStorage. 의존성 0, 빌드 0.

## Generative Sequence

각 단계가 그 자체로 완결된 '살아있는 전체'이며, 다음 단계가 이전을 보존하며 펼쳐진다.

- **Step 0–2 (현재):** 다구 선택 + 색·맛·기분·사람 기록 → localStorage 저장 → 타임라인으로 돌아보기. (기본 삭제 포함)
- Step 3: 카드 편집.
- Step 4: 이모지 → 손그림풍 SVG 다구 세트, 배치.
- Step 5: JSON 내보내기 (데이터 유실 방어).

## 데이터 모델

```js
TeaCard = {
  id, teaware: string[],
  color, taste, mood, withWhom,   // 빈 값 허용
  createdAt, updatedAt            // 연속성·재방문 관찰용 흔적
}
```

`localStorage["tea-cards"]` 에 배열로 보관. 이 기기 로컬 유일본.

## 로컬에서 보기

빌드 없음. 파일을 브라우저로 열거나:

```
python3 -m http.server 8000   # → http://localhost:8000
```
