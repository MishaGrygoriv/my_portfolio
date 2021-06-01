<template>
  <div class="first-section">
    <div class="first-section__left-col">
      <h1 class="first-section__title _name">
        Michael<span class="first-section__title _surname">Grygoriv</span>
      </h1>
      <h2 class="first-section__subtitle">Front-End Developer</h2>
      <ul class="first-section__social-list">
        <li
          class="first-section__social-item"
          v-for="icon in socialIcons"
          :key="icon.name"
        >
          <a :href="icon.href" target="_blank" :class="icon.classLink">
            <i :class="icon.classIcon"></i>
          </a>
        </li>
      </ul>
    </div>
    <div class="first-section__right-col">
      <img class="first-section__img" :src="image" />
    </div>
  </div>
</template>
<script>
import image from "@/assets/michael.png";

export default {
  name: "FirstSections",
  data: function () {
    return {
      image: image,
      socialIcons: this.$store.state.socialIcons,
    };
  },
};
</script>
<style lang="scss">
.first-section {
  @include flex(space-between, stretch);
  &__title {
    @include text($H550, 700, $text-color);
    letter-spacing: 18px;
    text-align: left;
    margin-bottom: 110px;
    line-height: 122px;
    &._name {
      position: relative;
      transform: rotate(5deg);
      &:before {
        content: "Michael";
        position: absolute;
        color: #0f1011;
        opacity: 0.6;
        bottom: 67px;
        left: -52px;
        font-size: 80px;
        transform: rotate(-6deg);
      }
    }
    &._surname {
      display: block;
      font-size: 4.5rem;
      transform: rotate(-11deg);
      &::before {
        content: "Grygoriv";
        position: absolute;
        color: #0f1011;
        opacity: 0.6;
        bottom: -86px;
        left: -48px;
        font-size: 106px;
        transform: rotate(3deg);
      }
    }
  }
  &__subtitle {
    @include text($H200, 400, $blue-text-color);
    text-align: left;
    margin-bottom: 45px;
  }
  &__social-list {
    @include flex(space-between, stretch);
    margin-bottom: 0;
    max-width: 400px;
    width: 100%;
  }
  &__social-item {
    &:nth-child(1) .first-section__social-link {
      animation-delay: 0s;
    }
    &:nth-child(2) .first-section__social-link {
      animation-delay: 0.07s;
    }
    &:nth-child(3) .first-section__social-link {
      animation-delay: 0.14s;
    }
    &:nth-child(4) .first-section__social-link {
      animation-delay: 0.21s;
    }
  }
  &__social-link {
    overflow: hidden;
    display: block;
    width: 45px;
    height: 45px;
    text-align: center;
    color: $text-color;
    border: 2px solid $social-color;
    background-color: $social-color;
    border-radius: 50%;
    line-height: 3.1;
    transition: all 0.4s ease-in-out;
    animation: bouncy 5s infinite linear;
    position: relative;
    &:hover {
      transform: rotate(360deg) scale(1.2);
      color: $light-color;
      &._github {
        background: #5a32a3;
        border: 2px solid rgba(#5a32a3, 0.7);
        box-shadow: 0 0 0 4px rgba(#5a32a3, 0.4);
        color: $dark-color;
      }
      &._linkedin {
        background: #0077b5;
        border: 2px solid rgba(#0077b5, 0.7);
        box-shadow: 0 0 0 4px rgba(#0077b5, 0.4);
      }
      &._instagram {
        background: radial-gradient(
          circle at 30% 107%,
          #fdf497 0%,
          #fdf497 5%,
          #fd5949 45%,
          #d6249f 60%,
          #285aeb 90%
        );
        border: 2px solid rgba(#e4405f, 0.7);
        box-shadow: 0 0 0 4px rgba(#e4405f, 0.4);
      }
      &._resume {
        background: #cb2027;
        border: 2px solid rgba(#cb2027, 0.7);
        box-shadow: 0 0 0 4px rgba(#cb2027, 0.4);
      }
    }
  }
  &__social-icon {
    font-size: $H300;
  }
  &__right-col {
    @include flex(space-around, stretch);
  }
  &__img {
    width: 430px;
    position: relative;
    right: 50px;
    bottom: 20px;
  }
}
@keyframes bouncy {
  0% {
    top: 0em;
  }
  40% {
    top: 0em;
  }
  43% {
    top: -0.9em;
  }
  46% {
    top: 0em;
  }
  48% {
    top: -0.4em;
  }
  50% {
    top: 0em;
  }
  100% {
    top: 0em;
  }
}
</style>