<template>
  <div class="max-w-7xl m-center pt-48 pb-20">
    <div
      class="skills text-center mt-10"
      data-aos="fade-up"
      data-aos-delay="100"
      data-aos-duration="800"
    >
      <h2 class="text-5xl dark:text-white">Skills</h2>
      <span class="f-gray text-sm dark:text-white">My Technical Level</span>
    </div>
    <div
      class="skill-details grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-20"
    >
      <div
        v-for="(group, index) in groups"
        :key="group.title"
        data-aos="fade-up"
        data-aos-duration="800"
        :data-aos-delay="100 + index * 100"
        class="card bg-white drop-shadow-2xl dark:bg-slate-800 flex flex-col"
      >
        <h2 class="pt-6 px-5 pb-4 flex items-center gap-3">
          <font-awesome-icon
            class="text-2xl f-blue"
            :icon="['fas', group.fa]"
          />
          <h3
            class="text-lg font-extrabold dark:text-white leading-tight"
            :title="group.title"
          >
            {{ group.title }}
          </h3>
        </h2>
        <div
          class="description grid grid-cols-2 gap-3 m-auto w-full px-5 pb-6"
        >
          <div v-for="skill in group.skills" :key="skill.name" class="p-1 card-mini">
            <div class="h-9 flex items-center justify-center">
              <img
                v-if="skill.icon"
                :src="skill.icon"
                :alt="skill.name"
                class="skill-logo h-8"
              />
              <font-awesome-icon
                v-else
                :icon="['fas', skill.fa]"
                class="text-2xl dark:text-white"
              />
            </div>
            <span class="dark:text-white">{{ skill.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import javascript from "@/assets/img/skills/javascript.svg";
import typescript from "@/assets/img/skills/typescript.svg";
import php from "@/assets/img/skills/php.svg";
import react from "@/assets/img/skills/react.svg";
import reactnative from "@/assets/img/skills/reactnative.svg";
import vuejs from "@/assets/img/skills/vuejs.svg";
import nextjs from "@/assets/img/skills/nextjs.svg";
import nodejs from "@/assets/img/skills/nodejs.svg";
import express from "@/assets/img/skills/express.svg";
import mysql from "@/assets/img/skills/mysql.svg";
import mongodb from "@/assets/img/skills/mongodb.svg";
import aws from "@/assets/img/skills/aws.svg";
import docker from "@/assets/img/skills/docker.svg";
import git from "@/assets/img/skills/git.svg";

type Skill = {
  name: string;
  icon?: string;
  fa?: string;
};

type SkillGroup = {
  title: string;
  fa: string;
  skills: Skill[];
};

const groups: SkillGroup[] = [
  {
    title: "Programming",
    fa: "code",
    skills: [
      { name: "JavaScript", icon: javascript },
      { name: "TypeScript", icon: typescript },
      { name: "PHP", icon: php },
    ],
  },
  {
    title: "Frontend",
    fa: "display",
    skills: [
      { name: "React", icon: react },
      { name: "React Native", icon: reactnative },
      { name: "Vue.js", icon: vuejs },
      { name: "Next.js", icon: nextjs },
    ],
  },
  {
    title: "Backend & APIs",
    fa: "server",
    skills: [
      { name: "Node.js", icon: nodejs },
      { name: "Express.js", icon: express },
      { name: "REST APIs", fa: "arrows-rotate" },
      { name: "API Integration", fa: "plug" },
    ],
  },
  {
    title: "Databases",
    fa: "database",
    skills: [
      { name: "SQL", fa: "table" },
      { name: "MySQL", icon: mysql },
      { name: "NoSQL", icon: mongodb },
    ],
  },
  {
    title: "Cloud & DevOps",
    fa: "cloud",
    skills: [
      { name: "AWS", icon: aws },
      { name: "Docker", icon: docker },
      { name: "Git", icon: git },
      { name: "CI/CD", fa: "rotate" },
    ],
  },
  {
    title: "Development Practices",
    fa: "clipboard-check",
    skills: [
      { name: "Agile / Scrum", fa: "people-group" },
      { name: "Code Review", fa: "code-branch" },
    ],
  },
  {
    title: "AI-Assisted Development",
    fa: "wand-magic-sparkles",
    skills: [
      { name: "BMAD", fa: "diagram-project" },
      { name: "GitHub Spec Kit", fa: "file-code" },
      { name: "AI Workflows", fa: "robot" },
    ],
  },
];
</script>

<style lang="scss" scoped>
/* Logos are single-path black SVGs, so a neutral black -> white flip is
   all that dark mode needs. No hue shifting, so brand silhouettes stay true. */
.dark .skill-logo {
  filter: invert(1);
}

/* The global .card-mini hover scales 1.3, which overlaps inside a 2-column
   chip grid. Tone it down for this layout. */
.card-mini:hover {
  transform: scale(1.08);
}
</style>
