
<script>
import GiftDelivery from './GiftDelivery.vue';
export default {
    components: { GiftDelivery },
    props: ['mainTitle', 'tailTitle'],
    data() {
        return {
            currentScreen : 0,
            screenCount : 3,
            condition: 'A'
        }
    },
    methods: {
        slideContainer(event, isToLeft) {
            event.preventDefault();
            if(isToLeft) {
                this.currentScreen = (this.currentScreen + this.screenCount - 1) % this.screenCount;
            } else {
                this.currentScreen = (this.currentScreen + 1) % this.screenCount;
            }
        }
    }
}
</script>

<template>
    <div class="background">
        <main class="main">
            <div class="container">
                <GiftDelivery v-if="currentScreen === 0" />
                <div v-else>
                    {{ mainTitle }} {{ currentScreen }}
                </div>
            </div>
            <div class="slide">
                <div @click="(event) => slideContainer(event, true)" class="direction left"></div>
                <div @click="(event) => slideContainer(event, false)" class="direction right"></div>
            </div>
        </main>
        <tail class="tail">
            {{ tailTitle }}
        </tail>
    </div>
</template>

<style scoped>


.background {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 1000px;
    height: 680px;
    background-color: antiquewhite;
}

.main {
    width: 95%;
    height: 90%;
    margin: 5px;
    
    
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.main > .container {
    height: 95%;
}

.main > .slide {
    height: 5%;
    padding: auto;
    margin: 5px;;

    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}

.tail {
    width: 95%;
    height: 5%;
    margin: 5px;
    background-color:aquamarine;
}


.direction {
    height: 20px;
    width: 20px;
    margin: 30px;
    background-image: url('@/image/direction-key.png');
    background-repeat: no-repeat;
    background-size: contain;
    transition: filter 0.2s ease;
}
.direction:hover {
    filter: brightness(0%) saturate(100%) invert(50%) sepia(100%) saturate(749%) hue-rotate(135deg) brightness(92%) contrast(85%);
}
.direction + .right {
    transform: rotate(180deg);
}
.direction + .left {

}

</style>