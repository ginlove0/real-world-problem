<template>
    <div>
        <search-box @handleSearch="onSearch"/>
        <div class="card-list">
            <div v-for="contact in resultQuery" :key="contact.id">
                <Card 
                    :contact="contact"
                />
            </div>
        </div>
    </div>
    
</template>
    
<script>
import axios from 'axios';
import Card from '../card/CardComponent'
import SearchBox from '../search-box/SearchBoxComponent.vue';

export default {
    name: 'cardList',
    components:{
        Card,
        SearchBox
    },
    data() {
        return{
            contacts: [],
            searchQuery: ''
        }
    },
    computed: {
        //TODO: filter by search input
        resultQuery(){
            if(this.searchQuery){
                return this.contacts.filter(user => user.name.toLowerCase().includes(this.searchQuery.toLowerCase()));
            }else{
                return this.contacts;
            }
        }
        
    },
    methods:{
        //TODO: fetch data from API, using axios package
        fetchDataContact: function(){
            axios.get('https://jsonplaceholder.typicode.com/users')
            .then((res) => {
                if(res){
                    this.contacts = res.data;
                }
            })
        },

        onSearch: function(event){
            this.searchQuery = event.target.value;
        }
    },

    mounted(){
        this.fetchDataContact()
    }
}
</script>

<style>
.card-list {
  width: 85vw;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 20px;
}

</style>