<template>
  <div class="hello">
    <h3>{{ msg }}</h3>
    <div class="theme-handling">
      <button @click="changeTheme">change theme</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    changeTheme() {
      const root = document.querySelector(':root');
      const theme = root.getAttribute('theme')
      root.setAttribute('theme' , theme == 'ligth' ? 'dark' : 'ligth')
    }
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/sass/utilities/typography.scss";
@import "@/assets/sass/abstracts";

h3 {
  @include typography-H3;
  margin: 40px 0 0;
  $c : green;
  --c : $c;
  color: var(--c);
  $c : red;
}
.theme-handling {
  margin-top: 50px;
  > button {
    cursor: pointer;
    @include typography-bold;
    padding: 10px;
    border-radius: $border-radius;
    background-color: var(--clr-primary);
    color: var(--text-primary)
  }
}
</style>
