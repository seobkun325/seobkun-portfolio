<template>
  <section class="about">
    <h2 class="about__title">About me</h2>

    <!-- 프로필 이모지 -->
    <div class="about__profile">
      <!-- <img src="../assets/image/avatar.png" alt="Profile" class="about__avatar" /> -->
    </div>

    <!-- 해시태그 -->
    <div class="about__tags">
      <span>#???</span>
      <span>#????</span>
      <span>#??</span>
      <span>#?????</span>
    </div>

    <!-- 인터뷰 섹션 -->
    <div class="about__interview">
      <h3>Interview</h3>
      <div class="about__qa">
        <div class="q">Q. 프론트엔드를 선택한 이유?</div>
        <div class="a">
          프론트엔드는 사용자가 가장 먼저 접하는 영역이자, 서비스의 직관성과 편의성을 결정짓는 중요한 요소라고
          생각합니다. 단순히 UI를 개발하는 것이 아니라, 사용자의 니즈를 반영하여 더 효율적이고 직관적인 경험을 제공하는
          과정이 매력적이었습니다. 특히, 데이터를 단순히 보여주는 것이 아니라 의미 있는 정보로 가공하여 전달하는 데이터
          시각화에 관심이 많았고, 이를 효과적으로 구현할 수 있는 분야가 프론트엔드라고 생각하여 선택하게 되었습니다.
        </div>
      </div>
      <div class="about__qa">
        <div class="q">Q. 스마트팩토리를 도메인으로 선택한 이유?</div>
        <div class="a">
          스마트팩토리는 단순한 자동화를 넘어, 데이터를 기반으로 공정을 최적화하고 실시간 모니터링을 통해 생산성을
          극대화하는 방향으로 발전하고 있습니다. 저는 이러한 스마트팩토리 환경에서 데이터 시각화와 디지털 트윈 기술이
          중요한 역할을 한다고 생각했습니다. 공장 내에서 발생하는 방대한 데이터를 직관적으로 표현하고, 이를 통해
          엔지니어들이 더 쉽게 문제를 분석하고 의사결정을 내릴 수 있도록 돕는 웹 플랫폼을 개발하는 것이 매우 가치 있는
          일이라 판단하여 스마트팩토리를 도메인으로 선택하게 되었습니다.
        </div>
      </div>
      <div class="about__qa">
        <div class="q">Q. 일에 있어 중요하게 생각하는 것은?</div>
        <div class="a">
          저는 문제를 끝까지 해결하는 <span class="a__highlight">책임감</span> 과
          <span class="a__highlight">끊임없는 성장</span> 을 중요하게 생각합니다. 개발을 하다 보면 예상치 못한 오류나
          해결해야 할 문제들이 계속해서 발생합니다. 이때, 단순히 코드만 작성하는 것이 아니라 왜 이런 문제가 발생했는지,
          더 나은 해결 방법은 없는지 고민하는 태도가 중요하다고 생각합니다. 또한, 빠르게 변화하는 기술 환경에서
          지속적으로 학습하고 새로운 기술을 적용하는 자세도 중요하다고 생각하며, 이를 위해 꾸준히 자기계발을 실천하고
          있습니다.
        </div>
      </div>

      <div class="about__qa">
        <div class="q">Q. 자기계발을 위해 어떠한 것들을 해왔는지?</div>
        <div class="a">
          _"저는 자기계발을 위해 다양한 방식으로 학습하고 성장해왔습니다. 1️⃣ 프로젝트 경험: 실제 데이터를 활용한
          프로젝트를 진행하며, 데이터 시각화 및 디지털 트윈 기술을 적용해보았습니다. 이를 통해 Vue.js, WebGL, Three.js,
          Babylon.js 등의 기술을 실무에 적용하는 경험을 쌓았습니다. 2️⃣ 스터디 & 부트캠프: 개발 역량을 높이기 위해
          스마트팩토리 관련 부트캠프에 참여하고, CS 기초(자료구조, 운영체제, 네트워크) 스터디를 병행하며 이론적인
          이해도를 높였습니다. 3️⃣ 기술 블로그 & 오픈소스 기여: 학습한 내용을 정리하여 기술 블로그에 기록하고, 오픈소스
          프로젝트에 기여하며 협업 능력을 키웠습니다.
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
</style>
