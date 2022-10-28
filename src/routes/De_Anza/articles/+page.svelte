<script>
	import { Button } from 'attractions';
	import CollapsibleSection from '../../../components/CollapsibleSection.svelte'
	import * as data from './file.json';
	const {articles} = data;
	let article;
	import Modal from '../../../components/Modal.svelte';
</script>

<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto+Mono"
/>


<section id = "body">
	<ul>
		{#each articles as article}
			<CollapsibleSection headerText={article.title} >
				<div class = "article">
					<h2 class = "subtitle"> {article.author} </h2>
					<h2 class = "subtitle"> date </h2>
					<div class="content">
							{article.content}
					</div>
					<Modal title={article.title} link = {article.link}/>
				</div>
			</CollapsibleSection>
		{/each}
	</ul>
</section>

<style>
	section {
		width: 300;
	}
	
	.content {
		background-color: #ffffff;
		padding: 0.5em;
	}
    .subtitle {
        background-color: #ffffff;
		font: Roboto;
		font-size: 0.75em;
    }
	h3 {
		position: absolute;
		right: 20px;
	}

</style>