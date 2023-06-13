<script>
    import { page } from '$app/stores';
    import { writable } from 'svelte/store';
    import Toggle from './toggle.svelte';

  let currentPage = writable(''); 

  $: {
    // Get the current page URL pathname from the $page store
    const currentPath = $page.url.pathname;

    // Update the currentPage variable based on the current path
    if (currentPath === '/') {
      currentPage.set('Welcome');
    } else if (currentPath === '/zip-domains') {
      currentPage.set('Zip Domains');
    } else if (currentPath ===('/web-skimmers')) {
      currentPage.set('Web Skimmers');
    } else {
      currentPage.set('Unknown Page');
    }
  }
</script>

<header>
	<div class="header-content">
		<div class="header-left">
			<a href="/" class="page-title"> {$currentPage} </a>
		</div>
		<nav class="header-right">
			<ul>
				<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/">Home</a>
				</li>
				<li aria-current={$page.url.pathname === '/zip-domains' ? 'page' : undefined}>
					<a href="/zip-domains">Zip Domains</a>
				</li>
				<li aria-current={$page.url.pathname.startsWith('/web-skimmers') ? 'page' : undefined}>
					<a href="/web-skimmers">Web Skimmers</a>
				</li>
				<Toggle />
			</ul>
		</nav>
	</div>
</header>

<style>
header {
	padding: 10px;
}

.header-content {
	display: flex;
	flex-direction:flex-start;
	justify-content: space-between;
	align-items: left;
}

.page-title {
	text-decoration-line: none;
	text-decoration-color: var(--text-1) !important;
	text-decoration-style:none;
	margin: 0;
	font-size: 3rem;
	font-weight: bold;
	position:relative;
	justify-self:left;
	margin-right:auto;
}

.header-left {
	display: flex;
	flex-direction: column;
}

.header-right {
	display: flex;
}

nav ul {
	list-style: none;
	padding: 0;
	margin: 0;
	display: flex;
	justify-content: center;
	align-items: center;
}

nav li {
	margin: 0 10px;
}

nav li[aria-current='page'] a {
	background-color: var(--brand);
	color: var(--surface-4);
}

nav a {
	display: inline-block;
	padding: 10px 20px;
	border: 1px solid #333;
	border-radius: 10px;
	text-decoration: none;
	color: var(--text-1);
	font-weight: 700;
	font-size: 0.8rem;
	text-transform: uppercase;
	letter-spacing: 0.1em;
	transition: color 0.2s linear;
}

a:visited {
	text-decoration-line: none;
	text-decoration-color: var(--text-1) !important;
	text-decoration-style:none;
}

a:hover {
	background-color: var(--surface-3);
}
</style>
