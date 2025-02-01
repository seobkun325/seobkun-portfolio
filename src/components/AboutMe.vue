<template>
  <section class="about">
    <h2 class="about__title">About me</h2>

    <!-- 프로필 이모지 -->
    <div class="about__profile">
      <img src="../assets/image/avatar.png" alt="Profile" class="about__avatar" />
    </div>

    <!-- 해시태그 -->
    <div class="about__tags">
      <span>#역지사지</span>
      <span>#메타인지</span>
      <span>#피드백수용</span>
      <span>#끊임없는 배움</span>
    </div>

    <!-- 팀원 리뷰 보기 버튼 -->
    <button class="about__review-btn">팀원 리뷰 보기 ➝</button>

    <!-- 인터뷰 섹션 -->
    <div class="about__interview">
      <h3>Interview</h3>
      <div class="about__qa">
        <h4>Q. 프론트엔드를 선택한 이유?</h4>
        <p>사용자 경험을 직관적으로 개선할 수 있기 때문입니다.</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  width: 100vw;
  min-height: 100vh;
  background-color: #1f1f1f;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

/* 제목 */
.about__title {
  font-size: 3rem;
  font-weight: bold;
  align-self: flex-start;
  margin-left: 5%;
}

/* 프로필 */
.about__profile {
  margin-top: 20px;
}

.about__avatar {
  width: 150px;
  height: 150px;
  border-radius: 50%;
}

/* 해시태그 */
.about__tags {
  margin-top: 15px;
  display: flex;
  gap: 10px;
}

.about__tags span {
  background: rgba(255, 255, 255, 0.1);
  padding: 5px 10px;
  border-radius: 5px;
}

/* 팀원 리뷰 버튼 */
.about__review-btn {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 1rem;
  border: none;
  background-color: white;
  color: black;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.about__review-btn:hover {
  background-color: #f1f1f1;
}

/* 인터뷰 */
.about__interview {
  margin-top: 40px;
  width: 80%;
}

.about__qa {
  margin-top: 20px;
  background: rgba(255, 255, 255, 0.1);
  padding: 15px;
  border-radius: 10px;
}
</style>
