<template>
<div class="main-page-page page3">
    <div class="content">
        <h3>Baking Process</h3>
        <div class="steps-wrap">
            <StepItem
                v-for="(i, n) in stepDataList" :key="n" :stepData="i"/>
        </div>
    </div>
</div>
</template>

<script>
import StepItem from "./StepItem.vue"

import StepData from "./../../Model/StepData.js"

export default {
    name : "Page3",
    data(){return{
        stepDataList : [
            new StepData(
                1,
                "수확",
                "모든 제빵의 시작에는 수확이 있습니다. 별도의 농부가 있는 것이 아닌, 모두가 힘을 모아 사과를 재배합니다.",
            ),
            new StepData(
                2,
                "재료 준비",
                "제빵에 필요한 재료를 준비합니다. 사과 파이에 들어가는 사과와, 제빵 재료를 빠르게 준비하고, 바로 재료 손질과 발효에 착수하여, 최소한의 준비를 합니다.",
            ),
            new StepData(
                3,
                "굽기",
                "파이 틀에 반죽을 넣고 그 안에 사과를 채워넣어 파이의 모양을 만든 뒤 오븐에 넣어 굽습니다.",
            ),
            new StepData(
                4,
                "완전한 사과파이 제작",
                "굽기를 마치고 문제가 없음을 확인하였다면, 이제 사과파이에 데코레이션을 하고, 문제가 있다면 다시 제작하여 완성합니다."
            ),
        ]
    }},
    components : {
        StepItem
    }
}
</script>

<style scoped>
.page3 {
    min-height : min-content;

    color : white;

    background: linear-gradient(107.56deg, #400091 0%, #52142A 50%, #000000 100%);
}

.content {
    min-height : 100vh;

    display: flex;
    flex-direction: column;
    justify-content: center;
    gap : 44px;
}

h3 {
    font-weight: 500;
    font-size: 28px;
    line-height: 33px;
    text-align: center;
}

.steps-wrap {
    display: flex;
    flex-direction: column;
    gap : 36px;
}

@media (max-width : 900px) {
    .content {
        padding : 64px 32px;
    }
}
</style>