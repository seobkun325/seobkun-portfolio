<template>
  <section class="projects">
    <h2 class="projects__title">Projects</h2>

    <div class="projects__list">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <div class="project-card__content">
          <img :src="project.image" :alt="project.name" class="project-card__image" />
          <div class="project-card__info">
            <h3 class="project-card__name">{{ project.name }}</h3>
            <p class="project-card__desc">{{ project.shortDescription }}</p>
            <div class="project-card__tags">
              <span v-for="tag in project.tags" :key="tag" class="project-tag">{{ tag }}</span>
            </div>
          </div>

          <div class="project-card__overlay">
            <p class="project-card__full-desc">{{ project.name }}</p>
            <div class="project-card__buttons">
              <button class="btn" @click="openModal(project)">자세히 보기</button>
              <a v-if="project.githubLink" :href="project.githubLink" target="_blank" class="btn">GitHub 바로가기</a>
              <button v-if="project.youtubeLink" @click="openLink(project.youtubeLink)" class="btn">
                YouTube 바로가기
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- 모달 추가 -->
    <ProjectModal v-if="selectedProject" :project="selectedProject" :isOpen="isModalOpen" @close="closeModal" />
  </section>
</template>

<script setup>
import { ref } from "vue";
import ProjectModal from "./ProjectModal.vue";

// 이미지 동적 로드
const images = import.meta.glob("../assets/image/*.png", { eager: true });

// 프로젝트 데이터
const projects = ref([
  {
    id: 1,
    name: "Your Capsules",
    shortDescription: "사용자가 특정 날짜에 타임캡슐을 생성하고 보관할 수 있는 웹 플랫폼",
    description:
      "Your Capsules는 사용자가 텍스트, 이미지, 비디오, 음성 등을 기록하여 타임캡슐을 만들고, 미래에 열어볼 수 있도록 설계된 서비스입니다. 또한, 목표 캡슐을 생성하여 목표를 설정하고, 달성 여부를 추적할 수 있습니다.",
    date: "2024.05 - 2024.06",
    teamSize: "3인 (프론트 1명, 백엔드 1명, 풀스택 1명)",
    tags: ["팀", "웹", "UI/UX", "게임 요소"],
    features: [
      "타임캡슐 생성 및 텍스트, 이미지, 비디오, 음성 저장",
      "미래 일정 설정 및 캡슐 잠금/해제",
      "목표 캡슐 시스템 (목표 달성 추적 및 보상 제공)",
      "사용자 간 캡슐 공유 기능",
      "웹캠/마이크 활용하여 비디오 및 음성 메시지 녹음 가능",
      "캡슐 만료 시 자동 알림 시스템 (pgboss 스케줄링 적용)",
    ],
    role: [
      "Vue.js 기반의 프론트엔드 UI 개발 및 상태 관리 구현",
      "게임형 UX 설계를 도입하여 키보드 이벤트를 활용한 인터랙션 구현",
      "미디어 파일(이미지, 비디오, 오디오) 업로드 및 처리 기능 개발",
      "GitHub PR 리뷰 및 코드 관리, Notion을 통한 정보 공유",
    ],
    screenshots: [
      { src: "/yourCapsule/main.png", description: "로그인 화면" },
      { src: "/yourCapsule/menu.png", description: "메인 메뉴 화면" },
      { src: "/yourCapsule/createCapsule.png", description: "캡슐 생성 화면" },
      { src: "/yourCapsule/progress.png", description: "진척도 화면" },
      { src: "/yourCapsule/progressdetail.png", description: "진척도 상세보기 화면" },
      { src: "/yourCapsule/past.png", description: "캡슐 도감 화면" },
      { src: "/yourCapsule/gameuser.png", description: "게임 메뉴 화면 (유저의 집)" },
      { src: "/yourCapsule/gamecapsule.png", description: "게임 메뉴 화면 (캡슐 센터)" },
      { src: "/yourCapsule/admin.png", description: "관리자 페이지" },
    ],
    image: images["../assets/image/capsule-thumbnail.png"].default,
    color: "#FF6F61", // 포인트 컬러 적용
    githubLink: "https://github.com/seobkun325/ThreeIdiots-FE",
    youtubeLink: null,
    tech: ["JavaScript", "Vue", "HTML", "CSS"],
  },

  {
    id: 2,
    name: "Traum",
    shortDescription: "3D 오브젝트와 Live-Data 매핑의 디지털 트윈 모니터링 플랫폼",
    description:
      "Traum 프로젝트는 스마트팩토리 환경에서 실시간 데이터를 시각화하고, 3D 오브젝트를 활용하여 공장 설비와 센서 데이터를 직관적으로 표현하는 디지털 트윈 모니터링 시스템입니다. 사용자는 Drag & Drop 인터페이스를 통해 공장 내 장비를 배치하고, 라이브 데이터를 반영하여 공정 상태를 실시간으로 모니터링할 수 있습니다.",
    date: "2024.07 - 2024.08",
    teamSize: "3인 (프론트 2명, 백엔드 1명)",
    tags: ["팀", "웹", "UI/UX", "스마트팩토리", "디지털트윈"],
    features: [
      "3D 오브젝트 Drag & Drop 배치 기능 구현",
      "실시간 센서 데이터 연동 및 시각화",
      "공장 설비의 동작 상태를 UI 색상 변화로 표현",
      "MQTT 기반 실시간 모니터링 및 대시보드 제공",
      "WebSocket을 통한 원격 제어 기능",
      "블랙박스 기능을 활용한 데이터 기록 및 시뮬레이션",
    ],
    role: [
      "Babylon.js 기반의 3D 오브젝트 렌더링 및 인터랙션 구현",
      "MQTT 및 WebSocket을 활용한 실시간 데이터 연동 및 UI 반영",
      "Vue.js를 활용한 프론트엔드 개발 및 UI/UX 최적화",
      "No-Code 기반 Drag & Drop 인터페이스 설계",
      "GitHub PR 리뷰 및 코드 관리",
    ],
    screenshots: [
      { src: "/traum/1.png", description: "배치된 3D 오브젝트와 Live-Data 간의 매핑" },
      { src: "/traum/2.png", description: "Drag & Drop 형태의 사용자 친화적 웹 인터페이스 지원" },
      { src: "/traum/3.png", description: "수집 데이터 저장 및 조회 등 시계열데이터 활용에 최적화된 influxDB 활용" },
      {
        src: "/traum/7.png",
        description: "MQTT 기반 실시간 모니터링과 대시보드 제공 및, WebSocket 기반 리셋, 정지 등 원격 제어 지원",
      },
      { src: "/traum/4.png", description: "Dashboard에서 Edukit의 데이터 확인" },
      {
        src: "/traum/5.png",
        description: "문제 발생 당시 원인을 체계적으로 파악하여 향후 대응 및 AI 학습 등 활용 가능",
      },
      { src: "/traum/6.png", description: "Unity WebGL을 통해 실제 설비의 디지털복제를 통한 과거 상황 재현" },
    ],
    image: images["../assets/image/traum-thumbnail.png"].default,
    color: "#4A90E2", // 포인트 컬러 적용
    githubLink: null,
    //youtubeLink: "https://youtu.be/7OaEGdnoYcE",
    tech: ["JavaScript", "Vue", "Babylon.js", "MQTT", "WebSocket"],
  },
  {
    id: 3,
    name: "의장공정 모니터링 시스템",
    shortDescription: "자재, 생산, 품질, 설비 데이터를 실시간으로 모니터링하는 웹 플랫폼",
    description:
      "현대 아산공장 의장공정에서 실시간 데이터 모니터링을 통해 공정 가시성을 확보하고, 데이터 기반 의사 결정을 지원하는 시스템입니다. 생산 및 설비 데이터를 시각화하여 엔지니어들이 공정 상태를 쉽게 파악할 수 있도록 설계되었습니다.",
    date: "2024.12 - 2024.12",
    teamSize: "6인 (프론트 3명, 백엔드 3명)",
    tags: ["팀", "웹", "스마트팩토리", "데이터 시각화"],
    features: [
      "자재 현 재고량 및 안전재고량 실시간 조회",
      "라인별 실시간 공정 모니터링 및 가동률 분석",
      "불량 유형 및 품질 데이터를 시각적으로 분석",
      "생산 라인 및 차량 생산 현황 실시간 모니터링",
      "ECharts를 활용한 데이터 시각화",
      "Element Plus 기반 UI 컴포넌트 적용",
    ],
    role: [
      "JavaScript 및 jQuery를 활용한 UI 및 데이터 시각화 개발",
      "ECharts를 활용하여 실시간 차트 구현",
      "Element Plus를 활용한 UI 구성 및 사용자 경험 최적화",
      "HTML/CSS 기반 대시보드 스타일링 및 반응형 대응",
      "GitHub PR 리뷰 및 코드 관리, Notion을 통한 일정 관리",
    ],
    image: images["../assets/image/hyundai-thumbnail.png"].default,
    color: "#2C3E50", // 포인트 컬러 적용 (현대자동차 브랜드 컬러와 유사한 톤)
    githubLink: null,
    youtubeLink: "https://www.youtube.com/watch?v=TDZEwmIXL8Q",
    tech: ["JavaScript", "HTML", "CSS", "jQuery", "SMWP", "ECharts", "Element Plus"],
  },
  {
    id: 4,
    name: "COKKIRI",
    shortDescription: "스터디와 프로젝트 멤버를 모으고, 일정을 관리하는 플랫폼",
    description:
      "COKKIRI는 스터디와 프로젝트 멤버를 모집하고, 팀 일정 및 진행 상황을 관리할 수 있도록 돕는 웹 플랫폼입니다. 사용자는 팀을 생성하고, 일정 조율, 진행 상태 공유, 역할 분배 등을 효율적으로 수행할 수 있습니다.",
    date: "2024.11 - 진행 중",
    teamSize: "3인 (프론트 2명, 백엔드 1명)",
    tags: ["팀", "웹", "사이드 프로젝트"],
    features: [
      "스터디 및 프로젝트 팀 생성 및 관리",
      "일정 조율 및 팀원 간 실시간 일정 공유",
      "업무 역할 분배 및 진행 상태 추적",
      "Vue.js 기반의 대시보드 UI 구성",
      "Element Plus를 활용한 UI 컴포넌트 적용",
      "현재 진행 중...",
    ],
    role: [
      "Vue.js 기반의 프론트엔드 UI 개발",
      "Element Plus를 활용하여 사용자 친화적인 UI 설계",
      "HTML/CSS를 활용한 반응형 스타일링 구현",
      "팀 일정 및 상태 관리 기능 개발",
      "GitHub을 활용한 코드 협업 및 PR 리뷰",
      "현재 진행 중...",
    ],
    image: images["../assets/image/cokkiri-thumbnail.png"].default,
    color: "#F4A261", // 포인트 컬러 적용
    githubLink: null,
    youtubeLink: null,
    tech: ["Vue", "HTML", "CSS", "JavaScript"],
  },
  {
    id: 5,
    name: "Seobkun - Portfolio",
    description:
      "Seobkun - Portfolio는 Vue.js를 활용하여 개발 중인 개인 포트폴리오 웹사이트로, 개발 경험과 프로젝트를 정리하고 효과적으로 보여주기 위해 제작되었습니다. 프로젝트 섹션, 교육 섹션, 모달 기능을 포함하며, 반응형 디자인을 적용하여 다양한 해상도에서 최적의 레이아웃을 제공합니다.",
    date: "2025.01 - 진행 중",
    teamSize: "1인 (개인 프로젝트)",
    tags: ["개인", "웹", "포트폴리오"],
    features: [
      "Vue.js 기반의 SPA (Single Page Application) 구조",
      "프로젝트 및 교육 섹션을 포함한 포트폴리오 웹사이트",
      "모달 기능을 활용한 프로젝트 상세 보기",
      "SCSS를 활용한 커스텀 스타일링 및 반응형 디자인 적용",
      "반응형 UI 최적화 (맥북, 데스크탑 등 다양한 해상도 지원)",
      "현재 진행 중...",
    ],
    role: [
      "Vue.js 기반의 전체적인 UI/UX 설계 및 개발",
      "컴포넌트 기반 설계를 통해 유지보수성과 확장성을 고려한 개발",
      "SCSS를 이용하여 디자인 커스터마이징 및 반응형 스타일 적용",
      "모달 시스템을 개발하여 프로젝트 상세 보기 기능 추가",
      "GitHub을 활용한 코드 관리",
      "현재 진행 중...",
    ],
    screenshots: ["../assets/image/portfolio-1.png", "../assets/image/portfolio-2.png"],
    image: images["../assets/image/portfolio-thumbnail.png"].default,
    color: "#3b3b3b", // 포인트 컬러 적용
    githubLink: "https://github.com/seobkun325/seobkun-portfolio",
    youtubeLink: null,
    tech: ["Vue", "SCSS", "HTML", "CSS", "JavaScript"],
  },
]);

// 모달 상태 관리
const selectedProject = ref(null);
const isModalOpen = ref(false);

// 모달 열기
const openModal = (project) => {
  selectedProject.value = project;
  isModalOpen.value = true;
};

// 모달 닫기
const closeModal = () => {
  selectedProject.value = null;
  isModalOpen.value = false;
};

// 유튜브 링크 열기
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
  width: 60%;
  margin-bottom: 5%;
}

/* 프로젝트 카드 */
.project-card {
  position: relative;
  width: 100%;
  background: #353535;
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
