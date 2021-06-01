<template>
  <div class="header">
    <router-link class="header__logo-link" to="/">
      <span class="header__logo _logo-tag">&lt; </span>
      <span class="header__logo">Grygoriv</span>
      <span class="header__logo _logo-tag">/></span>
    </router-link>
    <top-nav-bar />
  </div>
</template>
<script>
import TopNavBar from "../top-nav-bar/TopNavBar.vue";

export default {
  components: { TopNavBar },
  name: "TheHeader",
};
</script>
<style lang="scss">
.header {
  @include flex(space-between, center);
  margin-bottom: 120px;
  &__logo {
    @include text($H240, 700, $text-color);
    &._logo-tag {
      @include text($H90, 400, $blue-text-color);
    }
  }
}
</style>