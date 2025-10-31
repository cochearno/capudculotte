<template>
	<header>
		<div class="heading-page">
			<div class="heading-page-presentation">
				<div class="logo">
					<img
						src="../../../assets/img/capudculotte copie.png"
						alt="logo-capudculotte"
						class="capudculotte"
					/>
				</div>
				<div class="title">CAPUD'CULOTTE</div>
				<div class="page-heading-menu">
					<elements-menu-cta
						v-for="button in buttonList"
						v-bind="button"
						@cta-redirect="handleClick"
					/>
				</div>
			</div>
		</div>
	</header>
</template>

<script>
export default {
	data() {
		const buttonList = [
			{ text: "Accueil", interact: "redirect", redirectUrl: "/" },
			{ text: "Collections", interact: "redirect", redirectUrl: "/" },
			{ text: "Tissus", interact: "redirect", redirectUrl: "/" },
			{ text: "Contacts", interact: "redirect", redirecturl: "/" },
		];
		return {
			buttonList,
		};
	},
	methods: {
		handleClick(item) {
			if (item.interact === "redirect") {
				navigateTo(item.redirectUrl);
			}
		},
	},
};
</script>

<style lang="scss" src="./header.scss" />

