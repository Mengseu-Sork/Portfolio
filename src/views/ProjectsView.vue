<template>
  <section
    id="projects"
    class="py-16 px-4 sm:px-6 lg:px-8 bg-white/80 backdrop-blur-sm relative"
  >
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-12" ref="projectsTitle">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">My Projects</h2>
        <div class="w-20 h-1 bg-gradient-to-r from-sky-500 to-blue-600 mx-auto"></div>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto mt-4">
          Explore my latest work and creative solutions
        </p>
      </div>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8" ref="projectsGrid">
        <Card
          v-for="(project, index) in projects"
          :key="project.id"
          :project="project"
          :index="index"
          @toggle-details="toggleProjectDetails(project.id)"
        />
      </div>
      <div class="text-center mt-12">
        <button
          class="bg-gradient-to-r from-sky-500 via-blue-600 to-purple-600 text-white px-8 py-3 rounded-full font-semibold hover:shadow-2xl transform hover:-translate-y-2 transition-all duration-300 hover:scale-105"
        >
          View All Projects
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import Card from "@/components/Card.vue";

const expandedProjects = ref([]);
const projects = [
  {
    id: 1,
    name: "Fruit Shop Website",
    description:
      "An online platform for browsing, purchasing, and managing fresh fruits with user-friendly interfaces and real-time stock updates.",
    image: "/image/Vue_website.jpg",
    technologies: [
      "HTML",
      "CSS",
      "JavaScript",
      "Tailwind",
      "VueJS",
      "Git",
      "GitHub",
      "Vercel",
    ],
    role: "Individual",
    status: "live",
    duration: "2 weeks",
    teamSize: "1 people",
    liveUrl: "https://interface-pearl-two.vercel.app/",
    repositoryUrl: "https://github.com/Mengseu-Sork/Interface",
    details: [
      "Implemented real-time inventory tracking system",
      "Created comprehensive sales analytics dashboard",
      "Developed customer management features",
      "Built automated reporting system",
      "Integrated payment processing",
    ],
  },
  {
    id: 2,
    name: "Cafe Shop Management System",
    description:
      "A comprehensive management system for cafe operations with revenue analysis and inventory tracking.",
    image: "/image/cofe_shop.jpg",
    technologies: [
      "HTML",
      "CSS",
      "JavaScript",
      "PHP",
      "MySQL",
      "Chart.js",
      "GitHub",
      "Git",
      "Tailwind",
      "Jira",
    ],
    role: "Scrum Master",
    status: "completed",
    duration: "1 months",
    teamSize: "5 people",
    liveUrl: null,
    repositoryUrl: "https://github.com/Mengseu-Sork/VC1-G7",
    details: [
      "Implemented real-time inventory tracking system",
      "Created comprehensive sales analytics dashboard",
      "Developed customer management features",
      "Built automated reporting system",
      "Integrated payment processing",
    ],
  },
  {
    id: 3,
    name: "Music App Player",
    description:
      "A sleek and responsive music streaming app featuring real-time audio playback, personalized playlists, and seamless user experience.",
    image: "/image/music_app.png",
    technologies: [
      "HTML",
      "CSS",
      "JavaScript",
      "Firebase",
      "Bootstrap",
      "GitHub",
      "Git",
      "Netlify",
    ],
    role: "Team Lead",
    status: "live",
    duration: "2 weeks",
    teamSize: "3 people",
    liveUrl: "https://creative-pixie-beb05b.netlify.app/",
    repositoryUrl: "https://github.com/Mengseu-Sork/MUSIC-PLAYER-APP_-G11",
    details: [
      "Designed and built a responsive music player UI",
      "Implemented real-time audio playback controls (play, pause, next, prev)",
      "Integrated playlist and queue management",
      "Added user login and profile support",
      "Connected with third-party audio APIs for streaming",
    ],
  },
  {
    id: 4,
    name: "Web Scraping Aotumation",
    description:
      "An automated tool that scrapes academic data and generates formatted certificates, transcripts, and official letters on demand.",
    image: "/image/scrping.jpg",
    technologies: ["Python", "Tkinter", "Pandas", "HTML", "CSS", "Git", "GitHub"],
    role: "Team Lead",
    status: "completed",
    duration: "2 weeks",
    teamSize: "3 people",
    liveUrl: null,
    repositoryUrl: "https://github.com/Mengseu-Sork/WEB-SCRAPING-AUTOMATION",
    details: [
      "Automated certificate generation from Excel data",
      "Created customizable document templates",
      "Implemented batch processing capabilities",
      "Built user-friendly GUI interface",
      "Added PDF export functionality",
    ],
  },
  {
    id: 5,
    name: "Library Website",
    description:
      "A user-friendly web platform that allows members to browse books, manage borrowing records, and track library activities.",
    image: "/image/library.jpg",
    technologies: ["HTML", "CSS", "Sass", "Git", "GitHub", "Figma", "Firebase"],
    role: "Team Lead",
    status: "live",
    duration: "2 weeks",
    teamSize: "3 people",
    liveUrl: "https://library-c6.netlify.app/",
    repositoryUrl: "https://github.com/Mengseu-Sork/Library-C6",
    details: [
      "Automated certificate generation from Excel data",
      "Created customizable document templates",
      "Implemented batch processing capabilities",
      "Built user-friendly GUI interface",
      "Added PDF export functionality",
    ],
  },
];

const toggleProjectDetails = (projectId) => {
  const index = expandedProjects.value.indexOf(projectId);
  if (index > -1) {
    expandedProjects.value.splice(index, 1);
  } else {
    expandedProjects.value.push(projectId);
  }
};
</script>
