<script lang="ts">
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../app.postcss';
	import { AppShell, AppBar, AppRail, AppRailTile, Modal } from '@skeletonlabs/skeleton';
	import Navigation from '$lib/Navigation/Navigation.svelte';
	import {ManualGearbox, ApiApp, Settings, Settings2, Apple} from '@steeze-ui/tabler-icons';
	import {Icon} from '@steeze-ui/svelte-icon';

	
</script>

<!-- App Shell -->
<AppShell >
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl">Shield Explorer</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a class="btn btn-sm variant-ghost-surface" href="https://discord.gg/EXqV7W8MtY" target="_blank" rel="noreferrer">Discord</a>
				<a class="btn btn-sm variant-ghost-surface" href="https://twitter.com/SkeletonUI" target="_blank" rel="noreferrer">Twitter</a>
				<a class="btn btn-sm variant-ghost-surface" href="https://github.com/skeletonlabs/skeleton" target="_blank" rel="noreferrer">GitHub</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		<div class="flex h-full">
			<div style="background-color: #222F44">
				<AppRail >
					<svelte:fragment slot="lead">
						<AppRailTile tag="a" href="https://github.com/" target="_blank" title="Settings">
							<Icon src={ApiApp} size="36px" color=#ccc/>
						</AppRailTile>
						<AppRailTile tag="b" href="/about"  title="About">
							<Icon src={ManualGearbox} size="36px" color=#ccc/>
						</AppRailTile>							
						<AppRailTile tag="a" href="https://github.com/" target="_blank" title="Settings">
							<Icon src={Settings2} size="36px" color=#ccc/>
						</AppRailTile>
						<AppRailTile tag="a" href="https://github.com/" target="_blank" title="Settings">
							<Icon src={Apple} size="36px" color=#ccc/>
						</AppRailTile>													
					</svelte:fragment>
					<svelte:fragment slot="trail">
						<AppRailTile tag="a" href="https://github.com/" target="_blank" title="Settings">
							<Icon src={Settings} size="36px" color=#ccc/>
						</AppRailTile>
					</svelte:fragment>
				</AppRail>
			</div> 
			<div style="background-color: #1B2636">
				<Navigation />
			</div>
		</div>
	</svelte:fragment>
	<svelte:fragment slot="pageHeader" >
		<div class="flex justify-end" style="background-color: #1222F44">
			<button>
				<a href="/about">
					<Icon src={ApiApp} size="22px" color=#ccc />
				</a>
			</button>
			<button>
				<Icon src={ManualGearbox} class="hover:bg-primary-hover-token" size="22px" color=#ccc />
			</button>
			<button class="btn-icon">B</button>
			<a href="/" class="btn-icon unstyled hover:bg-primary-hover-token" >A</a>
		</div>
	</svelte:fragment>

	<!-- Page Route Content -->
	<slot />
</AppShell>

<Modal />
