<template>
    <div class="card-container">
        <h3>{{this.contact.name}}</h3>
        <span>
            <label>Username:</label> 
            {{this.contact.username}}
        </span>
        <span>
            <label>Email:</label> 
            {{this.contact.email}}
        </span>
        <span>
            <label>Address:</label> 
            {{this.contact.address.suite}}, 
            {{this.contact.address.street}}, 
            {{this.contact.address.city}},  
            {{this.contact.address.zipcode}}
        </span>
        <span>
            <label>Phone:</label> 
            {{this.contact.phone}}
        </span>
        <span>
            <label>Website:</label> 
            {{this.contact.website}}</span>
        <span>
            <label>Company:</label> 
            {{this.contact.company.name}}, 
            <label>Catch Pharse:</label> 
            {{this.contact.company.catchPhrase}}, 
            <label>Bs:</label> 
            {{this.contact.company.bs}}</span>
    </div>
</template>

<script>
export default {
    props: ['contact'],
}
</script>

<style>
.card-container {
  display: flex;
  flex-direction: column;
  background-color: #95dada;
  border: 1px solid grey;
  border-radius: 5px;
  padding: 25px;
  cursor: pointer;
  -moz-osx-font-smoothing: grayscale;
  backface-visibility: hidden;
  transform: translateZ(0);
  transition: transform 0.25s ease-out;
}

.card-container:hover {
  transform: scale(1.05);
}

span{
    line-height: 1.5rem;
}

label{
    font-weight: bold;
}
</style>