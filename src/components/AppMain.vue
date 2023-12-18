<template>
    <main>


       <article v-for="carte in cards">
        <div class="carta">
            <img :src="carte.card_images[0].image_url" :alt="carte.name" @error="handleImageError">
            <p>
                {{  carte.name }}
            </p>

            <p>
                {{ carte.archetype }}
            </p>
        </div>
       </article>

    </main>
</template>

<script>

import { store } from '../../js/store';

export default {
    data() {
        return {
            store,
            
        }
    },

    props:{
        cards:{
            type: Array,
            required: true,
        }
    },

    methods: {
    handleImageError(event) {
      console.error('Error loading image:', event.target.src);
    },
    
} 
}



</script>

<style>

main{
    background-color: #D48F38;
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    text-align: center;
    justify-content: center;

}


.carta {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin-left: 5rem;
  padding: 1rem;
}

.carta img {
  height: auto;
  max-width: 60%; 
}


.carta p {
  background-color: rgb(255, 255, 255);
  text-align: center; 
  padding: 1rem;
  width: 60%;
  height: 100%;
}

div .carta {
display: flex;
flex-direction: column;
width: 100%;
}

article{
    width: 25%;
    margin: 0 auto;
    display: flex;
  

}

    
</style>