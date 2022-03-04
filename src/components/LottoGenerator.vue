<template>
    <div class="img">
        <img src="../assets/psco.png" alt="psco-logo">
        <p> My Lotto Generator</p>
    </div>
    <button @click="generateNum()">Generate Numbers</button>
    
    <div class="container">
        <div class="outcome" v-for="num in randomNum" :key="num">
            {{ num }}
        </div>
    </div>
</template>


<script>
export default {
    data() {
        return {
            randomNum : [],
            isPlaying : false
        }
    },
    methods: {
        generateNum(){
            while(this.randomNum.length < 6){
                let no = Math.floor((Math.random() * 41)) + 1;
                if(!this.randomNum.includes(no)){
                    this.randomNum.push(no);
                }
            }
        }
    }
}
</script>

<style scoped>
p {
    font-size: 40px;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
.img{
    display: flex;
    align-items: center;
    justify-content: center;
}
.container{
    display: flex;
    margin-left: 26%;
    margin-right: 50%;
}
img{
    height: 100px;
    padding: 25px;
}
button{
    margin-top: 20px;
    font-family: sans-serif;
    width: 280px;
    border-radius: 7px;
    box-shadow: 0px 3px 4px 2px #636161;
    height: 60px;
    font-size: 20px;
    margin-left: 40%;
    margin-right: 50%;
}
.outcome {
    padding: 24px;
    font-size: 60px;
    font-family: sans-serif;
}
</style>