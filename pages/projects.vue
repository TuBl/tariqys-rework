<template>
  <div class="container">
    <Project
      :title="`Rick and morty Application`"
      :description="`This was a test for a a job application that I had. It was one of the most interesting and educational assignments
      that I ever had, I got to play around with Docker, Google Kuberbetes Engine and many more interesting technologies`"
      :tags="['React', 'Docker', 'GKE', 'GraphQL']"
      :image="{
        src: 'project5.png',
        alt:
          'Image showing a rick & morty application using rickandmortyapi.com',
      }"
      :slug="`http://34.67.79.233/`"
    ></Project>
    <Project
      :title="`Weather Application`"
      :description="`I used this application in order to practice animating SVG images. The
          application utilizes openweathermap API to provide accurate weather
          conditions. the front-end vue application renders different animated
          illustration based on the weather.`"
      :tags="['Vue', 'SaaS', 'SVG']"
      :alternate="true"      
      :image="{
        src: 'project1.png',
        alt:
          'Image showing a simple weather application using Openweathermap API',
      }"
      :slug="`https://tubi-weather.netlify.app/`"
    ></Project>
    <Project
      :title="`Quantumzero.net`"
      :description="`QuantumZero Inc is an organization located in dubai, UAE. they specialize in building gaming and workstations to order.
       this project included designing and building their company website.`"
      :tags="['Vue', 'SaaS', 'Bluehost']"
      :image="{
        src: 'project2.png',
        alt:
          'Image showing a client website quantumzero.net, to demonstrate work for my portofolio',
      }"
      :slug="`https://quantumzero.net/`"
    ></Project>
    <Project
      :title="`YelpCamp`"
      :description="`My first functional project ever! Using EJS templates, NodeJS, MongoDB to deliver Campsites review website with Registration, Logins, posts, comments and more!.
       I like to look at it to see how far I've come since I began this journey.`"
      :tags="['HTML', 'CSS', 'Mongo', 'ExpressJS', 'NodeJS', 'EJS']"
      :alternate="true"
      :image="{
        src: 'project3.png',
        alt:
          'Image showing a personal project featuring a Yelp style campsite review website.',
      }"
      :slug="`https://immense-bayou-20235.herokuapp.com/`"
    ></Project>
    <Project
      :title="`Dev-Connector`"
      :description="`Personal Project: A social network web app with signup, 
      login, personal profiles, posts, comments, feed, like and unlike system and more.`"
      :tags="['MERN', 'Redux', 'Heroku']"
      :image="{
        src: 'project4.png',
        alt:
          'Image showing a personal project Dev-Connector. A social network application for developers',
      }"
      :slug="`https://agile-temple-78256.herokuapp.com/`"
    ></Project>
    <Project
      :title="`Design portofolio`"
      :description="`Collection of website designs that I have worked on for clients, these were done in Figma, utilizing resources like patternpad,
      adobe colors, coolor and many more!`"
      :tags="['Figma', 'Coolors']"
      :alternate="true"
      :image="{
        src: 'project6.png',
        alt:
          'Image showing a personal project Dev-Connector. A social network application for developers',
      }"
      :slug="`https://docs.google.com/document/d/113T3qKyADpXJBQZqN1sSOfCj-3Ux6EZkIuuWF2q21EU/edit?usp=sharing`"
    ></Project>
    <Social></Social>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style scoped>
.container {
  margin-top: 5rem;
}
</style>
