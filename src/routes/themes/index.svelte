<script lang="ts">
	import { Button, TextBox } from "$lib";
	import { Writable, writable } from "svelte/store";

	interface ThemeData {
		colors: {
			region: { light: string, dark: string },
			base: { light: string, dark: string },
			primary: { light: string, dark: string },
		},
		shapes: {
			cornerRadius: {
				controls: {
					top: number,
					bottom: number,
					left: number,
					right: number,
				},
				overlay: {
					top: number,
					bottom: number,
					left: number,
					right: number,
				},
			},
			borderThickness: {
				top: number,
				bottom: number,
				left: number,
				right: number,
			},
		}
	}

	let data: Writable<ThemeData> = writable({
		colors: {
			region: {
				light: "#ffffff",
				dark: "#000000"
			},
			base: {
				light: "#cccccc",
				dark: "#333333"
			},
			primary: {
				light: "#0073cf",
				dark: "#0073cf"
			}
		},
		shapes: {
			cornerRadius: {
				controls: {
					top: 2,
					bottom: 2,
					left: 2,
					right: 2
				},
				overlay: {
					top: 4,
					bottom: 4,
					left: 4,
					right: 4
				}
			},
			borderThickness: {
				top: 1,
				bottom: 1,
				left: 1,
				right: 1
			}
		}
	});

	let themeName = "";
</script>

<svelte:head>
	<title>Files - Themes</title>
	<meta content="Files - Themes" property="og:title" />

	<meta content="/branding/banner-themes-light.png" property="og:image" />
</svelte:head>

<aside>
	<form id="theme-creator">
		<h1>Theme Creator</h1>
		<div role="separator"></div>

		<div class="colors-tab">
			<h2>Region</h2>
			<div class="region-color">

				<label for="light-region">Light Theme</label>
				<label for="dark-region">Dark Theme</label>

				<input id="light-region" type="color" class="light-theme-color" bind:value={$data.colors.region.light}>
				<input id="dark-region" type="color" class="dark-theme-color" bind:value={$data.colors.region.dark}>
			</div>

			<h2>Base</h2>
			<div class="base-color">

				<label for="light-base">Light Theme</label>
				<label for="dark-base">Dark Theme</label>

				<input id="light-base" type="color" class="light-theme-color" bind:value={$data.colors.base.light}>
				<input id="dark-base" type="color" class="dark-theme-color" bind:value={$data.colors.base.dark}>
			</div>

			<h2>Primary</h2>
			<div class="primary-color">

				<label for="light-primary">Light Theme</label>
				<label for="dark-primary">Dark Theme</label>

				<input id="light-primary" type="color" class="light-theme-color" bind:value={$data.colors.primary.light}>
				<input id="dark-primary" type="color" class="dark-theme-color" bind:value={$data.colors.primary.dark}>
			</div>
		</div>

		<div class="theme-name">
			<label for="theme-name">Theme Name</label>
			<TextBox bind:value={themeName} clearButton={false} id="theme-name" />
		</div>

		<div role="separator"></div>

		<Button variant="accent" class="export-theme" type="submit"
		        href="data:text/json,{JSON.stringify($data)}"
		        download="{ themeName }.json">
			Export Theme
		</Button>
	</form>
</aside>

<style lang="scss">
	@use "src/styles/pages/themes";
</style>