<script setup>
</script>

<template>
    <div class="meals-space">
        <h2>Component do monitorowania posiłków</h2>

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
    </div>
</template>

<style lang="scss" scoped>
    .meals-space{
        border: 1px dashed black;
    }
    .breakfast{
        line-height: 0.1em;
            .nutritions{
                display: flex;
                gap: 25px;
            }
    }

    .brunch{
        line-height: 0.1em;
            .nutritions{
                display: flex;
                gap: 25px;
            }
    }

    .lunch{
        line-height: 0.1em;
            .nutritions{
                display: flex;
                gap: 25px;
            }
    }

    .tea{
        line-height: 0.1em;
            .nutritions{
                display: flex;
                gap: 25px;
            }
    }

    .dinner{
        line-height: 0.1em;
            .nutritions{
                display: flex;
                gap: 25px;
            }
    }
</style>