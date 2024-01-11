<main>
	<!-- svelte-ignore a11y-missing-attribute -->
	<a href="/" class="currentTournament">
		<h2>Current Tournament</h2>
		<p class="subtitle-small">Check the current tournaments</p>
	</a>

	<!-- svelte-ignore a11y-missing-attribute -->
	<a href="/" class="creatTournament">
		<h2>Create Tournament</h2>
		<p class="subtitle-small">Create your tournament</p>
	</a>

	<!-- svelte-ignore a11y-missing-attribute -->
	<a href="/players/new" class="createPlayer">
		<h3>Create Player</h3>
		<p class="subtitle-small">Create your players</p>
	</a>

	<!-- svelte-ignore a11y-missing-attribute -->
	<a href="/" class="creatTeam">
		<h3>Create Team</h3>
		<p class="subtitle-small">Create your team</p>
	</a>

	<!-- svelte-ignore a11y-missing-attribute -->
	<a href="/" class="completedTournaments">
		<h2>Completed Tournaments</h2>
		<p class="subtitle-small">View the completed tournaments</p>
	</a>

	<img class="frisbee" src="../images/frisbee.png" alt="frisbee" />
</main>

<style>
	main {
		display: grid;
		grid-template-rows: 1fr;
		/* grid-template-columns: 1fr 1fr 1fr 1fr; */
		grid-template-areas:
			'currentTournament'
			'completedTournaments'
			'creatTournament'
			'creatTeam'
			'createPlayer'
			'frisbee';
		gap: 1rem;
		padding: 2rem;
		width: 100%;
		height: 100%;
		overflow-x: scroll;
		background: var(back);
	}

	a {
		box-shadow: var(--box-shadow);
		border-radius: 15px;
		background-color: white;
		padding: 1rem 1.5rem;
		text-decoration: none;
	}

	.createPlayer {
		grid-area: createPlayer;
		background-color: hsl(160, 100%, 95%);
	}

	.creatTeam {
		grid-area: creatTeam;
		background-color: hsl(160, 100%, 95%);
	}

	.creatTournament {
		grid-area: creatTournament;
		background-color: hsl(160, 100%, 95%);
	}

	.completedTournaments {
		grid-area: completedTournaments;
		background-color: hsl(0, 0%, 100%);
	}

	.currentTournament {
		grid-area: currentTournament;
		background-color: hsl(231, 100%, 92%);
	}

	.currentTournament:is(:hover, :focus) {
		background-color: hsl(231, 100%, 87%);
	}

	.completedTournaments:is(:hover, :focus) {
		background-color: hsl(0, 0%, 95%);
	}

	.creatTournament:is(:hover, :focus),
	.creatTeam:is(:hover, :focus),
	.createPlayer:is(:hover, :focus) {
		background-color: hsl(160, 100%, 90%);
	}

	.frisbee {
		grid-area: frisbee;
		box-shadow: var(--box-shadow);
		border-radius: 25px;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	@media only screen and (min-width: 750px) {
		main {
			display: grid;
			grid-template-rows: 1fr 1fr 1fr;
			grid-template-columns: 1fr 1fr 1fr 1fr;
			grid-template-areas:
				' currentTournament currentTournament currentTournament currentTournament'
				'completedTournaments completedTournaments creatTournament creatTournament'
				'creatTeam creatTeam createPlayer createPlayer'
				' frisbee frisbee frisbee frisbee';
			gap: 2rem;
			padding: 2rem;
		}

		a {
			border-radius: 25px;
			padding: 1frisbee5rem 2.5rem;
		}
	}

	@media only screen and (min-width: 1100px) {
		main {
			display: grid;
			grid-template-rows: 1fr 1fr 1fr;
			grid-template-columns: 1fr 1fr 1fr 1fr;
			grid-template-areas:
				'creatTournament creatTournament completedTournaments completedTournaments'
				'creatTeam createPlayer completedTournaments completedTournaments'
				'currentTournament currentTournament currentTournament frisbee';
			gap: 2rem;
			padding: 2rem;
		}

		a {
			border-radius: 25px;
			padding: 1.5rem 2.5rem;
		}
	}
</style>
