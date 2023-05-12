# 미션 - 워들

## 🔍 진행 방식

- 미션은 **기능 요구 사항, 프로그래밍 요구 사항, 과제 진행 요구 사항** 세 가지로 구성되어 있다.
- 세 개의 요구 사항을 만족하기 위해 노력한다. 특히 기능을 구현하기 전에 기능 목록을 만들고, 기능 단위로 커밋 하는 방식으로 진행한다.
- 기능 요구 사항에 기재되지 않은 내용은 스스로 판단하여 구현한다.

---

## 🚀 기능 요구 사항

선풍적인 인기를 끌었던 영어 단어 맞추기 게임이다.

- 6x5 격자를 통해서 5글자 단어를 6번 만에 추측한다.
- 플레이어가 답안을 제출하면 프로그램이 정답과 제출된 단어의 각 알파벳 종류와 위치를 비교해 판별한다.
- 판별 결과는 흰색의 타일이 세 가지 색(초록색/노란색/회색) 중 하나로 바뀌면서 표현된다.
   - 맞는 글자는 초록색, 위치가 틀리면 노란색, 없으면 회색
   - 두 개의 동일한 문자를 입력하고 그중 하나가 회색으로 표시되면 해당 문자 중 하나만 최종 단어에 나타난다.
- 정답과 답안은 `words.txt`에 존재하는 단어여야 한다.
- 정답은 매일 바뀌며 ((현재 날짜 - 2021년 6월 19일) % 배열의 크기) 번째의 단어이다.

### 입출력 요구 사항

#### 실행 결과 예시

```
WORDLE을 6번 만에 맞춰 보세요.
시도의 결과는 타일의 색 변화로 나타납니다.
정답을 입력해 주세요.
hello

⬜⬜🟨🟩⬜

정답을 입력해 주세요.
label

⬜⬜🟨🟩⬜
🟨⬜⬜⬜🟩

정답을 입력해 주세요.
spell

⬜⬜🟨🟩⬜
🟨⬜⬜⬜🟩
🟩🟩⬜🟩🟩

정답을 입력해 주세요.
spill

4/6

⬜⬜🟨🟩⬜
🟨⬜⬜⬜🟩
🟩🟩⬜🟩🟩
🟩🟩🟩🟩🟩
```
## 📄기능 목록

### 도메인
#### 게임
 - [x] 시도 회수를 다 사용하면 게임은 패배한다.
 - [x] 게임 한 턴 당 결과를 계산 및 저장한다

#### 문제
 - [x] words.txt 안에 존재해야한다.
   - [x] 문제는 매일 바뀌어야한다.
   - [x] ((현재 날짜 - 2021년 6월 19일) % 단어 전체의 개수) 번째의 단어
 - [x] 정답을 맞추면 true, 틀리면 false 를 반환한다.
 - [x] 힌트를 반환한다
   - [x] 처음 Green 을 검사한다.(같은 인덱스와의 문자 검사)
     - [x] Green이 맞으면 정답과 입력에서 해당 값을 빈 걸로 치환한다.
   - [x] 순회하면서 나머지를 검사한다.
     - [x] Yello가 맞으면 정답과 입력에서 해당 값을 빈 걸로 치환한다.
   
#### 시도 회수
 - [x] 시도 회수는 총 6번 주워진다.
 - [x] 몇 번 시도하였는지를 저장한다.

### 입력
 - [x] 정답을 입력받는다. 
 - [x] 사용자가 5글자를 입력하지 않으면 재입력을 요구한다.
 - [x] 사용자가 영어 이외의 글자를 입력하면 재입력을 요구한다.
 - [x] word.txt 안에 존재하는 단어를 입력하지 않으면 재입력을 요구한다. 

### 출력
 - [x] 타일에는 초록색/노란색/회색이 존재한다
 - [x] 최종 시도 횟수를 출력한다.

