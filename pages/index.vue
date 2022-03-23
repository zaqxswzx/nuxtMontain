<script>
import axios from "axios";
export default {
  head: {
    title: "Home Page",
    meta: [
      { hid: "description", name: "description", content: "你好歡迎光臨" },
    ],
  },
  data() {
    return {
      // sendtype: "text",
      sendtype: "select",
      num: 0,
      name: "",
      city: "",
    };
  },
  async asyncData() {
    let getApi = { data: {} };
    try {
      await axios
        .get("https://mocki.io/v1/2e44221f-0b30-4d8e-8d26-17c514214e21")
        .then((res) => {
          console.log(res.data.name);
          getApi.data = res.data;
        });
      console.log(getApi.data);
    } catch (error) {
      console.dir(error);
    }
    return {
      getApi,
    };
  },
  computed: {
    theData() {
      this.num++;
      return this.num;
    },
  },
};
</script>

<template>
  <div id="apple">
    <NuxtLink to="/about">About</NuxtLink>
    <p class="theNum">
      {{ theData }}
    </p>
    <NuxtLogo />
    <test :theType="sendtype" />
  </div>
</template>


<style scoped lang="scss">
@import "~assets/style/main.scss";
.theNum {
  color: $orange;
}
</style>