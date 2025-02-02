<template>
  <section class="education">
    <!-- 왼쪽 고정 텍스트 -->
    <h2 class="education__title">Education</h2>

    <!-- 오른쪽 교육 이력 카드 -->
    <div class="education__list">
      <div v-for="edu in education" :key="edu.id" class="education-card">
        <p class="education-card__date">{{ edu.date }}</p>
        <h3 class="education-card__name">{{ edu.institution }}</h3>
        <p class="education-card__course">@ {{ edu.course }}</p>
        <ul class="education-card__details">
          <li v-for="detail in edu.details" :key="detail">{{ detail }}</li>
        </ul>

        <!-- 사용 기술 아이콘 -->
        <div class="education-card__tech">
          <div class="tech-icon" v-for="tech in edu.techIcons" :key="tech">
            <img :src="tech" alt="Tech Icon" class="icon" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

// 교육 이력 데이터
const education = ref([
  {
    id: 1,
    date: "2024.08 - 2025.02",
    institution: `현대오토에버 모빌리티 SW 스쿨`,
    course: "스마트팩토리 관련 교육 수강 중",
    details: [
      "스마트팩토리 도메인 및 데이터 분석 교육",
      "python, java, c# 등 프로그래밍 언어 학습",
      "협업 프로젝트 3회 (sfaas, cps/phm, 머신비전) 진행",
      "자료구조, 운영체제, 알고리즘 등 CS 스터디에 참가하여 학습",
    ],
    techIcons: [
      "/icons/python.svg",
      "/icons/java.svg",
      "/icons/javascript.svg",
      "/icons/spring-boot.svg",
      "/icons/github.svg",
      "/icons/figma.svg",
    ],
  },
  {
    id: 2,
    date: "2024.04 - 2024.08",
    institution: "디지털트윈 IT 개발자 부트캠프",
    course: "웹 기반의 디지털트윈 교육 수료",
    details: [
      "스마트팩토리 도메인 교육",
      "HTML, CSS, JavaScript 등 프로그래밍 언어 학습",
      "vue, react, express 등 웹 프레임워크 교육",
      "IT, OT 교육을 통한 센서 데이터 학습",
    ],
    techIcons: [
      "/icons/html.svg",
      "/icons/css.svg",
      "/icons/javascript.svg",
      "/icons/vue.svg",
      "icons/react.svg",
      "icons/nodejs.svg",
      "icons/express.svg",
    ],
  },
]);
</script>

<style scoped>
.education {
  width: 100vw;
  min-height: 100vh;
  background-color: #1f1f1f;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* 왼쪽 Education 제목 */
.education__title {
  font-size: 3rem;
  font-weight: bold;
  align-self: flex-start;
  margin-left: 5%;
}

/* 교육 카드 리스트 */
.education__list {
  width: 60%;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

/* 개별 교육 카드 */
.education-card {
  background: #353535;
  padding: 20px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  transition: transform 0.3s;
}

.education-card:hover {
  transform: scale(1.05);
}

.education-card__date {
  font-size: 0.9rem;
  color: gray;
}

.education-card__name {
  font-size: 1.5rem;
  font-weight: bold;
}

.education-card__course {
  font-size: 1rem;
  color: lightgray;
  margin-bottom: 10px;
}

/* 교육 상세 내용 */
.education-card__details {
  font-size: 0.9rem;
  margin-bottom: 15px;
}

.education-card__details li {
  margin-bottom: 5px;
}

/* 사용 기술 아이콘 */
.education-card__tech {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}

/* 개별 아이콘을 흰색 배경의 40x40 div 안에 배치 */
.tech-icon {
  width: 10%;
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
}

.icon {
  width: 60%;
  height: 60%;
}

/* 반응형: 화면이 작아지면 1열로 정렬 */
@media (max-width: 768px) {
  .education__list {
    grid-template-columns: 1fr;
  }
}
</style>
