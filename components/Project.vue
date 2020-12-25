<template>
  <section class="project">
    <h2 class="project__title">{{ title }}</h2>
    <article
      :class="[
        'project__container',
        alternate ? 'project__container--alternate' : '',
      ]"
    >
      <a :href="slug" target="_blank" rel="nonereferrer">
        <div
          :class="[
            'project__display',
            alternate ? 'project__display--alternate' : '',
          ]"
        >
          <img :src="require(`@/assets/${image.src}`)" :alt="image.alt" />
        </div>
      </a>

      <div
        :class="[
          'project__description',
          alternate ? 'project__description--alternate' : '',
        ]"
      >
        <transition name="slide">
          <p>
            {{ description }}
          </p>
        </transition>
        <div
          :class="[
            'project__tags',
            alternate ? 'project__tags--alternate' : '',
          ]"
        >
          <ul>
            <li v-for="tag in tags" :key="tag">{{ tag }}</li>
          </ul>
        </div>
      </div>
    </article>
  </section>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    tags: {
      type: Array,
      required: true,
    },
    alternate: {
      type: Boolean,
      default: false,
    },
    image: {
      type: Object,
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
a {
  height: auto;
  width: 50%;
  margin: 0;
  padding: 0;
}
.project {
  color: var(--text);
  font-family: Montserrat Alternates;
  margin-bottom: 5rem;
  &__title {
    font-style: normal;
    font-weight: normal;
    font-size: unquote('clamp(1rem, 0.2500rem + 3.3333vw, 2.5rem)');
    padding-bottom: 5rem;
  }

  &__container {
    display: flex;
    &--alternate {
      flex-direction: row-reverse;
    }
  }

  &__display {
    width: 100%;
    animation: slide-right 1000ms;
    &--alternate {
      animation: slide-left 1000ms;
    }
  }
  &__description {
    border-left: 5px solid var(--alternate-color);
    width: 50%;
    height: auto;
    display: flex;
    flex-direction: column;
    p {
      font-family: Moul;
      font-style: normal;
      font-weight: normal;
      line-height: 3rem;
      font-size: unquote('clamp(1.4rem, 2.5vw, 1.7rem)');
      text-align: justify;
      flex-grow: 2;
      margin-block-start: 1em;
      padding-left: 1rem;
      animation: slide-left 1000ms;
    }
    &--alternate {
      border-left: none;
      border-right: 5px solid var(--alternate-color);
      p {
        padding-left: 0rem;
        padding-right: 1rem;
        animation: slide-right 1000ms;
      }
    }
  }
  &__tags {
    display: flex;
    align-items: flex-end;
    flex-grow: 1;
    ul {
      padding-left: 1rem;
      display: flex;
      flex-wrap: wrap;
    }
    li {
      display: inline-block;
      text-align: center;
      padding: 0.5rem;
      margin: 0.2rem;
      margin-left: 0rem;
      width: 10rem;
      font-size: unquote('clamp(.8rem, 0.2500rem + 3.3333vw, 1.5rem)');
      border: 2px solid var(--alternate-color);
      border-radius: 40px;
      animation: slide-left 1000ms;
    }
    &--alternate {
      justify-content: flex-end;
      animation: slide-right 1000ms;
      ul {
        padding-left: 0rem;
        padding-right: 1rem;
      }
    }
  }
}

@media only screen and(max-width: 1170px) {
  .project {
    &__container {
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    &__display {
      margin-bottom: 2.5rem;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    &__description {
      border: none;
      width: 100%;
      border-top: 5px solid var(--alternate-color);
      border-bottom: 5px solid var(--alternate-color);
      border-radius: 40px;
      padding: 1rem;
      justify-content: center;
      align-items: center;
      p {
        text-align: center;
        margin-bottom: 2.5rem;
      }
    }
    &__tags {
      ul {
        justify-content: center;
      }
      li {
        width: 7rem;
      }
    }
  }
}
@media only screen and(max-width: 480px) {
  .project {
    &__description {
      width: 80%;
    }
  }
}
</style>
