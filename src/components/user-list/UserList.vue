<template>
    <div>
        <search-box @handleSearch="onSearch"/>
        <div class="user-list">
            <div v-for="contact in resultQuery" :key="contact.id">
                <User 
                    :contact="contact"
                />
            </div>
        </div>
    </div>
    
</template>
    
<script>
import axios from 'axios';
import User from '../user/User';
import SearchBox from '../search-box/SearchBox.vue';

export default {
    name: 'userList',
    components:{
        User,
        SearchBox
    },
    data() {
        return{
            contacts: [],
            searchQuery: ''
        }
    },
    computed: {
        //filter by search input
        resultQuery: function(){
            if(this.searchQuery){
                return this.contacts.filter(user => user.name.toLowerCase().includes(this.searchQuery.toLowerCase()));
            }
            return this.contacts;
        }
        
    },
    methods:{
        //fetch data from API, using axios package
        fetchDataContact: function(){
            axios.get('https://jsonplaceholder.typicode.com/users')
            .then((res) => {
                if(res){
                    this.contacts = res.data;
                }
            })
            .catch((err) => {
                console.log('Error in fetching api ' + err);
            })
        },

        onSearch: function(event){
            this.searchQuery = event.target.value;
        }
    },

    mounted(){
        this.fetchDataContact()
    },
}
</script>

<style>
.user-list {
  width: 85vw;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 20px;
}

</style>