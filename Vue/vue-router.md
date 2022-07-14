## vue-router
<br><br>

### vue-router 로 데이터 전달하기
<br>

- query
<br>
> {name: 'Query', query: {name: 'cow', age: 3}}
<br>

- params
<br>
> {name: 'Params', params: {name:'tiger', age:4}}
<br>

```
<template>
    <div>
      <li @click="clickQuery">
        1. Query
        <router-link :to ="{name: 'Query', query: {name: 'cow', age: 3}}">
        </router-link>
      </li>

      <li @click="clickParams">
        2. Params
        <router-link :to ="{name: 'Params', query: {name: 'tiger', age: 4}}">
        </router-link>
      </li>
    </div>
</template>

<script>
  export default{
    methods: {
      clickQuery() {
        this.$router.push({name: 'Query', query: {name: 'cow', age: 3}})
      },
      clickParams() {
        this.$router.push({name: 'Query', query: {name: 'tiger', age: 4}})
      }
    }
  }
</script>
```
<br><br>

### router > index.js
<br>

- params 로 전달하는 경우, <strong> props:true <strong> 로 설정하면 데이터가 props에도 전달된다.
<br>

```import VueRouter from 'vue-router'
import vue from 'vue'

vue.use(VueRouter)

import Main from '@/views/Main.vue'
import Query from '@/views/Query.vue'
import Params from '@/views/Params.vue'

const router = new VueRouter({
    mode: 'hash',
    routes: [
        {
            path: '/',
            component: Main,
            name: 'Main'
        },
        {
            path: '/query',
            component: Query,
            name: 'Query'
        },
        {
            path: '/params',
            component: Params,
            name: 'Params',
            // true로 설정하면 데이터를 props로도 받습니다.
            props: true
        }     
    ]
})

export { router }
```
<br><br>

## 데이터 받기
<br>

### Query
<br>

```
<template>
  <div>
    <h2>{{ $route.query.name }}</h2>
    <h2>{{ $route.query.age }}</h2>
  </div>
</template>
```
<br>

### Params
<br>

```
<template>
  <div>
    <h2>params로 받은 데이터</h2>
    <h2>name: {{ $route.params.name }}</h2>
    <h2>age: {{ $route.params.age }}</h2>

    <h2>props로 받은 데이터</h2>
    <h2>name: {{ name }}</h2>
    <h2>age: {{ age }}</h2>
  </div>
</template>
```
<br>