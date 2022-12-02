<template>
  <div id="app">
    <form id="form">
      <div
        class="inp"
        :class="captchaConfig.config.product === 'bind' ? 'minWidth' : ''"
      >
        <div class="user">user</div>
        <input
          type="email"
          id="email"
          autocomplete="false"
          placeholder="hello@geetest.com"
        />
      </div>
      <div class="inp">
        <div class="pass"></div>
        <input
          type="password"
          id="pass"
          autocomplete="false"
          placeholder="******"
        />
      </div>
      <div
        id="captcha"
        :class="captchaConfig.config.product === 'bind' ? 'hideHeight' : ''"
      >
        <GeeTest :captcha-config="captchaConfig" />
      </div>
      <div class="login" @click="login">
        {{ captchaConfig.config.language === "en" ? "login" : "登录" }}
      </div>
    </form>
  </div>
</template>

<script>
import GeeTest from "./components/GeeTest.vue";

export default {
  name: "App",
  components: { GeeTest },
  data() {
    return {
      captchaConfig: {
        config: {
          captchaId: "097333cc0dff02bff190d16cb1a99aaf",
          language: "en",
          product: "bind",
        },
        handler: this.captchaHandler(),
      },
    };
  },
  methods: {
    captchaHandler() {},
    login() {},
  },
};
</script>
