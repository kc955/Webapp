<script>
    import { Button, Card, Divider, Accordion, AccordionSection } from "attractions";
	import * as data from './school.json';
	const {schools} = data;
</script>

<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
/>
<!-- Roboto -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700"
/>
<!-- Roboto Mono -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto+Mono"
/>

<header >
	<h1>Psychology Clubs</h1>
</header>
<Divider/>
<nav>
	<div class = "used">
		{#each schools as school}
				<Accordion let:closeOtherPanels>
					<div class="accor">
						<AccordionSection on:panel-open={closeOtherPanels}>
							<div slot="handle" let:toggle>
							<Button on:click={toggle}>
								{school.name}              +
							</Button>
							</div>
							<Divider/>
							<a href="./{school.name}">
								<Button>
									<h2>Event calendar</h2>
								</Button>
							</a>
							<a href="./{school.name}/articles">
								<Button>
									<h2>Meeting notes</h2>
								</Button>
							</a>
							<a href="https://mail.google.com/mail/?view=cm&fs=1&to={school.email}&su=question&body=BODY">
								<Button>
									<h2>Ask questions</h2>
								</Button>
						</AccordionSection>
					</div>
				</Accordion>
		{/each}
	</div>

</nav>
<footer>
	<Card outline>
		<a href="./resource">
			<h2>click here to see fliers</h2>
		</a>		
	</Card>
</footer>




<style>
	body {
		font-family: 'Roboto';font-size: 22px;
		margin: 0px;
		padding: 0px;
	}
	footer {
		position: absolute;
		right: 45%;
		bottom: 30px;
	}
	nav{
		background-color: rgb(209, 209, 209);
		font-size: 1em;
		min-height: 700px;
	}
	header {
		text-align: center;
		padding: 0;
		width: 100%;
		margin: 0 auto;
		border-bottom: 2px black;
	}

	h1 {
		color: #ff0000;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
		font-family: 'Roboto'
	}
	h2 {
		color: #9c03ee;
		text-transform: uppercase;
		font-size: 1em;
		font-weight: 20;
		text-decoration: none;
	}
	h3 {
		color: #ffffff;
		text-transform: uppercase;
		font-weight: 20;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	.accor {
		background-color: #ffffff;
		width: 400px;
		border: black 3px;
		border-radius: 20px 12px 20px 12px;
		padding: 2;
	}
	.used{
		position: absolute;
		width: 400px;
		left: 10px;
	}

</style>
