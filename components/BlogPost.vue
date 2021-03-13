<template>
  <nuxt-link :to="`/blog/${slug}`">
    <section class="post">
      <img src="~assets/tete.jpg" alt="" class="post__overlay" />
      <article class="post__content">
        <h2>{{ title }}</h2>
        <div class="post__captions">
          <span>{{ duration }}</span>
          <span>{{ date }}</span>
        </div>
        <div class="post__abstract">
          <p>
            {{ abstract }}
          </p>
        </div>
      </article>
      <article class="post__circle">
        <div class="post__pattern-container">
          <div class="post__pattern-container--top">
            <img
              src="~assets/iconfinder_3_Xd_Adobe_logo_logos_4373061.svg"
              alt=""
              class="post__icon"
            />
            <div class="post__info">
              <p>{{ info1 }}</p>
              <div class="post__info--secondary">
                <p>{{ info2 }}</p>
                <p>{{ info3 }}</p>
              </div>
            </div>
          </div>
          <div class="post__pattern-container--bottom">
            <p>Resource Type: {{ category }}</p>
            <p>Difficulty: Easy</p>
            <p>Author: {{ author }}</p>
          </div>
        </div>
      </article>
    </section>
  </nuxt-link>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    title: {
      type: String,
      required: true,
    },
    abstract: {
      type: String,
      required: true,
    },
    duration: {
      type: String,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
    category: {
      type: String,
      required: true,
    },
    author: {
      type: String,
      required: true,
    },
    info1: {
      type: String,
      required: true,
    },
    info2: {
      type: String,
      required: true,
    },
    info3: {
      type: String,
      required: true,
    },
    slug: {
      type: String,
      required: true,
    },
  },
})
</script>

<style lang="scss" scoped>
h2 {
  font-weight: 300;
  font-size: calc(1rem + (2.425 - 1) * (100vw - 30rem) / (123.75 - 30));
  letter-spacing: -0.1rem;
}

p,
li {
  font-family: 'Montserrat';
  font-weight: 400;
  font-size: calc(0.6rem + (1 - 0.6) * (100vw - 30rem) / (123.75 - 30));
  letter-spacing: 0.03125rem;
  line-height: 1.1875rem;
}
span {
  font-size: calc(0.75rem + (1 - 0.75) * (100vw - 30rem) / (123.75 - 30));
}
img {
  width: 100%;
  height: auto;
}
a {
  width: 100%;
}
.post {
  background-color: var(--blog-primary);
  color: var(--blog-alternate);
  display: flex;
  width: 100%;
  height: auto;
  min-height: 25rem;
  position: relative;
  margin-bottom: 3rem;
  border-radius: 2rem;
  &__overlay {
    width: 35%;
    border-top-left-radius: 1rem;
    border-bottom-left-radius: 1rem;
    background-blend-mode: overlay;
    clip-path: polygon(0 0, 62% 0, 100% 100%, 0% 100%);
  }
  h2 {
    margin-bottom: 1rem;
    color: var(--blog-alternate);
  }
  &__content {
    width: 40%;
    margin-top: 1rem;
    padding: 1rem;
    padding-left: 0rem;
  }
  &__captions {
    width: 100%;
    display: flex;
    justify-content: space-between;
    margin-bottom: 2rem;
  }
  &__circle {
    align-self: center;
    width: 21.875rem;
    height: 21.875rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: var(--blog-primary);
    background-color: var(--blog-alternate);
    border-radius: 50%;
  }
  &__post-info {
    font-size: calc(0.75rem + (1 - 0.75) * (100vw - 30rem) / (123.75 - 30));
  }
  &__pattern-container {
    height: 50%;
    width: 90%;
    padding: 1rem;
    position: relative;
    p {
      font-size: calc(
        0.625rem + (0.625 - 0.525) * (100vw - 30rem) / (123.75 - 30)
      );
      font-family: 'Rubik', sans-serif;
      font-weight: normal;
      letter-spacing: 13%;
      color: var(--blog-dark--primary);
    }
    &--top {
      display: flex;
      justify-content: space-evenly;
      margin-bottom: 1rem;
      align-items: flex-start;
    }
    &--bottom {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      text-align: justify;
      padding-left: 1.8125rem;
    }
  }
  &__pattern-container::after {
    content: '';
    height: 100%;
    width: 100%;
    position: absolute;
    border-radius: 0.375rem;
    background: url('~assets/patternpad.svg') 50% 50% / cover no-repeat;
    top: 0;
    left: 0;
    opacity: 0.1;
  }
  &__icon {
    width: 1.5rem;
    height: 1.5rem;
    margin-top: 0.4rem;
  }
}

.post:hover {
  transform: translateY(-5px);
  transition: transform 100ms ease-in-out;
}
@media only screen and(max-width: 768px) {
  h2 {
    letter-spacing: 0rem;
  }
  .post {
    border-top-left-radius: 1.2rem;
    border-top-right-radius: 1.2rem;
    flex-direction: column;
    &__overlay {
      width: 100%;
      border-radius: 1rem;
      border-bottom-right-radius: 0rem;
      border-bottom-left-radius: 0rem;
      height: 25%;
      max-height: 250px;
      clip-path: none;
    }
    &__content {
      width: 100%;
      height: 50%;
      padding-right: 1.5rem;
      padding-left: 1rem;
      min-height: 200px;
    }
    &__captions {
      margin-bottom: 1rem;
    }
    &__circle {
      align-self: center;
      width: 100%;
      height: 25%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      //from circle to square
      border-radius: 0%;
    }
    &__post-info {
      font-size: calc(0.75rem + (1 - 0.75) * (100vw - 30rem) / (123.75 - 30));
    }
    &__pattern-container {
      width: 100%;
      padding: 1rem;
      display: flex;
      align-items: flex-start;
      justify-content: space-evenly;
      &--top {
        justify-content: flex-start;
      }
      &--bottom {
        align-items: flex-start;
      }
    }
    &__icon {
      margin-right: 1rem;
    }
  }
}
</style>
