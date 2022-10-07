# 자주 사용하는 keyword

## <span style="background-color:#959595">**Action**
<br>

### 상태에 어떠한 변화가 필요하게 될 때 액션을 발생시키고 하나의 객체로 표현된다.
<br>

```typescript
{
  type: "TOGGLE_VALUE"
}
```

### 액션 객체는 `type` 필드를 필수로 가지고 있어야하고 그 외의 값들은 마음대로 넣는다.
<br>

```typescript
{
  type: "LEARN_REDUX"
  data: {
    id: 1,
    text: "redux 배우기"
  }
}
```
<br><br>

## **Action Creator**
<br>

### 액션 생성함수는 액션을 만는 함수로 파라미터를 받아와서 액션 객체 형태로 만든다.
<br>

```typescript
export function learnRedux(data) {
  return {
    type: "LEARN_REDUX",
    data
  }
}

// 화살표 함수도 가능
export const learnRedux = text => ({
  type: "LEARN_REDUX",
  text
})
```
<br>

### 이러한 액션 생성함수를 만들어서 사용하는 이유는 나중에 컴포넌트에서 쉽게 액션을 발생시키기 위해서다.
### redux 를 사용 할 때 액션 생성함수를 사용하는것은 필수가 아니다.
<br><br>

## **Reducer**
<br>

### reducer 는 변화를 일으키는 함수로 두 가지의 파라미터를 받아온다.
<br>

```typescript
function reducer(statae, action) {
  // ... TODO
  return alteredState
}
```
<br>

### reducer 는 현재 상태와 전달 받은 액션을 참고해서 새로운 상태를 만들어 반환한다. 이는 `useReducer` 를 사용할때와 똑같은 형태로 작성한다.
<br>

```typescript
function counter(state, action) {
  switch (action.type) {
    case 'INCREASE':
      return state + 1
    case "DECREASE":
      return state - 1
    default:
      return state
  }
}
```
<br><br>

## **Store**
<br>

### redux 에는 한 애플리케이션당 하나의 스토어를 만들게 된다. 스토어 안에는 현재의 앱 상태, reducer 가 들어있고 몇가지 내장 함수들이 있다.
<br><br>

## **Dispatch**
<br>

### dispatch 는 store 의 내장함수 중 하나이다. dispatch 는 액션을 발생 시키는 것으로 액션을 파라미터롤 전달한다. 
### 이렇게 호출을 하면 store 는 reducer 함수를 실행시켜 해당 액션을 처리하는 로직이 있다면 액션을 참고하여 새로운 상태를 만든다.
<br><br>

## **Subscribe**
<br>

### subscribe 도 store 의 내장함수 중 하나이다. subscribe 함수는 함수 형태의 값을 파라미터로 받아오고 특정 함수를 전달해주면 액션이 dispatch 되었을 때 마다 전달해준 함수가 호출된다.
### 이 함수를 직접 사용하는 일은 별로 없지만 react-redux 라는 라이브러리에서 제공하는 connect 함수 또는 useSelector Hook 을 사용하여 redux store 의 상태에 subscribe 한다.




