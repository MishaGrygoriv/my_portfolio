<template>
  <div class="top-nav">
    <ul class="top-nav__list">
      <li class="top-nav__item" v-for="route in routes" :key="route.name">
        <router-link
          active-class="_active"
          exact
          class="top-nav__link"
          :to="route.path"
          >{{ route.name }}</router-link
        >
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "TopNavBar",
  data() {
    return {
      routes: [
        {
          name: "About Me",
          path: "/about",
        },
        {
          name: "Projects",
          path: "/projects",
        },
        {
          name: "Interests",
          path: "/interests",
        },
        {
          name: "Contact",
          path: "/contact",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.top-nav {
  &__list {
    display: flex;
    margin-bottom: 0;
  }
  &__item {
    margin-right: 130px;
    position: relative;
    @include text($H90, 400, $blue-text-color);
    &:last-child {
      margin-right: 0;
    }
    &:nth-child(1) {
      &::before {
        content: "{";
        margin-right: 5px;
      }
      &::after {
        content: "}";
        margin-left: 5px;
      }
    }
    &:nth-child(2) {
      &::before {
        content: "[";
        margin-right: 5px;
      }
      &::after {
        content: "]";
        margin-left: 5px;
      }
    }
    &:nth-child(3) {
      &::after {
        content: "()";
      }
    }
    &:nth-child(4) {
      &::before {
        content: "#";
      }
    }
  }
  &__link {
    @include text($H200, 400, $text-color);
    background-color: #0f1011;
    padding: 10px;
    position: relative;
    transition: background-color 225ms cubic-bezier(0.7, 0.15, 0.3, 0.95);
    transform: translateX(-50%);
    &:hover {
      background-color: #206bff;
      color: $light-color;
      &::before {
        transform: translate3d(0, -0.35em, 0);
        background-color: #206bff;
      }
      &::after {
        transform: translate3d(0, 0.35em, 0);
        transition: background-color 225ms cubic-bezier(0.4, 0.25, 0.3, 1) 20ms,
          transform 225ms cubic-bezier(0.4, 0.25, 0.3, 1) 20ms;
        background-color: #206bff;
      }
    }
    &::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 50%;
      height: 100%;
      transform: translateZ(0);
      background-color: #0a0a0b;
      z-index: -1;
      transition: background-color 225ms cubic-bezier(0.4, 0.25, 0.3, 1),
        transform 225ms cubic-bezier(0.4, 0.25, 0.3, 1);
    }
    &::after {
      content: "";
      position: absolute;
      top: 0;
      right: 0;
      width: 50%;
      height: 100%;
      transform: translateZ(0);
      background-color: #0a0a0b;
      z-index: -1;
      transition: background-color 225ms cubic-bezier(0.4, 0.25, 0.3, 1),
        transform 225ms cubic-bezier(0.4, 0.25, 0.3, 1);
    }
    // position: relative;
    // &::before {
    //   content: "";
    //   background-color: $blue-text-color;
    //   position: absolute;
    //   width: 100%;
    //   height: 2px;
    //   bottom: -6px;
    // }
  }
}
</style>