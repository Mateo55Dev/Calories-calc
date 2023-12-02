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
const weight = ref(100);

function addIngredient(id, weight){
    //this.weight = 100;
    this.meals.push(id);

    let ingredient = this.ingredients.find(ingredient => ingredient.id === id);
    
    let caloriesPerGram = Number(ingredient.calories) / ingredient.portion;
    let proteinsPerGram = Number(ingredient.proteins) / ingredient.portion;
    let carbsPerGram = Number(ingredient.carbs) / ingredient.portion;
    let fatsPerGram = Number(ingredient.fats) / ingredient.portion;

    this.totalCalories += caloriesPerGram * this.weight;
    this.totalProteins += caloriesPerGram * this.weight;
    this.totalCarbs += caloriesPerGram * this.weight;
    this.totalFats += caloriesPerGram * this.weight;

    console.log('Meals:', this.meals);
    console.log('Total Calories:', this.totalCalories);
    console.log('Weight: ', weight);
}
</script>

<template>
    <h2>Monitoring calories in meals</h2>

    <div class="ingredients-container">
        <div class="ingredient-card" v-for="ingredient in ingredients">
            <div class="ingredient-title">
                <div class="ingredient-name">{{ ingredient.name }}</div>
                <div class="ingredient-category">({{ ingredient.category }})</div>
            </div>
            <div class="nutrition-values">
                <div class="ingredient-calories">{{ ingredient.calories }} kcal</div>
                <div class="ingredient-protein">{{ ingredient.proteins }} kcal</div>
                <div class="ingredient-carbs">{{ ingredient.carbs }} kcal</div>
                <div class="ingredient-fat">{{ ingredient.fats }} kcal</div>
            </div>
            
            <div class="add">
                <input type="number" v-model="weight" placeholder="Quantity in grams" min="1">
                <button @click="addIngredient(ingredient.id)">Add ingredient</button>
            </div>
            <div class="ingredient-id">ID:{{ ingredient.id }}</div> <!--do usunięcia-->
        </div>
    </div>
    
    <div class="total-container">
        <div class="total-cals">Total Calories: {{ totalCalories }} kcal</div>
        <div class="total-proteins">Total Proteins: {{ totalProteins }} g</div>
        <div class="total-carbs">Total Carbs: {{ totalCarbs }} g</div>
        <div class="total-fats">Total Fats: {{ totalFats }} g</div> 
    </div>
</template>

<style lang="scss" scoped>
    .ingredients-container{
        padding: 10px;
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        gap: 10px;
        .ingredient-card{
            border: 2px solid var(--color-light-gray);
            padding: 10px 5px 10px 5px;
            .ingredient-id{ // do usunięcia
                font-size: 10px; 
            }
            .ingredient-title{
                display: flex;
                gap: 30px;
                margin: 0px auto 0px auto;
                font-size: 1.5em;
                .ingredient-category{
                    font-size: 14px;
                    padding: 5px;
                }
            }
            .nutrition-values{
                display: flex;
                gap: 20px;
                margin-bottom: 5px;
            }
            .add{
                display: flex;
                justify-content: left;
            }
        }
        input[type=number], button {
            padding: 5px;
            font-size: 14px;
        }
        input[type=number] {
            border: 1px solid var(--color-primary-green);
            margin-right: 5px;
        }
        button {
            background-color: var(--color-primary-green);
            border: none;
            color: white;
            cursor: pointer;
            color: var(--color-background-gray);
            font-weight: bold;
        }
        button:hover {
            background-color: #4b407a;
        }
    }
    .total-container{
        padding: 10px;
        display: flex;
        gap: 20px;
    }
</style>