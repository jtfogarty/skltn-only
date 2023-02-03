<script>
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../app.postcss';
	import { AppShell, AppBar, AppRail, AppRailTile } from '@skeletonlabs/skeleton';
	import Navigation from '$lib/Navigation/Navigation.svelte';
	import {IconSettings} from '@tabler/icons-svelte';
</script>

<!-- App Shell -->
<AppShell >
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Shield Explorer</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a class="btn btn-sm variant-ghost-surface" href="https://discord.gg/EXqV7W8MtY" target="_blank" rel="noreferrer">Discord</a>
				<a class="btn btn-sm variant-ghost-surface" href="https://twitter.com/SkeletonUI" target="_blank" rel="noreferrer">Twitter</a>
				<a class="btn btn-sm variant-ghost-surface" href="https://github.com/skeletonlabs/skeleton" target="_blank" rel="noreferrer">GitHub</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		<div class="flex">
			<div>
				<AppRail >
					<svelte:fragment slot="lead"></svelte:fragment>
					<svelte:fragment slot="trail">
						<AppRailTile tag="a" href="https://github.com/" target="_blank" title="Settings">
							<IconSettings size={36} color=#ccc/>
						</AppRailTile>
					</svelte:fragment>
				</AppRail>
			</div>
			<div>
				<Navigation />
			</div>
		</div>
	</svelte:fragment>
	<svelte:fragment slot="pageHeader">
		<button>
			<a href="/about">
				<IconSettings size={22} color=#ccc />
			</a>
		</button>
		<button>
			<IconSettings class="hover:bg-primary-hover-token" size={22} color=#ccc />
		</button>
		<button class="btn-icon">B</button>
		<a href="/" class="btn-icon unstyled hover:bg-primary-hover-token" >A</a>
	</svelte:fragment>

	<!-- Page Route Content -->
	<slot />
</AppShell>
