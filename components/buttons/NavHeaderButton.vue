<template>
	<li>
		<NuxtLink 
			:to="to"
			:class="AtualNavPageAcessado"
			class="nav-header-button" 
		>
			{{ texto }}
		</NuxtLink>
	</li>
</template>

<script>
export default {
	props: {
		texto: {
			type: String,
			default: ''
		},
		to: {
			type: String,
			default: '/'
		},
	},
	computed: {
		AtualNavPageAcessado() {
			return this.$route.path === this.to ?
				'nav-page-clicked'
				:
				''
		}
	}
}
</script>

<style scoped>
.nav-header-button {
    height: 40px;
    width: auto;
    padding: 0px .8rem;
    font-size: min(max(1rem, 1.7vw), 1.6rem);
    font-weight: 600;
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
	white-space: nowrap;
    border: none;
    background-color: transparent;
    color: black;
}
	.nav-header-button:hover {
		text-decoration: none;
	}

.nav-page-clicked {
    border-bottom: 3px solid #1E08AA;
}

</style>