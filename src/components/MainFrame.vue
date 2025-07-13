<script>
export default {
    props: ['mainTitle', 'tailTitle'],
    data() {
        return {
            count : 100,
        }
    },
    computed: {
        computedNow() {
            return Date.now();
        }
    },
    methods: {
        increaseCount() {
            this.count += 1;
        },
        methodNow() {
            return Date.now();
        }

    }
}
</script>

<template>
    <div class="background">
        <main class="main">
            {{ mainTitle }} Count : {{ count }}
            {{ methodNow() }}
        </main>
        <tail class="tail">
            {{ tailTitle }}
            main 컴포넌트를 옆으로 전환할 수 있는 거 만들기
            <button @click="increaseCount">
                클릭하기
            </button>
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
}

.tail {
    width: 95%;
    height: 5%;
    margin: 5px;
    background-color:aquamarine;
}

</style>