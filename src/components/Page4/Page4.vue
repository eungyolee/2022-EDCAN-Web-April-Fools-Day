<template>
  <div class="main-page-page page4">
    <div class="content">
      <div class="description-wrap">
        <h3 class="page-title">Education</h3>
        <p class="description">
          이러한 과정들을 수행하기 위한 교육도 준비되어 있습니다.<br />
          모든 교육과정은 학과에 관계없이
          <span @click="gotoEducan" class="educan">EDUCAN</span>에서 이수할 수
          있습니다.
        </p>
      </div>

      <div class="educan-item-wrap">
        <EducanItem
          v-for="(i, n) in educanData"
          :key="n"
          :educanStudyData="i"
        />
      </div>

      <button @click="gotoEducan" class="goto-educan nomal-button">
        <span class="bold">EDUCAN</span> 바로가기
      </button>
    </div>
  </div>
</template>

<script>
import EducanItem from "./EducanItem.vue";
import {
  EducanStudyData,
  EducanStudyTag,
} from "../../Model/EducanStudyData.js";

const educanData = [
    new EducanStudyData(
        "사과 농사법 개발",
        "Atelier",
        [
            new EducanStudyTag("Apple", "#0B7038"),
            new EducanStudyTag("Harvest", "#6F3C0B"),
            new EducanStudyTag("Growth", "#073042"),
        ],
        "사과 파이 제빵의 가장 핵심이 되는 사과를 재배하기 위해 공부합니다.",
    ),
    new EducanStudyData(
        "누워서 반죽 만들기",
        "Atelier",
        [
            new EducanStudyTag("Dough", "#74cbfa" ),
            new EducanStudyTag("Bread", "#95df80" ),
            new EducanStudyTag("Baking", "#df0d23" ),
        ],
        "사과 파이 제빵의 두 번째, 반죽 분야를 공부하기 위해서 여러번 반죽을 만들어봅니다.",
    ),
    new EducanStudyData(
        "발효/성형 기초 강좌",
        "Pixel",
        [
            new EducanStudyTag("UI/UX", "#fe654a" ),
            new EducanStudyTag("기초이론", "#ffbc3f" ),
            new EducanStudyTag("디자인", "#27cf21" ),
        ],
        "모바일 UI/UX 디자인에 대한 이론을 Figma와 Adobe XD를 이용하여 실습해보며 학습합니다.",  // 마저 하자
    ),
    new EducanStudyData(
        "서비스 클론 디자인 과정",
        "Pixel",
        [
            new EducanStudyTag("UI/UX", "#fe654a" ),
            new EducanStudyTag("웹디자인", "#8d80e7" ),
            new EducanStudyTag("클론 디자인", "#5fba88" ),
        ],
        "멜론, 토스, 유튜브와 같은 실제 서비스를 클론 디자인해보며 UI/UX에 대한 기본적인 개념을 수립합니다.",
    ),
]

export default {
  name: "Page4",
  data() {
    return {
      educanData,
    };
  },
  methods: {
    gotoEducan() {
      setTimeout(() => {
        // location.href = "https://edu.edcan.kr"
        window.open("https://edu.edcan.kr");
      }, 150);
    },
  },
  components: {
    EducanItem,
  },
};
</script>

<style scoped>
.page4 {
  display: grid;
  grid-template-rows: 1fr;
}

.content {
  padding-top: 180px;
  padding-bottom: 180px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 48px;
}

.description-wrap {
  display: flex;
  flex-direction: column;
  gap: 24px;

  text-align: center;
}

.description {
  font-size: 20px;
}

.educan-item-wrap {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.description .educan {
  font-weight: bold;
  text-decoration: underline 3px;

  cursor: pointer;
}

.goto-educan {
  font-size: 25px;

  padding: 12px 16px;
}

.bold {
  font-weight: bold;
}

/* .goto-educan:hover {
    transform: scale(1.05);
}

.goto-educan:active {
    opacity: 0.5;
    transform: scale(0.95);
} */

@media (max-width: 900px) {
  .educan-item-wrap {
    grid-template-columns: 1fr;
  }
}
</style>
