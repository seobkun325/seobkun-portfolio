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
          처음 스마트팩토리에 대해 접했을 때, 단순한 자동화 시스템이 아니라
          <span class="a__highlight">데이터를 기반으로 공정을 최적화하고 실시간으로 모니터링하는 구조</span>에 흥미를
          느꼈습니다. 특히, <span class="a__highlight">디지털 트윈</span> 및
          <span class="a__highlight">데이터 시각화</span> 기술이 제조업의 효율성을 극대화하는 데 핵심적인 역할을 한다는
          점이 인상적이었습니다. 이러한 기술이 단순히 정보를 나열하는 것이 아니라, 공장 내 데이터를 직관적으로 표현하여
          실제 의사결정에 영향을 줄 수 있다는 점이 매력적이었고,
          <span class="a__highlight">스마트팩토리의 데이터 활용 가치</span>를 높이는 개발자가 되고 싶다는 목표를 가지게
          되었습니다.
        </div>
      </div>

      <div class="about__qa">
        <div class="q">Q. 프론트엔드를 선택한 이유?</div>
        <div class="a">저는 사용자가 직접 보고, 조작하는 UI를 설계하고 개발하는 과정에서 보람을 느낍니다.</div>
        <div class="a">
          프론트엔드는 단순한 화면 구현을 넘어
          <span class="a__highlight">사용자의 니즈</span>를 반영하여 더
          <span class="a__highlight">편리하고 직관적인 경험</span>을 제공하는 과정이 중요하다고 생각합니다. 특히,
          데이터를 단순히 출력하는 것이 아니라, 의미 있는 정보로
          <span class="a__highlight">가공하여 시각적으로 효과적으로 전달</span>하는 과정에 흥미를 가지게 되었고, 이를
          구현할 수 있는 분야가 프론트엔드라고 판단하여 선택하게 되었습니다.
        </div>
      </div>
      <div class="about__qa">
        <div class="q">Q. 개발에서 중요하게 생각하는 것은?</div>
        <div class="a">
          프론트엔드는 단순한 화면 개발이 아니라, <span class="a__highlight">사용자가 직관적으로 이해</span>하고
          <span class="a__highlight">편하게 사용</span>할 수 있도록 만드는 것이 중요하다고 생각합니다. Drag & Drop UI를
          설계할 때 <span class="a__highlight">직관적인 조작 방식</span>과 <span class="a__highlight">피드백</span>을
          고려하여, 사용자가 쉽게 사용할 수 있도록 신경 쓴 경험이 있으며, 항상
          <span class="a__highlight">역지사지의 태도</span>로 사용자 경험을 최우선으로 생각하며 개발하려 노력합니다.
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
  line-height: 1.9rem;
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
  margin-bottom: 40px;
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
