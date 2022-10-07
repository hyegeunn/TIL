# Redux 의 3가지 규칙
<br>

## **1.하나의 애플리케이션 안에는 하나의 스토어가 있다.**
<br>

### 여러개의 스토어를 사용하는것은 가능하나 권장하지는 않는다. 특정 업데이트가 너무 빈번하게 일어나거나 애플리케이션의 특정 부분을 완전히 분리시키게 될 때 여러개의 스토어를 만들수도 있다. 하지만 그렇게 하면 개발 도구를 활용하지 못한다.
<br><br>

## **2. 상태는 읽기전용 이다.**
<br>

### react 에서 state 를 업데이트 해야 할 때, `setState` 를 사용하고 배열을 업데이트 해야 할 때는 배열 자체에 push 를 직접 하지 않고 concat 같은 함수를 사용하여 새로운 배열을 만들어 교체하는 방식으로 업데이트를 한다. 깊은 구조로 되어있는 객체를 업데이트 할 때도 기존의 객체는 건들이지 않고 `Object.assign` 을 사용하거나 `spread(...)` 연산자를 사용하여 업데이트 한다.
<br>

### redux 에서도 마찬가지이다. 기존의 상태는 건들이지 않고 새로운 상태를 생성하여 업데이트 해주는 방식으로 해주면 나중에 개발자 도구를 통해 뒤로 돌릴 수도 있고 다시 앞으로 돌릴 수 있다.
<br>

### redux 에서 불변성을 유지해야 하는 이유는 `내부적으로 데이터가 변경 되는 것을 감지하기 위해 shallow equality 검사` 를 하기 때문 이다. 이를 통해 객체의 변화를 감지 할 때 객체의 안쪽까지 비교를 하는 것이 아니라 겉으로 비교를 하여 좋은 성능을 유지할 수 있다.
<br><br>

## **3. 변화를 일으키는 함수, reducer 의 순수한 함수여야 한다.**
<br>

### 순수한 함수란
- reducer 함수는 이전 상태와 액션 객체를 파라미터로 벋는다.
- 이전의 상태는 절대 건들이지 않고 변화를 일으킨 새로운 상태 객체를 만들어서 반환한다.
- 똑같은 파라미터로 호출된 reducer 함수는 `언제나 똑같은 결과값` 을 반환해야 한다.