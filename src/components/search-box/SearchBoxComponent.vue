<template>
    <div class="search-container">
        <input class="search"  placeholder="Search name" type="input"  v-on:change="handleSearch" />
    </div>
</template>
<script>
export default {
    methods:{
        //TODO: passing data from input search to card list filter
        handleSearch: function(event) {
            this.$emit('handleSearch', event)
        }
    }
}
</script>

<style>
.search-container{
    margin-bottom: 20px;
}
.search {
    padding: 10px;
    width: 150px;
    line-height: 20px;
    margin: auto;
    display: flex;
}
</style>