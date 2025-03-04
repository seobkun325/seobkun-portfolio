<template>
  <section class="hero">
    <!-- 상단 네비게이션 -->
    <nav class="hero__nav">
      <!-- <a href="https://github.com/seobkun325" target="_blank">GitHub</a> -->
      <!-- <a href="https://velog.io/" target="_blank">Velog</a> -->
    </nav>

    <!-- 메인 컨텐츠 -->
    <div class="hero__content">
      <h1 class="hero__title">Front-End</h1>
      <h2 class="hero__subtitle">프론트엔드 개발자 <span class="bold">윤준섭</span>입니다.</h2>
      <p class="hero__description">
        사용자를 생각하는 <span class="highlight">역지사지</span> 마인드,<br />
        포기하지 않고 <span class="highlight">책임감</span> 있게 일하는 개발자입니다.
      </p>
    </div>

    <!-- 하단 업데이트 정보 -->
    <p class="hero__update">update. 25. 03. 04</p>

    <!-- 아래 화살표 -->
    <div class="hero__scroll">
      <i class="arrow" @click="scrollToAbout"></i>
    </div>

    <!-- 우측 고정 아이콘 버튼 -->
    <div class="hero__fixed-buttons">
      <button class="fixed-btn github-btn" @click="goToGitHub"><i class="icon-github"></i> GitHub</button>
      <button class="fixed-btn top-btn" @click="scrollToTop"><i class="icon-arrow-up"></i> Top</button>
    </div>
  </section>
</template>

<script setup>
const scrollToAbout = () => {
  const aboutSection = document.querySelector(".about");
  if (aboutSection) {
    aboutSection.scrollIntoView({ behavior: "smooth" });
  }
};

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
};

const goToGitHub = () => {
  window.open("https://github.com/seobkun325", "_blank");
};
</script>

<style scoped>
.hero {
  width: 100vw;
  height: 100vh;
  background: url("../assets/image/hero-bg.jpg") no-repeat center center/cover;
  text-align: center;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

/* 네비게이션 스타일 */
.hero__nav {
  position: absolute;
  top: 5%;
  left: 5%;
  display: flex;
  gap: 40px;
}
.bold {
  font-weight: bold;
}
.hero__nav a {
  font-size: 1rem;
  font-weight: bold;
  text-decoration: none;
  color: black;
  border-bottom: 4px solid black;
}

/* 메인 컨텐츠 */
.hero__content {
  text-align: center;
  width: 100%;
}

.hero__title {
  font-size: 8rem;
  width: 100%;
  font-weight: bold;
  color: rgba(0, 0, 0, 0.1);
  position: absolute;
  top: 10%;
  left: 50%;
  transform: translateX(-50%);
}

.hero__subtitle {
  font-size: 2.2rem;
  font-weight: normal;
  color: black;
}

.hero__description {
  font-size: 1.2rem;
  margin-top: 40px;
  line-height: 1.6;
}

.hero__description .highlight {
  font-weight: bold;
  text-decoration: underline;
}

/* 하단 업데이트 정보 */
.hero__update {
  position: absolute;
  bottom: 8%;
  left: 5%;
  font-size: 0.9rem;
  color: gray;
}

/* 아래 스크롤 화살표 */
.hero__scroll {
  position: absolute;
  bottom: 10%;
}

.hero__scroll .arrow {
  display: block;
  width: 24px;
  height: 24px;
  border-bottom: 4px solid black;
  border-right: 4px solid black;
  transform: rotate(45deg);
  animation: bounce 1.5s infinite;
}

/* 우측 고정 버튼 */
.hero__fixed-buttons {
  position: fixed;
  bottom: 50px;
  right: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  z-index: 999;
}

.fixed-btn {
  width: 120px;
  height: 45px;
  background: white;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  border: none;
  font-size: 1rem;
  font-weight: bold;
  transition: 0.3s;
}

.fixed-btn:hover {
  background: black;
  color: white;
}

/* GitHub 버튼 */
.github-btn {
  background: #333;
  color: white;
}

.github-btn:hover {
  background: black;
}

/* 맨 위로 버튼 */
.top-btn {
  background: lightgray;
}

.top-btn:hover {
  background: gray;
  color: white;
}

@keyframes bounce {
  0%,
  100% {
    transform: translateY(0) rotate(45deg);
  }
  50% {
    transform: translateY(10px) rotate(45deg);
  }
}
</style>
