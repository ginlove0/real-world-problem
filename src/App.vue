<template>
  <div id="app">
    <card-list />
  </div>
</template>

<script>
import CardList from './components/card-list/CardListComponent.vue'

export default {
  name: 'App',
  components: {
    CardList
  }
}
</script>