# 구현할 기능

---
## 세 자리 숫자 생성 편의 클래스를 만든다.
- 세 자리 숫자는 다음 규칙을 지키고 이를 확인하기 위한 메서드를 제공한다.
    - 각 자리의 수는 1부터 9까지다.
    - 각 자리의 수는 서로 다른 수이다.
    - 숫자는 반드시 세자리여야 한다.
- 세 자리 숫자를 만드는 방법은 두 가지다.
    1. 사용자로부터 입력받는 방법
        - `camp.nextstep.edu.missionutils`에서 제공하는 `Console`의  `readLine()`을 활용한다.
    2. 랜덤으로 생성하는 방법
        - `camp.nextstep.edu.missionutils`에서 제공하는 `Randoms` 의 `pickNumberInRange()`를 활용한다.


## Player 도메인을 구축한다.
- 세 자리 숫자를 담는 도메인


## GameResult 도메인을 구축한다.
- 게임 결과(Ball수, Strike수)를 담는 도메인
- 관련 편의 메서드를 제공한다.
    - 게임 결과 출력 메서드
        - 입력한 수에 대한 결과를 볼, 스트라이크 개수로 표시
        - `1볼 1스트라이크`
        - 하나도 없는 경우
        - `낫싱`
        - 3개의 숫자를 모두 맞힐 경우
        - `3스트라이크\n3개의 숫자르 모두 맞히셨습니다! 게임 종료`
    - 게임 결과 판정 메서드
        - Strike 수가 세 개라면 게임을 종료시킬 수 있도록 작성한다.


## Application 클래스는 게임을 진행하는 로직을 맡는다.
- 게임 시작 문구를 출력한다.
    - `숫자 야구 게임을 시작합니다.`
- 컴퓨터 플레이어를 생성한다.
    - 랜덤한 숫자 3개를 갖는다.
    -  `Player` 타입으로 만들고, 숫자를 생성할 때는 `NumberUtil` 을 이용한다.
- 사용자 플레이어를 생성한다.
    - 사용자로부터 숫자 3개를 입력받는다.
    - 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료한다.
    -   `Player` 타입으로 만들고, 숫자를 생성할 때는 `NumberUtil` 을 이용한다.
- 게임을 진행한다.
    - 게임 진행 후 `GameResult` 도메인을 이용하여 결과 출력 및 승부 판정을 한다.
    - 유저 플레이어가 진 경우, 새로운 숫자를 입력받고 게임을 반복한다.
    - 유저 플레이어가 이긴 경우 재시작/종료 여부를 묻는다.
    - `게임을 새로 시작하려면 1, 종료하려면 2를 입력하세요.`
    - 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료한다.