<template>
<div class="main-page-page page2">
    <div class="bg">
        <p class="bg-item" v-for="n in 20" :key="n">
            App:ple Pi 애플파이 앱파 앱플파이 앱플 파이 애플 파이
            앱흘파이 Apple Pi Apple Pie ApplePie 사과 파이
            사과 맛 파이 토독토독 사과맛 파이 App:ple Pie
            Ap:ple Pi Ap:ple Pie 아 귀찮다 애플 파이
            App:ple Pi 애플파이 애플파이 애플파이
            App:ple Pi App:ple Pie Apple Pi Apple Pie
            맛있는 토독토독 사과맛 파이
        </p>
    </div>
    <div class="content">
        <h2>What is EDCAN?</h2>
        <div class="comment-wrap">
            <div class="comment">
                우리는 사과나, 파이를 만들지만,
                <br>
                농부나, 제빵사와 같은 <b>무언가로 정의</b>되지 않습니다.
            </div>

            <div class="comment">
                우리는 모두가 같은 것들을 만들어 낼 때,
                <br>
                <b>우리만의 것을 만드는</b> 사람들입니다.
            </div>

            <div class="comment">
                우리는 <b>특별한 사과파이 창작자</b>입니다.
                <br>
                우리는 <b>App:ple Pi</b>입니다.
            </div>
        </div>
    </div>
</div>
</template>

<script>
let leftList = []
leftList

export default {
    name : "Page2",
    data(){
        return{

        }
    },
    mounted(){
        const WINDOW_WIDTH = window.innerWidth
        WINDOW_WIDTH
        
        let bgItmes = document.querySelectorAll(".bg-item")


        bgItmes.forEach((element, n)=>{
            // leftList.push(WINDOW_WIDTH * n - 30)

            leftList.push(-1 * Math.random() * 1000 % (17000 - WINDOW_WIDTH))
            element.style.left =  leftList[n] + "px"
            element.style.top = 52 * n + "px"
        })


        setInterval(()=>{
            bgItmes.forEach((element, n)=>{

                if(n % 2){
                    leftList[n]--

                    if(leftList[n] < -100) leftList[n] = -1 * Math.random() * 1000 % (17000 - WINDOW_WIDTH)
                }
                else {
                    leftList[n]++

                    if(leftList[n] > -100) leftList[n] = -1 * Math.random() * 1000 % (17000 - WINDOW_WIDTH)
                }

                element.style.left =  leftList[n] + "px"
            })
        }, 50)
    }
}
</script>

<style scoped>
.page2 {
    height : 100vh;
    background-color: #0A0A0A;

    position: relative;
}

.bg {
    width: 100%;
    height: 100%;

    color: #3D3D3D;

    font-size: 40px;
    line-height: 52px;
    letter-spacing: 0.6em;

    overflow: hidden;

    position: absolute;
    left: 0px;
    top: 0px;
    z-index: 0;

    filter: blur(5px);
}

.bg-item {
    width : max-content;
    word-break: break-all;

    position: absolute;
}
/* 
.bg-item:nth-child(1){
    color : red;
}

.bg-item:nth-child(2){
    color : blue;
}

.bg-item:nth-child(3){

} */

.content {
    height : 100%;

    color : white;

    padding : 20px 40px;

    display: flex;
    justify-content: space-between;
    align-items: center;
}

h2 {
    font-family: "Work Sans";
    font-size: 32px;
    font-weight: 300;
    line-height: 38px;
    letter-spacing: 0.025em;
}

.comment-wrap {
    font-size: 24px;
    line-height: 25px;
    letter-spacing: 0em;
    text-align: right;

    display: flex;
    flex-direction: column;
    gap : 2em;
}

.comment {
    font-weight: 300;
    line-height: 1.7em;
}


.unser-line {
    position: relative;
}

.unser-line::before {
    content: "";

    width : 105%;

    border-bottom : 2px solid white;
    border-radius: 20px;

    position: absolute;
    bottom : 0px;
    left : 0px;

    transform: translateX(-2.5%) rotateY(90deg);
    
    animation-name: underline-ani;
    animation-duration: 1000ms;
    animation-delay: 600ms;
    animation-fill-mode: forwards;
}

@keyframes underline-ani {
    0%{
        transform: translateX(-2.5%) rotateY(90deg);
    }

    100%{
        transform: translateX(-2.5%) rotateY(0deg);
    }
}

@media (max-width : 900px) {
    h2 {
        /* text-align: left; */
    }
    .content {
        display: flex;
        flex-direction: column;
        align-items: stretch;
        justify-content: space-evenly;
    }

    .comment {
        font-size: 18px;
    }

    .comment br {
        /* display: none; */
    }
}
</style>