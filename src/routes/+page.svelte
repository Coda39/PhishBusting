<script> import * as config from '$lib/config'
	import {formatDate} from '$lib/utils'
	import Animate from '$lib/animate.svelte'
	import {fly} from 'svelte/transition'
	import {backOut} from 'svelte/easing'

	const lines = [
		'Who you gonna call?',
		'Phish Busters',
		'👻',
	]

	export let data
</script>



<svelte:head>
	<title>{config.title}</title>
</svelte:head>

	
<section>
  <picture class="promo-art">
	<Animate>
		<div class="title-text">
				{#each lines as line, i}
					<div class="overflow">
						<span 
							class="line"
							in:fly={{
							  y:100,
							  delay:300 * i,
							  easing:backOut
							}}
						>
							{line}
						</span>
					</div>
				{/each}
		</div>
	</Animate>


	<img  src="/stressed-person-using-computer-at-desk.png" alt="a random doodle" style="max-width: 50%">
  </picture>
</section>

<section>
	<div class="row">
		<div class="three-column">
			<h2 class=p-header>Project Description</h2>
			<p class=p-description >PhishBusters is an easy to understand blog website aimed to inform users about different types of scams. It was built using CSS, HTML, and JavaScript through the Svelte framework. This website is aimed at users that are looking for information about how to detect scams, people who suspect they’re being scammed, and internet users unfamiliar with how to safely navigate the web. We have information on two types of phishing attacks called .zip domains and web skimming.</p>
		</div>
		<div class="three-column">
			<h2 class=p-header>About the Team</h2>
			<p class=p-description style="padding:10px;">We are the Phishbusters, your trusted cybersecurity force. We’re here to keep you safe on the web by spreading awareness about phishing attempts and other cybersecurity attacks. We are a team of four externs developing a project for the ALRISE 2023 Summer Externship Program. We have two researchers, Giovani Castillo and Paris Saucedo, and two web developers, Mateo Estrada and Casandra Marquez.</p>
		</div>
		<div class="three-column">
			<h2 class=p-header>Why it Matters</h2>
			<p class=p-description >All it takes is better judgment and vigilance when browsing the internet to stay safe. Our goal is to spread information to avoid scammers from having an upper hand and taking advantage of people who aren’t very knowledgeable about scams. Scams hurt people daily which is why it’s so important to prevent users from being scammed by spreading information in an easy to understand way. The best way to avoid scams is to know about different types of scams and how they work.</p>
		</div>
	</div>
</section>

<section>
	<h1 class ="post-header"> Posts </h1> 
	<ul class="posts">
		{#each data.posts as post}
			<li class="post">
				<a href={post.slug} class = "title">{post.title}</a>
				<p class = "date">{formatDate(post.date)}</p>
				<p class = "date">{post.author}</p>
				<p class = "description">{post.description}</p>
			</li>
		{/each}
	</ul>
</section>


<style>
		.overflow {
			display: inline-block;
			overflow: hidden;
			vertical-align: bottom;
		}
		.line {
			display: inline-block;
			margin: 0.2rem;
			text-shadow: 2px 0 10px hsl(0 0% 0% / 20%);
			color:var(--text-1)
		}
	.title-text{
		display: flex;
		flex-direction:column;
		justify-content:center;
		max-width: 800px;
		font-size: 4rem;
		font-weight: 900;
		text-align: center;
	}
	.post-header{
		border-bottom:1px solid var(--border);
		padding-bottom:var(--size-7);
		padding-top:var(--size-7);
	}
	.posts{
		display:grid;
		gap:var(--size-7); 
	}
	.post{
		max-inline-size: var(--size-content-3);
	}
	.post:not(:last-child){
		border-bottom:1px solid var(--border);
		padding-bottom:var(--size-7);
	}
	.title{
		font-size: var(--font-size-fluid-3);
		text-transform:capitalize;
	}
	.date{
		color:var(--text-2);
	}
	.description{
		margin-top: var(--size-3);
	}
	.row{
		display:flex; 
		flex-flow:row;
		justify-content: space-between;
		align-items:center;
	}
	.three-column{
		flex-basis: calc(33.33% - 20px);
		padding: 10px;
		margin: 10px;
		background-color:var(--surface-4);
		border-radius: 8px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	}
	.p-header {
		margin-bottom:var(--size-2);
	}
	.p-description{
		color:var(--text-2)
	}
	.promo-art{
		display:flex;
		justify-content:center;
	}
</style>
