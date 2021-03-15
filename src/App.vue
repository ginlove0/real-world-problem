<template>
  <div id="app">
    <user-list />
  </div>
</template>

<script>
import UserList from './components/user-list/UserList.vue'

export default {
  name: 'App',
  components: {
    UserList
  }
}
</script>