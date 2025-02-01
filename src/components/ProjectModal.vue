<template>
  <div v-if="isOpen" class="modal-overlay" @click.self="closeModal">
    <div class="modal">
      <!-- 상단 배경 (포인트 컬러 적용) -->
      <div class="modal__header" :style="{ background: project.color }">
        <button class="modal__close" @click="closeModal">✖</button>
        <div class="modal__tags">
          <span v-for="tag in project.tags" :key="tag" class="project-tag">{{ tag }}</span>
        </div>
        <h2 class="modal__title">{{ project.name }}</h2>
        <p class="modal__date">{{ project.date }} &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp{{ project.teamSize }}</p>
      </div>

      <!-- 프로젝트 대표 이미지 (포인트 컬러 위로 배치) -->
      <div class="modal__image-container">
        <img :src="project.image" alt="Project Image" class="modal__image" />
      </div>

      <!-- 프로젝트 소개 -->
      <p class="modal__description">{{ project.description }}</p>

      <!-- 주요 기능 -->
      <h3>📌 주요 기능</h3>
      <ul class="modal__features">
        <li v-for="feature in project.features" :key="feature">{{ feature }}</li>
      </ul>

      <!-- 사용 기술 -->
      <h3>⚙️ 사용 기술</h3>
      <ul class="modal__tech">
        <li v-for="tech in project.tech" :key="tech">{{ tech }}</li>
      </ul>

      <!-- 트러블슈팅 -->
      <h3>🛠 Trouble Shooting</h3>
      <ul class="modal__troubleshooting">
        <li v-for="issue in project.troubleshooting" :key="issue">{{ issue }}</li>
      </ul>

      <!-- 작업 화면 (스크린샷) -->
      <h3>📸 작업 화면</h3>
      <div class="modal__screenshots">
        <img v-for="screenshot in project.screenshots" :key="screenshot" :src="screenshot" alt="Project Screenshot" />
      </div>

      <!-- 프로젝트 링크 -->
      <div class="modal__links">
        <a v-if="project.githubLink" :href="project.githubLink" target="_blank" class="btn">GitHub 바로가기</a>
        <a v-if="project.youtubeLink" :href="project.youtubeLink" target="_blank" class="btn">YouTube 바로가기</a>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: Object,
  isOpen: Boolean,
});

const emit = defineEmits(["close"]);

const closeModal = () => {
  emit("close");
};
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal {
  background: white;
  width: 70%;
  border-radius: 10px;
  text-align: center;
  position: relative;
  max-height: 90vh;
  overflow-y: auto;
  color: black;
}

/* 모달 상단 배경 (포인트 컬러 적용) */
.modal__header {
  height: 250px; /* 포인트 컬러 영역 */
  position: relative;
  padding-top: 40px;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  text-align: center;
  color: white;
}

/* 프로젝트 썸네일이 상단 배경 위로 올라오도록 설정 */
.modal__image-container {
  position: relative;
  margin-top: -120px; /* 이미지가 포인트 컬러 배경 위로 올라오도록 */
  display: flex;
  justify-content: center;
}

.modal__image {
  width: 50%;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

/* 태그 스타일 */
.modal__tags {
  margin-bottom: 10px;
}

.project-tag {
  background: rgba(0, 0, 0, 0.8);
  padding: 5px 10px;
  border-radius: 5px;
  margin-right: 5px;
  font-size: 0.9rem;
}
.modal__close {
  position: absolute;
  top: 15px;
  right: 15px;
  background: none;
  border: none;
  font-size: 1.5rem;
  font-weight: thin;
  cursor: pointer;
  color: white;
}
/* 프로젝트 제목 */
.modal__title {
  font-size: 3rem;
  font-weight: bold;
  margin: 10px;
}

/* 프로젝트 기간 및 인원 정보 */
.modal__date {
  font-size: 0.8rem;
  color: white;
  margin-bottom: 30px;
}

/* 프로젝트 설명 */
.modal__description {
  font-size: 1.2rem;
  line-height: 1.5;
  margin-bottom: 20px;
}

/* 프로젝트 링크 */
.modal__links {
  margin-top: 20px;
}

.btn {
  display: inline-block;
  margin: 5px;
  padding: 10px 15px;
  border: 1px solid black;
  border-radius: 5px;
  background: white;
  text-decoration: none;
  color: black;
  transition: 0.3s;
}

.btn:hover {
  background: black;
  color: white;
}
</style>
