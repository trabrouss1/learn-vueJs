<template>
    <div class="home">
        <RestaurantRow v-for="(data, i) in data_restaurant" v-bind:key="i" :three_restaurant="data"/>
    </div>
</template>

<script>
// IMPORT 
import BDD from '../BDD.js'
import { onMounted, ref } from 'vue';

// COMPONENTS
import RestaurantRow from '../components/RestaurantRow.vue';
export default {
    name:'HomeP',
    components:{
        RestaurantRow
    },
    setup() {
        class Restaurant {
            constructor (name, note, image, drive_time){
                this.name       = name
                this.note       = note
                this.image      = image
                this.drive_time = drive_time
            }
        }

        let data_restaurant = ref([])
        const makeDataRestaurant = () => {
            let three_restaurannt = []
            for (const restaurant of BDD) {
                const new_restaurant = new Restaurant(restaurant.name, restaurant.note, restaurant.image, restaurant.drive_time)
                if (three_restaurannt.length === 2) {
                    three_restaurannt.push(new_restaurant)
                    data_restaurant.value.push(three_restaurannt)
                    three_restaurannt = []
                }else{
                    three_restaurannt.push(new_restaurant)
                }
            }
        }

        onMounted(makeDataRestaurant);

        // return 
        return {
            data_restaurant,
        }
    },
}
</script>

<style>

</style>