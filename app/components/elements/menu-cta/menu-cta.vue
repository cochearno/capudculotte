<template>
	<div class="menu-cta" @click="handleRedirect">{{ text }}</div>
</template>

<script lang="js">
export default {
  name: "menu-cta",
  props: {
    text: {
      type: String,
      required: false,
      default: undefined,
    },
		interact: {
			type: String,
			default: "redirect"
		},
		redirectUrl: {
			type: String,
			default: undefined
		}
  },
	emits: ["cta-redirect"],
	methods: {
		handleRedirect() {
			const redirectData = {
				interact: this.interact,
				redirectUrl : this.redirectUrl
			}
			this.$emit("cta-redirect", redirectData)
		}
	}
};
</script>

<style lang="scss" src="../menu-cta/menu-cta.scss" />

