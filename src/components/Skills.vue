<template>
  <section id="skills">
    <v-layout pa-5 justify-space-around wrap>
      <v-img :src="require('@/assets/abstract-2.png')" height="711" width="778" class="abstract-2"></v-img>
      <v-flex xs12 mb-5 position>
        <v-layout justify-space-between>
          <h2 class="display-2 font-weight-bold primary--text mb-4">What I Know</h2>
          <blockquote style="max-width:230px;">
            <p class="subheading font-weight-light font-italic">
              Need a More
              Professional
              describtion of me? Well, here's exactly that;)
            </p>
            <footer class="text-xs-center">
              <v-btn
                color="primary"
                href="https://drive.google.com/file/d/1fv4O3MIylENtRadVWQRKjVlqe0V1uF5z/view?usp=sharing"
              >
                <span>Download CV</span>
              </v-btn>
            </footer>
          </blockquote>
        </v-layout>
      </v-flex>
      <v-flex xs12 md3>
        <h3 class="headline font-weight-medium mb-4 primary--text">My Education</h3>
        <v-sheet v-for="(edu,index) in educations" :key="index" class="mb-5 transparent">
          <v-layout>
            <v-sheet class="mr-3" color="primary" height="100" width="1"></v-sheet>
            <v-flex>
              <div class="mb-3">{{edu.name}}</div>
              <div class="text-xs-right">
                <span class="title primary--text">{{edu.stream}}</span>
                <footer>
                  <div>{{edu.alt}}</div>
                  <div>{{edu.duration}}</div>
                </footer>
              </div>
            </v-flex>
          </v-layout>
        </v-sheet>
      </v-flex>
      <v-flex xs12 md4>
        <h3 class="headline font-weight-medium mb-4 primary--text">My Skills</h3>
        <div class="mb-4" v-for="(skill, index) in skills" :key="index">
          <h4 class="text-uppercase mb-3 primary--text">{{skill.skillName}}</h4>
          <div class="pl-4">
            <v-layout
              align-center
              v-for="(currentSkill, index) in skill.skillSets"
              :key="index"
              mb-4
            >
              <v-flex xs5>
                <h5 class="subheading">{{currentSkill.name}}</h5>
              </v-flex>
              <v-flex xs7>
                <v-rating
                  dense
                  readonly
                  color="primary"
                  background-color="#111"
                  :full-icon="fullIcon"
                  :empty-icon="emptyIcon"
                  :value="currentSkill.exp"
                ></v-rating>
              </v-flex>
            </v-layout>
          </div>
        </div>
      </v-flex>
    </v-layout>
  </section>
</template>

<script>
export default {
  data() {
    return {
      fullIcon: "mdi-star-circle-outline",
      emptyIcon: "mdi-star-circle-outline",
      educations: [
        {
          name: "BitDegree",
          alt: "Full Stack Web Development",
          stream: "Certification of Full-Stack Web Developer",
          duration: "2019-Present"
        },
        {
          name: "Eduonix Learning Solutions",
          alt: "Back End Development",
          stream: "Mastering PHP & MySQL",
          duration: "2018-2019"
        },
        {
          name: "Udemy",
          alt: "Front End Development",
          stream: "Front End Development",
          duration: "2017-2018"
        },
        {
          name: "National University of Bangladesh",
          alt: "Political Science",
          stream: "Bachelor of Social Science",
          duration: "2017-Present"
        },
        {
          name: "Zirabo Dewan Idris College",
          alt: "General Subjects",
          stream: "Heigher Secondary",
          duration: "2015-2017"
        },
        {
          name: "Jumarbari High School",
          alt: "General Subjects",
          stream: "Senior Secondary",
          duration: "2013-2015"
        },
        {
          name: "Kamalerpara High School",
          alt: "General Subjects",
          stream: "Junior Secondary",
          duration: "2009-2012"
        },
        {
          name: "Folia Digar Govt. Primary School",
          alt: "General Subjects",
          stream: "Primary Education",
          duration: "2004-2008"
        }
      ],
      skills: [
        {
          skillName: "Web Design",
          skillSets: [
            { name: "HTML 5", exp: 5 },
            { name: "CSS 3", exp: 4 },
            { name: "Bootstrap", exp: 5 },
            { name: "Meterilize", exp: 4 },
            { name: "SASS", exp: 5 },
            { name: "Javascript", exp: 4 },
            { name: "VueJs", exp: 5 },
            { name: "Vuetify", exp: 4 },
            { name: "ReactJs", exp: 3 },
            { name: "JQuery", exp: 5 },
          ]
        },
        {
          skillName: "Web Development & Others",
          skillSets: [
            { name: "PHP & MYSQL", exp: 4 },
            { name: "WordPress Customization", exp: 5 },
            { name: "WordPress Theme Development", exp: 5 },
            { name: "Elementor Addons Development", exp: 4 },
            { name: "WordPress Plugin Development", exp: 3 },
            { name: "ExpressJs", exp: 3 },
            { name: "MongoDB", exp: 3 },
            { name: "NodeJs", exp: 3 },
            { name: "Firebase", exp: 4 },
            { name: "Github", exp: 5 },
          ]
        }
      ]
    };
  }
};
</script>


<style scoped>
section {
  position: relative;
}

.abstract-2 {
  position: absolute !important;
  right: 0;
  top: -128px;
  z-index: 0 !important;
}

.abstract-2 ~ * {
  z-index: 1 !important;
}
</style>
