<script setup>
import { ref } from 'vue';
const ingredients = ref([
    {
        id: 102,
        name: 'Pineapple',
        category: 'fruits',
        calories: '54',
        proteins: '0.4',
        carbs: '13.6',
        fats: '0.2',
        portion: 100
    },
    {
        id: 748,
        name: 'Sugar',
        category: 'sweets',
        calories: '405',
        proteins: '0',
        carbs: '99.8',
        fats: '0',
        portion: 100
    },
    {
        id: 279,
        name: 'Pumpkin',
        category: 'vegetables',
        calories: '28',
        proteins: '1.3',
        carbs: '7.7',
        fats: '0.3',
        portion: 100
    },
    {
        id: 109,
        name: 'Beef',
        category: 'meat',
        calories: '117',
        proteins: '20.9',
        carbs: '0',
        fats: '3.6',
        portion: 100
    },
    {
        id: 753,
        name: 'Banana',
        category: 'fruits',
        calories: '95',
        proteins: '1',
        carbs: '23.5',
        fats: '0.3',
        portion: 100
    },
    {
        id: 328,
        name: 'Chicken',
        category: 'meat',
        calories: '179',
        proteins: '16.4',
        carbs: '0.1',
        fats: '12.7',
        portion: 100
    },
    {
        id: 692,
        name: 'Pasta',
        category: 'cereal-products',
        calories: '363',
        proteins: '10',
        carbs: '78.5',
        fats: '1.6',
        portion: 100
    }, 
    {
        id: 234,
        name: 'Cottage cheese',
        category: 'dairy-products',
        calories: '101',
        proteins: '12.3',
        carbs: '3.3',
        fats: '4.3',
        portion: 100
    },
    {
        id: 817,
        name: 'Salted chips',
        category: 'sweets',
        calories: '552',
        proteins: '5.6',
        carbs: '49.9',
        fats: '40.7',
        portion: 100
    },
    {
        id: 882,
        name: 'Feta cheese',
        category: 'dairy-products',
        calories: '216',
        proteins: '17',
        carbs: '1',
        fats: '16',
        portion: 100
    },
    {
        id: 308,
        name: 'Chocolate',
        category: 'sweets',
        calories: '549',
        proteins: '9.8',
        carbs: '54.7',
        fats: '32.8',
        portion: 100
    },
    {
        id: 268,
        name: 'Onion',
        category: 'vegetables',
        calories: '30',
        proteins: '1.4',
        carbs: '6.9',
        fats: '0.4',
        portion: 100
    },
    {
        id: 924,
        name: 'Cornflakes',
        category: 'cereal-products',
        calories: '385',
        proteins: '6.9',
        carbs: '86.3',
        fats: '2.5',
        portion: 100
    },
    {
        id: 555,
        name: 'Coca Cola',
        category: 'drinks',
        calories: '42',
        proteins: '0',
        carbs: '10.4',
        fats: '0',
        portion: 100
    },
    {
        id: 626,
        name: 'Bread',
        category: 'cereal-products',
        calories: '246',
        proteins: '5.9',
        carbs: '55.9',
        fats: '1.5',
        portion: 100
    }
]);

const meals = ref([]);

const totalCalories = ref(0);
const totalProteins = ref(0);
const totalCarbs = ref(0);
const totalFats = ref(0);

function addIngredient(id){
    this.meals.push(id);

    let ingredient = this.ingredients.find(ingredient => ingredient.id === id);
    this.totalCalories += Number(ingredient.calories);
    this.totalProteins += Number(ingredient.proteins);
    this.totalCarbs += Number(ingredient.carbs);
    this.totalFats += Number(ingredient.fats);
    
    let caloriesPerGram = Number(ingredient.calories) / ingredient.portion;
    this.totalCalories += caloriesPerGram * weight;
    this.totalProteins += caloriesPerGram * weight;
    this.totalCarbs += caloriesPerGram * weight;
    this.totalFats += caloriesPerGram * weight;

    console.log('Meals:', this.meals);
    console.log('Total Calories:', this.totalCalories);
}
</script>

<template>

    
        <h2>Monitoring calories in meals</h2>
<!--
        <div class="breakfast">
            <h3>Śniadanie</h3>
            <div class="nutritions">
                <p>720 kcal</p>
                <p>55.9 protein</p>
                <p>38.4 fat</p>
                <p>39.9 carbs</p>
            </div>
            
        </div>

        <div class="brunch">
            <h3>II Śniadanie</h3>
            <div class="nutritions">
                <p>456 kcal</p>
                <p>55.8 protein</p>
                <p>58.4 fat</p>
                <p>39.8 carbs</p>
            </div>
        </div>
        <div class="lunch">
            <h3>Obiad</h3>
            <div class="nutritions">
                <p>1168 kcal</p>
                <p>10.9 protein</p>
                <p>38.4 fat</p>
                <p>39.9 carbs</p>
            </div>
        </div>
        <div class="tea">
            <h3>Podwieczorek</h3>
            <div class="nutritions">
                <p>759 kcal</p>
                <p>50.9 protein</p>
                <p>38.4 fat</p>
                <p>39.9 carbs</p>
            </div>
        </div>
        <div class="dinner">
            <h3>Kolacja</h3>
            <div class="nutritions">
                <p>589 kcal</p>
                <p>43.0 protein</p>
                <p>15.4 fat</p>
                <p>79.9 carbs</p>
            </div>
        </div>
-->

    <div class="ingredients-container">
        <div class="ingredient-card" v-for="ingredient in ingredients">
            <div class="ingredient-ident">ID:{{ ingredient.id }}</div>
            <div class="ingredient-name">{{ ingredient.name }}</div>
            <div class="ingredient-category">({{ ingredient.category }})</div>
            <div class="ingredient-calories">{{ ingredient.calories }} kcal</div>
            <div class="ingredient-protein">{{ ingredient.proteins }} kcal</div>
            <div class="ingredient-carbs">{{ ingredient.carbs }} kcal</div>
            <div class="ingredient-fat">{{ ingredient.fats }} kcal</div>
            <input type="number" v-model="weight" placeholder="Quantity in grams" min="1">
            <button @click="addIngredient(ingredient.id)">Add ingredient</button>
        </div>
    </div>
    
    <div class="total-container">
        <div class="total-cals">Total Calories: {{ totalCalories }}</div>
        <div class="total-proteins">Total Proteins: {{ totalProteins }}</div>
        <div class="total-carbs">Total Carbs: {{ totalCarbs }}</div>
        <div class="total-fats">Total Fats: {{ totalFats }}</div> 
    </div>




</template>

<style lang="scss" scoped>
    .ingredients-container{
        padding: 10px;
        display: grid;
        grid-template-columns: repeat(8, 1fr);
        gap: 20px;
        .ingredient-card{
            border: 2px solid var(--color-light-gray);
            padding: 10px 5px 10px 5px;
        }
    }

    .total-container{
        padding: 10px;
        display: flex;
        gap: 20px;
    }
    
    
    
    // .meals-space{
    //     border: 1px dashed black;
    // }
    // .breakfast{
    //     line-height: 0.1em;
    //         .nutritions{
    //             display: flex;
    //             gap: 25px;
    //         }
    // }
    // .brunch{
    //     line-height: 0.1em;
    //         .nutritions{
    //             display: flex;
    //             gap: 25px;
    //         }
    // }
    // .lunch{
    //     line-height: 0.1em;
    //         .nutritions{
    //             display: flex;
    //             gap: 25px;
    //         }
    // }
    // .tea{
    //     line-height: 0.1em;
    //         .nutritions{
    //             display: flex;
    //             gap: 25px;
    //         }
    // }
    // .dinner{
    //     line-height: 0.1em;
    //         .nutritions{
    //             display: flex;
    //             gap: 25px;
    //         }
    // }
</style>