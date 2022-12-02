<template>
  <div class="captcha"></div>
</template>

<script>
export default {
  name: "GeeTest",
  props: {
    captchaConfig: {
      type: Object,
      required: true,
    },
  },
  watch: {
    captchaConfig() {
      window.initGeetest4(
        this.captchaConfig.config,
        this.captchaConfig.handler
      );
    },
  },
  created() {
    window.initGeetest4(this.captchaConfig.config, this.captchaConfig.handler);
  },
};
</script>
