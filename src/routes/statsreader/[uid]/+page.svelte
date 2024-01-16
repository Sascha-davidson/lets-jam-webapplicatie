<script>
	import PlayersList from '$lib/organisms/PlayersList.svelte';

	export let data;

	const { match, statistics } = data;
</script>

<main class="page">
	<header class="page__header">
		<h1>Commentator Dashboard</h1>
	</header>

	<div class="page__content fluid-type">
		<section class="team">
			<header class="team__header">
				<h2>
					<img alt="" height="32" width="32" />
					<span>{match.team_a.name}</span>
				</h2>

				<p>{match.team_a.country.name} | City</p>
			</header>

			<div class="team__content">
				<!-- <pre>{JSON.stringify(match.team_a, null, 2)}</pre> -->
				<PlayersList players={match.team_a.players} match={match.id} team={match.team_a.id} />
			</div>
		</section>

		<section class="statistics">
			<header class="statistics__header">
				<h2>Statistics</h2>
			</header>

			<div class="statistics__content">
				<section class="status">
					<h3>Match status</h3>

					<p>LIVE</p>
					<p>Mixed | 2 | Arena | Finale</p>
				</section>

				<section class="scoreboard">
					<h3>Scoreboard</h3>

					<article>
						<img alt="" height="64" width="64" />
						<h4>{match.team_a.name}</h4>
					</article>
					<p>0 - 0</p>
					<article>
						<img alt="" height="64" width="64" />
						<h4>{match.team_b.name}</h4>
					</article>
				</section>

				<section class="timeline">
					<h3>Timeline</h3>

					<ul class="timeline-list">
						{#each statistics as stat}
							<li class="timeline-list__item--{stat.team}">
								<p class="jersey-number">{stat.jersey_number}</p>
								<p>{stat.name}</p>
								<p>{stat.time}</p>

								<p>8 - 3</p>
							</li>
						{/each}
					</ul>
				</section>
			</div>
		</section>

		<section class="team">
			<header class="team__header">
				<h2>
					<img alt="" height="32" width="32" />
					<span>{match.team_b.name}</span>
				</h2>

				<p>{match.team_b.country.name} | City</p>
			</header>

			<div class="team__content">
				<!-- <pre>{JSON.stringify(match.team_b, null, 2)}</pre> -->
				<PlayersList
					players={match.team_b.players}
					match={match.id}
					team={match.team_b.id}
					reversed={true}
				/>
			</div>
		</section>
	</div>
</main>

<style>
	.page {
		height: 100vh;
		/* font-size: 0.75rem; */
	}

	/* Inclusively Hidden */
	.page__header,
	.statistics__header,
	.status h3,
	.timeline h3,
	.scoreboard h3 {
		clip: rect(0 0 0 0);
		position: absolute;
		clip-path: inset(50%);
		width: 1px;
		height: 1px;
		overflow: hidden;
		white-space: nowrap;
	}

	.page__content {
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));
		flex: 1;
		gap: 1em;
		padding: 1rem;
		height: 100%;
	}

	.team {
		display: flex;
		flex-flow: column nowrap;
		gap: 0.5em;
	}

	.team__header {
		margin-bottom: 0px;
	}

	.scoreboard,
	.timeline,
	.team__header {
		border: 1px solid white;
		border-radius: 0.5rem;
		background: white;
		padding: 1em;
	}

	.team__header h2,
	.team__header p,
	.statistics__header h2 {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		font-size: 1.125rem;
	}

	.team:last-child .team__header h2,
	.team:last-child .team__header p {
		flex-flow: row-reverse;
	}

	.team__content {
		flex: 1;
	}

	.jersey-number,
	[class^='statistic-'] {
		--size: 2.167em;

		display: inline-block;
		vertical-align: middle;
		border: 1px solid black;
		border-radius: calc(1em - 0.5em);
		padding: 0.5em;
		width: var(--size);
		height: var(--size);
		line-height: 1;
		text-align: center;
	}

	[class^='statistic-'] {
		--color: white;
		border-color: var(--color);
		background: var(--color);

		color: white;
	}

	.statistic-goals {
		--color: #18d02b;
	}

	.statistic-assists {
		--color: #2974e4;
	}

	.statistic-blocks {
		--color: #ed4444;
	}

	.statistic-turnovers {
		--color: #ffc738;
	}

	[class^='statistic-']:empty {
		--color: #f4f5fa;
	}

	.statistics {
		display: flex;
		flex-flow: column nowrap;
	}

	.statistics__content {
		display: flex;
		flex: 1;
		flex-flow: column nowrap;
		gap: 1em;
	}

	.status {
		display: flex;
		justify-content: space-between;
		gap: 1em;
	}

	.status p:nth-of-type(1) {
		position: relative;
		border: 1px solid #ef1111;
		border-radius: 0.5rem;
		background: #ef1111;
		padding: 1em;
		padding-left: 3em;
		color: white;
	}
	.status p:nth-of-type(1)::after {
		--size: 0.5em;
		position: absolute;
		top: 1em;
		left: 1em;
		border-radius: 50%;
		background: white;
		width: var(--size);
		height: var(--size);

		content: '';
	}

	.status p:nth-of-type(2) {
		flex: 1;
		border: 1px solid white;
		border-radius: 0.5em;
		background: white;
		padding: 1em;
		text-align: center;
	}

	.scoreboard {
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));
	}

	.scoreboard * {
		text-align: center;
	}

	.scoreboard p {
		margin-block: auto;
	}

	.timeline {
		flex: 1;
	}

	.timeline-list {
		display: grid;
		grid-template-columns: auto minmax(0, 1fr) minmax(0, 1fr) auto minmax(0, 1fr) minmax(0, 1fr) auto;
		grid-template-areas: 'a b c d e f g';
		grid-auto-rows: min-content;
		gap: 0.5em;
		list-style: none;
	}

	[class^='timeline-list__item'] {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: 1 / -1;
	}

	[class^='timeline-list__item'] p {
		margin-block: auto;
	}

	[class^='timeline-list__item'] p:nth-of-type(1) {
		grid-area: a;
	}
	[class^='timeline-list__item'] p:nth-of-type(2) {
		grid-area: b;
	}
	[class^='timeline-list__item'] p:nth-of-type(3) {
		grid-area: c;
	}
	[class^='timeline-list__item'] p:nth-of-type(4) {
		grid-area: d;
		text-align: center;
	}

	.timeline-list__item--b * {
		text-align: right;
	}

	.timeline-list__item--b p:first-child {
		text-align: center;
	}

	.timeline-list__item--b p:nth-of-type(1) {
		grid-area: g;
	}
	.timeline-list__item--b p:nth-of-type(2) {
		grid-area: f;
	}
	.timeline-list__item--b p:nth-of-type(3) {
		grid-area: e;
	}



/* определения */
:root {
  --fz-min: 12;
  --fz-max: 16;
}

* {
  --fz-min-px: calc(var(--fz-min) * 1px); /* font-size-minimum */
  --fz-max-px: calc(var(--fz-max) * 1px); /* font-size-maximum */
  --fz-diff: calc(var(--fz-max) - var(--fz-min)); /* font-size-difference */
  font-size: clamp(
    var(--fz-min-px),
    calc(var(--fz-min-px) + var(--fz-diff) * ((100vw - 320px) / (1280 - 320))),
    var(--fz-max-px)
  );
}
/* .container {
  max-width: 1280px;
  padding: 0 15px;
  margin: 0 auto;
} */
/* а теперь юзаем  */

h1 {
  --fz-min: 28;
  --fz-max: 40;
  line-height: 1.2;
}

main {
  --fz-min: 6;
  --fz-max: 14;
  line-height: 1.614;
}


</style>
