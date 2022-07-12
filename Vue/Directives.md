## Directives
<br>

>### v-접두사가 있는 특수 속성이다.
>### 표현식의 값이 변경될때 사이드 이펙트를 반응적으로 DOM에 적용한다.
<br><br>

## v-model
<br>

>### form의 input, textarea를 양방향 바인딩 처리를 위해 사용한다.
>### 한쪽이 변경되면 다른쪽도 변경된다.
>### onclick, querySelectore 문을 사용할 필요가 없다.
<br>

```
<div id="app">
  <input type="text" v-model="text">
  <div>{{text}}</div>
</div>

<script>
  new Vue({
    el : "#app",
    data() {
      return {
        text : "Hello World"
      }
    }
  })
</script>
```
<br><br>

## v-bind
<br>

>### 엘리먼트의 속성과 바인딩 처리를 위해서 사용한다.
<br>

```
<div id='app'>
  <div v-bind:id="idValue">텍스트</div>
</div>

<script>
  new Vue({
    el: '#app',
    data() {
      return {
        idValue : "TEXT"
      }
    }
  })
</script>
```
<br><br>

## v-show
<br>

>### 조건에 따라 엘리먼트를 화면에 렌더링한다.
>### true, false 로 결정한다.
<br>

```
<div id="app">
  <button @click="isShow =! isShow">Show</button>
  <div v-show = "isShow">{{msg}}</div>
</div>

<script>
  new Vue({
    el : "#app",
    data () {
      return {
        msg : "Hello World",
        isShow : true
      }
    }
  })
</script>
```
<br><br>

## v-if, v-else-if, v-else
<br>

>### 조건에 따라 엘리먼트를 화면에 렌더링한다.
>### <strong>v-show 와 다르게 화면에 보이지 않으면 <em>렌더링도 되지 않는다. </em></strong>
<br>

```
<div id="app">
  <input type="text" v-model="age">
  <div>
    <div v-if="age<18">10000원</div>
    <div v-else-if="age<60">15000원</div>
    <div v-else>무료</div>
  </div>
</div>

<script>
  new Vue({
    el : "#app",
    data () {
      return {
        age : 0 // 초기값
      }
    }
  })
</script>
```
<br><br>

## v-for
<br>

>### 배열이나 객체의 반복에 사용한다.
>### v-for = "요소 변수 이름 in 배열" 또는 "(요소 변수 이름, 인덱스) in 배열"
<br>

```
<div id = "app">
  // 단순 for 문
  <div v-for="i in 5" :key="index">{{i}}번</div> 
  // 객체 반복
  <div v-for="value in student" :key="item.id">{{value}}</div>  
  // 배열 돌리기
  <div v-for="(color, index) in colors" :key="index">{{index}}.{{color}}</div> 
</div>

<script>
  new Vue({
    el : "#app",
    data() {
      return {
        student : {
          id: "test",
          name: "TEST",
          age: 10
        },
        colors : ["red", "orange", "yellow", "green"] 
      }
    }
  })
</script>

```
<br><br>

>## <strong> *** 참고 ***  <br> v-for 과 v-if 는 같이 쓰면 안된다. </strong>



