<template>
    <div class="search-container">
        <input class="search"  placeholder="Search name" type="input"  @change="handleSearch" />
    </div>
</template>
<script>
export default {
    name: "searchBox",
    methods:{
        //passing data from input search to card list filter
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