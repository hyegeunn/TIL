# Props
<br>

#### props는 상위에서 어떤 pops를 받을 것인지 알려준 후, setup 에서 props.xxxx로 접근한다.
<br>

### Parent Component
<br>

```
<template>
  <dlv class="home">
    <!-- child 컴포넌트에게 props 내림 -->
    <PostList :posts="posts" />
  </div>
</template>
<script>
  // 사용할 컴포넌트 import
  import PostList from '../components/PostList.vue'
  import { ref } from 'vue';

  export default {
    name: 'Home',
    // 사용할 컴포넌트를 넣어줍니다.
    components: { PostList },

    setup() {
      const posts = ref([
        { title: '1번 타이틀', body: '1번 제목', id: 1 },
        { title: '2번 타이틀', body: '2번 제목', id: 2 },
      ]);

      return { posts }
    }
  }
</script>

```
<br>

### Child components
<br>

```
<template>
  <div>
    {{ post.title }}
    {{ post.body }}
  </div>
</template>
<script>
export default {
  // 사용할 props를 배열내에 정의합니다.
  props: ["posts"],
  setup(props) {
    console.log(props.posts); // 받은 prop 사용가능
  }
};
</script>
 
```