<script>
	import CollapsibleSection from '../components/CollapsibleSection.svelte'
	let name = 'world';
	let articles = [
    {
        "title":"This is the first article",
        "author": "I made this website",
        "content": "Hey, this is the first article in this website, if you find this, cheers. If it took you a long time, it means that this website has grown and I'm really happy"

    },
    {
        "title":"This is the first article",
        "author": "I made this website",
        "content": "Hey, this is the second article in this website, please ignore"  
    }
];
	let article;
</script>

<section id = "body">
	<ul>
		{#each articles as article}
			<CollapsibleSection headerText={article.title} >
				<h2 class = "subtitle"> {article.author} </h2>
				<div class="content">
						{article.content}
				</div>
			</CollapsibleSection>
		{/each}
	</ul>
</section>

<style>
	section {
		width: 300px;
	}
	
	.content {
		background-color: #f4f4f4;
		padding: 0.5em;
	}
    .subtitle {
        background-color: grey;
    }
</style>