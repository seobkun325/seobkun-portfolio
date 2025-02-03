<template>
  <section class="about">
    <h2 class="about__title">About me</h2>

    <!-- 프로필 이미지 -->
    <div class="about__profile">
      <img src="/me.png" alt="Profile" class="about__avatar" />
    </div>

    <!-- 해시태그 -->
    <div class="about__tags">
      <span>#역지사지</span>
      <span>#끈기</span>
      <span>#도전정신</span>
      <span>#문제해결</span>
    </div>

    <!-- 인터뷰 섹션 -->
    <div class="about__interview">
      <h3 class="sub__title">Interview</h3>

      <div class="about__qa">
        <div class="q">Q. 스마트팩토리를 도메인으로 선택한 이유?</div>
        <div class="a">
          스마트팩토리는 단순한 자동화를 넘어, 데이터를 기반으로 공정을 최적화하고
          <span class="a__highlight">실시간 모니터링을 통해 생산성을 극대화</span>하는 방향으로 발전하고 있습니다. 저는
          이러한 스마트팩토리 환경에서 <span class="a__highlight">데이터 시각화</span>와
          <span class="a__highlight">디지털 트윈 기술</span>이 중요한 역할을 한다고 생각했습니다.
        </div>
      </div>

      <div class="about__qa">
        <div class="q">Q. 프론트엔드를 선택한 이유?</div>
        <div class="a">
          프론트엔드는 사용자가 가장 먼저 접하는 영역이자, 서비스의
          <span class="a__highlight">직관성과 편의성을 결정짓는 중요한 요소</span>라고 생각합니다. 단순히 UI를 개발하는
          것이 아니라, 사용자의 니즈를 반영하여
          <span class="a__highlight">더 효율적이고 직관적인 경험을 제공하는 과정</span>이 매력적이었습니다.
        </div>
      </div>
    </div>

    <!-- Skills & Tools 섹션 -->
    <div class="skills">
      <h3 class="sub__title">Skill & Tools</h3>
      <div class="skills__container">
        <div class="skills__category">
          <h4>Front-End</h4>
          <div class="skills__list">
            <div class="skill-card">
              <img src="/icons/html.svg" alt="HTML" />
              <!-- <span>HTML</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/css.svg" alt="CSS" />
              <!-- <span>CSS</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/javascript.svg" alt="JavaScript" />
              <!-- <span>JavaScript</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/vue.svg" alt="vue" />
              <!-- <span>Vue</span> -->
            </div>
          </div>
        </div>

        <div class="skills__category">
          <h4>Tools</h4>
          <div class="skills__list">
            <div class="skill-card">
              <img src="/icons/figma.svg" alt="Figma" />
              <!-- <span>Figma</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/blender.svg" alt="Blender" />
              <!-- <span>Figma</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/github.svg" alt="GitHub" />
              <!-- <span>GitHub</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/notion.svg" alt="Notion" />
              <!-- <span>Notion</span> -->
            </div>
            <div class="skill-card">
              <img src="/icons/slack.svg" alt="slack" />
              <!-- <span>Slack</span> -->
            </div>
          </div>
        </div>
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
  justify-content: flex-start;
  text-align: center;
  padding: 40px 0px;
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
  width: 250px;
  height: 250px;
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
  width: 60%;
  padding: 1%;
}

.about__qa {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
  background: rgba(255, 255, 255, 0.1);
  padding: 20px;
  border-radius: 10px;
  margin-bottom: 30px;
}
.q {
  font-weight: bold;
  font-size: 1.5rem;
  text-align: left;
  margin-bottom: 1rem;
}
.a {
  font-size: 1rem;
  text-align: left;
  font-weight: 300;
  line-height: 2rem;
}
.a__highlight {
  background-color: rgb(25, 25, 25);
  color: white;
  padding: 4px 4px;
  border-radius: 5px;
  font-weight: 600;
  display: inline; /* 문장 속에서 자연스럽게 이어지도록 변경 */
}

.skills {
  width: 60%;
  margin-top: 50px;
  text-align: center;
}

.sub__title {
  font-size: 2rem;
  font-weight: bold;
  text-align: left;
  margin-bottom: 20px;
}

.skills__container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}

.skills__category {
  flex: 1;
  min-width: 300px;
}

.skills__category h4 {
  font-size: 1.5rem;
  margin-bottom: 30px;
  text-align: left;
}

.skills__list {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.skill-card {
  background: rgba(59, 59, 59, 0.801);
  padding: 15px;
  border-radius: 10px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  /* width: 40px; */
}

.skill-card img {
  width: 30px;
  height: 30px;
  /* margin-bottom: 10px; */
}

.skill-card span {
  font-size: 0.9rem;
  font-weight: 600;
}
</style>
