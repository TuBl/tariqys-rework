<template>
  <div class="icons-container">
    <a href="https://github.com/TuBl" target="_blank">
      <fa-awesome-icon
        :icon="['fab', 'github']"
        size="4x"
        class="icon github"
      ></fa-awesome-icon>
    </a>

    <a href="https://www.instagram.com/tariqys95/" target="_blank">
      <fa-awesome-icon
        :icon="['fab', 'instagram']"
        size="4x"
        class="icon instagram"
      ></fa-awesome-icon>
    </a>
    <a href="https://www.linkedin.com/in/tariqys/" target="_blank">
      <fa-awesome-icon
        :icon="['fab', 'linkedin']"
        size="4x"
        class="icon linkedin"
      ></fa-awesome-icon>
    </a>
    <a href="https://api.whatsapp.com/send?phone=+15198605430" target="_blank">
      <fa-awesome-icon
        :icon="['fab', 'whatsapp-square']"
        size="4x"
        class="icon whatsapp"
      ></fa-awesome-icon>
    </a>
  </div>
</template>

<script>
import { fab } from '@fortawesome/free-brands-svg-icons'
export default {
  name: 'Social',
  computed: {
    fab() {
      return fab
    },
  },
}
</script>

<style lang="scss" scoped>
.icons-container {
  width: 100%;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
.icon {
  color: #fffffe;
  border-radius: 50%;
  padding: 0.15em;
  width: 0.75em;
  height: 0.75em;
  margin: 0.2em;
  animation: icon-animation 1000ms ease-in-out;
}
.icon:hover {
  transform: scale(0.98);
  opacity: 0.9;
  transition: transform, opacity 200ms ease-in-out forwards;
}


.github {
  background: white;
  color: #24292e;
}
.instagram {
  background: linear-gradient(
    43.94deg,
    #eea054 16.16%,
    #d64763 50.11%,
    #b62a99 83.68%
  );
}
.linkedin {
  background-color: #0073b1;
}
.whatsapp {
  background: #48c95f;
}
.paypal {
  background: rgb(0, 90, 149);
}
@keyframes icon-animation {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@media only screen and (max-width: 414px) {
  .icon {
    color: #fffffe;
    opacity: 0;
    border-radius: 50%;
    padding: 0.07em;
    width: 0.4em;
    height: 0.4em;
    margin: 0.2em;
  }
}
</style>
