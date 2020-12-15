<template>
  <section class="project">
    <h2 class="project__title">Weather Application</h2>
    <article class="project__container">
      <div class="project__display">
        <img
          src="~/assets/project1_image.png"
          alt="Image showing a simple weather application using Openweathermap API"
        />
      </div>
      <div class="project__description">
        <p>
          I used this application in order to practice animating SVG images. The
          application utilizes openweathermap API to provide accurate weather
          conditions. the front-end vue application renders different animated
          illustration based on the weather.
        </p>
        <div class="project__tags">
          <ul>
            <li>Vue</li>
            <li>SaaS</li>
            <li>SVG</li>
          </ul>
        </div>
      </div>
    </article>
  </section>
</template>

<style lang="scss" scoped>
.project {
  color: var(--primary-color);
  font-family: Montserrat Alternates;
  &__title {
    font-style: normal;
    font-weight: normal;
    font-size: unquote('clamp(1rem, 0.2500rem + 3.3333vw, 2.5rem)');
    padding-bottom: 5rem;
  }

  &__container {
    display: flex;
  }

  &__display {
    width: 50%;
  }

  &__description {
    border-left: 5px solid var(--primary-color);
    width: 50%;
    height: auto;
    display: flex;
    flex-direction: column;
    p {
      font-family: Moul;
      font-style: normal;
      font-weight: normal;
      line-height: 3rem;
      font-size: unquote('clamp(1rem, 2.5vw, 1.7rem)');
      text-align: justify;
      flex-grow: 2;
      margin-block-start: 1em;
      padding-left: 1rem;
      color: var(--alternate-color);
    }
  }
  &__tags {
    display: flex;
    align-items: flex-end;
    flex-grow: 1;
    ul {
      list-style: none;
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
      border: 2px solid var(--primary-color);
      border-radius: 40px;
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
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    &__description {
      border-left: none;
      width: 100%;
      border-top: 5px solid var(--primary-color);
      background: #3b3a3a;
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
</style>
