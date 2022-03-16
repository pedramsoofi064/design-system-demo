<template>
  <div class="hello">
    <div class="message">{{ msg }}</div>
    {{ theme }}
    <div class="theme-handling">
      <button @click="changeTheme('dark')">dark theme</button>
      <button @click="changeTheme('ligth')">ligth theme</button>
    </div>

    <div class="test-elevation elevation-2">this is a example for seeing elevation</div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    changeTheme(theme) {
      const root = document.querySelector(":root");
      root.setAttribute("theme", theme);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/abstracts";
@import "@/assets/style/tools/typography";
@import "@/assets/style/tools/spacing";

.message {
  margin: 40px 0 0;
  @include typography(h1);
}
.theme-handling {
  margin-top: 50px;

  > button {
    cursor: pointer;
    padding: 10px;
    border-radius: $border-radius;
    background-color: var(--clr-primary);
    color: var(--text-primary);

    &:first-child {
      margin-right: space(4);
    }
  }
}

.test-elevation {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: space(10);;
  
}
</style>
