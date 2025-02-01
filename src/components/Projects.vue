<template>
  <section class="projects">
    <h2 class="projects__title">Projects</h2>

    <div class="projects__list">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <div class="project-card__content">
          <!-- 프로젝트 이미지 -->
          <img :src="project.image" :alt="project.name" class="project-card__image" />

          <!-- 기본 정보: 제목, 한 줄 소개, 태그 -->
          <div class="project-card__info">
            <h3 class="project-card__name">{{ project.name }}</h3>
            <p class="project-card__desc">{{ project.shortDescription }}</p>
            <div class="project-card__tags">
              <span v-for="tag in project.tags" :key="tag" class="project-tag">{{ tag }}</span>
            </div>
          </div>

          <!-- 마우스 오버 시 나타나는 상세 정보 -->
          <div class="project-card__overlay">
            <p class="project-card__full-desc">{{ project.name }}</p>
            <div class="project-card__buttons">
              <button class="btn">자세히 보기</button>
              <a v-if="project.githubLink" :href="project.githubLink" target="_blank" class="btn">GitHub 바로가기</a>
              <button v-if="project.youtubeLink" @click="openLink(project.youtubeLink)" class="btn">
                YouTube 바로가기
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

// 이미지 동적 로드
const images = import.meta.glob("../assets/image/*.png", { eager: true });

// 프로젝트 데이터
const projects = ref([
  {
    id: 1,
    name: "Your Capsules",
    shortDescription: "게임 UX/UI 기반의 타임/목표 캡슐 관리 플랫폼입니다.",
    image: images["../assets/image/capsule-thumbnail.png"].default,
    githubLink: "https://github.com/seobkun/yourcapsules",
    youtubeLink: null,
    tags: ["JavaScript", "Vue", "HTML", "CSS"],
  },
  {
    id: 2,
    name: "Traum",
    shortDescription: "3D 오브젝트와 Live-Data 매핑의 디지털트윈 모니터링 플랫폼입니다.",
    image: images["../assets/image/traum-thumbnail.png"].default,
    githubLink: null,
    youtubeLink: "https://www.youtube.com/watch?v=traum-thumbnail",
    tags: ["JavaScript", "Vue", "HTML", "CSS", "Babylon.js"],
  },
  {
    id: 3,
    name: "의장공정 모니터링 시스템",
    shortDescription: "실시간 자재, 생산, 품질, 설비 데이터 모니터링 시스템입니다.",
    image: images["../assets/image/hyundai-thumbnail.png"].default,
    githubLink: null,
    youtubeLink: "https://www.youtube.com/watch?v=hyundai",
    tags: ["JavaScript", "HTML", "CSS", "jQuery", "SMWP"],
  },
  {
    id: 4,
    name: "COKKIRI",
    shortDescription: "스터디와 프로젝트 멤버를 모으고, 일정을 관리하는 플랫폼입니다.",
    image: images["../assets/image/cokkiri-thumbnail.png"].default,
    githubLink: null,
    youtubeLink: null,
    tags: ["JavaScript", "Vue", "HTML", "CSS"],
  },
]);

// 유튜브 링크 열기 함수 (새 창에서 열림)
const openLink = (url) => {
  window.open(url, "_blank");
};
</script>

<style scoped>
.projects {
  width: 100vw;
  min-height: 100vh;
  background-color: #1f1f1f;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* 제목 */
.projects__title {
  font-size: 3rem;
  font-weight: bold;
  align-self: flex-start;
  margin-left: 5%;
}

/* 2x2 그리드 설정 */
.projects__list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, auto);
  gap: 40px;
  width: 70%;
  margin-bottom: 5%;
}

/* 프로젝트 카드 */
.project-card {
  position: relative;
  width: 100%;
  background: #292929;
  border-radius: 10px;
  overflow: hidden;
}

/* 기본적으로 보이는 이미지 + 제목 + 설명 + 태그 */
.project-card__image {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.project-card__info {
  padding: 15px;
}

.project-card__name {
  font-size: 1.5rem;
  font-weight: bold;
}

.project-card__desc {
  font-size: 1rem;
  margin-top: 5px;
  color: #ccc;
}

/* 태그 스타일 */
.project-card__tags {
  margin-top: 10px;
  display: flex;
  gap: 5px;
}

.project-tag {
  background: rgba(255, 255, 255, 0.1);
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 0.9rem;
}

/* 마우스 오버 시 상세 정보 나타나도록 설정 */
.project-card__overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
}

/* 마우스 오버 시 상세 정보 표시 */
.project-card:hover .project-card__overlay {
  opacity: 1;
}

/* 상세 설명 */
.project-card__full-desc {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 15px;
  padding: 0 10px;
}

/* 버튼 스타일 */
.project-card__buttons {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.btn {
  padding: 16px 30px;
  font-size: 1rem;
  background: transparent;
  border: 1px solid white;
  color: white;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s, color 0.3s;
}

.btn:hover {
  background: white;
  color: black;
}

/* 반응형: 화면이 작아지면 1열 배치 */
@media (max-width: 768px) {
  .projects__list {
    grid-template-columns: 1fr;
    grid-template-rows: auto;
  }
}
</style>
