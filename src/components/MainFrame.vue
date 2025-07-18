<script>
export default {
    props: ['mainTitle', 'tailTitle'],
    data() {
        return {
            currentScreen : 0,
            screenCount : 3,
            condition: 'A'
        }
    }
}
</script>

<template>
    <div class="background">
        <main class="main">
            <div>
                {{ mainTitle }}
            </div>
            <div class="">
                <div class="direction left"></div>
                <div class="direction right"></div>
            </div>
        </main>
        <tail class="tail">
            {{ tailTitle }}
            main 컴포넌트를 옆으로 전환할 수 있는 거 만들기
        </tail>
    </div>
</template>

<style scoped>


.background {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 300px;
    height: 300px;
    background-color: antiquewhite;
}

.main {
    width: 95%;
    height: 90%;
    margin: 5px;
    background-color: aqua;
    
    display: flex;
    flex-direction: column;
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