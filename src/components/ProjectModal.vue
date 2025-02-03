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
        <p class="modal__date">{{ project.date }} • {{ project.teamSize }}</p>
      </div>

      <!-- 프로젝트 대표 이미지 -->
      <div class="modal__image-container">
        <img :src="project.image" alt="Project Image" class="modal__image" />
      </div>

      <!-- 프로젝트 설명 -->
      <div class="modal__content">
        <p class="modal__description">{{ project.description }}</p>

        <div class="line"></div>
        <!-- 주요 기능 -->
        <h3>📌 주요 기능</h3>
        <ul class="modal__features">
          <li v-for="feature in project.features" :key="feature">{{ feature }}</li>
        </ul>
        <div class="line"></div>

        <!-- 역할 및 기여 내용 -->
        <h3>💻 내 역할</h3>
        <ul class="modal__role">
          <li v-for="role in project.role" :key="role">{{ role }}</li>
        </ul>
        <div class="line"></div>

        <!-- 사용 기술 -->
        <h3>⚙️ 사용 기술</h3>
        <ul class="modal__tech">
          <li v-for="tech in project.tech" :key="tech">{{ tech }}</li>
        </ul>
        <div class="line"></div>

        <!-- 작업 화면 (스크린샷) -->
        <!-- <h3>📸 작업 화면</h3>
        <div class="modal__screenshots">
          <img v-for="screenshot in project.screenshots" :key="screenshot" :src="screenshot" alt="Project Screenshot" />
        </div> -->

        <!-- 프로젝트 링크 -->
        <div class="modal__links">
          <a v-if="project.githubLink" :href="project.githubLink" target="_blank" class="btn">GitHub 바로가기</a>
          <a v-if="project.youtubeLink" :href="project.youtubeLink" target="_blank" class="btn">YouTube 바로가기</a>
        </div>
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
  width: 60%;
  border-radius: 15px;
  text-align: center;
  position: relative;
  max-height: 90vh;
  overflow-y: auto;
  color: black;
  box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
}

/* 모달 상단 배경 (포인트 컬러 적용) */
.modal__header {
  height: 280px;
  position: relative;
  padding-top: 40px;
  border-top-left-radius: 15px;
  border-top-right-radius: 15px;
  text-align: center;
  color: white;
}

/* 프로젝트 썸네일 배치 */
.modal__image-container {
  position: relative;
  margin-top: -120px;
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
  background: rgba(255, 255, 255, 0.2);
  padding: 5px 10px;
  border-radius: 5px;
  margin-right: 5px;
  font-size: 0.9rem;
}

/* 닫기 버튼 */
.modal__close {
  position: absolute;
  top: 15px;
  right: 15px;
  background: none;
  border: none;
  font-size: 1.5rem;
  font-weight: bold;
  cursor: pointer;
  color: white;
}

/* 프로젝트 제목 */
.modal__title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 10px;
}

/* 프로젝트 기간 및 인원 정보 */
.modal__date {
  font-size: 1rem;
  color: white;
  margin-bottom: 20px;
}

/* 컨텐츠 스타일 */
.modal__content {
  display: flex;
  flex-direction: column;
  text-align: center;
  padding: 5% 15% 0 15%;
}

.modal__description {
  font-size: 1rem;
  font-weight: 300;
  line-height: 1.6;
  margin-bottom: 20px;
  color: rgb(0, 0, 0);
}

/* 리스트 공통 스타일 */
.modal__features,
.modal__role,
.modal__tech {
  list-style: none;
  margin-bottom: 40px;
  line-height: 2;
  text-align: left;
  padding: 0px;
}

.modal__features li::before,
.modal__role li::before,
.modal__tech li::before {
  content: "✔ ";
  color: #4caf50;
  font-weight: bold;
}

/* 작업 화면 */
.modal__screenshots {
  display: flex;
  gap: 10px;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 20px;
}

.modal__screenshots img {
  width: 150px;
  height: auto;
  border-radius: 5px;
}

/* 프로젝트 링크 */
.modal__links {
  margin-top: 20px;
  text-align: center;
  margin-bottom: 40px;
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
.line {
  margin-top: 40px;
  margin-bottom: 20px;
  width: 100%;
  height: 2px;
  background: lightgrey;
}
</style>
