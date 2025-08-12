<svelte:head>
	<title>About - EBT Labs Dashboard</title>
	<meta name="description" content="About EBT Labs and the dashboard project" />
</svelte:head>

<div class="about-page">
	<header class="page-header">
		<h1>About EBT Labs</h1>
		<p>Building and managing web applications</p>
	</header>

	<div class="content-grid">
		<section class="about-section">
			<h2>What is EBT Labs?</h2>
			<p>
				EBT Labs is a collection of web applications and services designed to make your digital life easier. 
				This dashboard serves as a central hub for managing and monitoring all your deployed sites.
			</p>
		</section>

		<section class="about-section">
			<h2>Current Projects</h2>
			<div class="project-list">
				<div class="project-item">
					<span class="project-icon">🎵</span>
					<div class="project-info">
						<h3>MusicBuddy</h3>
						<p>Your music companion app at <a href="https://musicbuddy.ebtlabs.site" target="_blank" rel="noopener noreferrer">musicbuddy.ebtlabs.site</a></p>
					</div>
				</div>
				<!-- More projects will be added here as you build them -->
			</div>
		</section>

		<section class="about-section">
			<h2>Technology Stack</h2>
			<p>
				This dashboard is built with modern web technologies including SvelteKit, TypeScript, and Tailwind CSS. 
				It's designed to be fast, responsive, and easy to maintain.
			</p>
			<div class="tech-stack">
				<span class="tech-tag">SvelteKit</span>
				<span class="tech-tag">TypeScript</span>
				<span class="tech-tag">Tailwind CSS</span>
				<span class="tech-tag">Vite</span>
			</div>
		</section>

		<section class="about-section">
			<h2>Get in Touch</h2>
			<p>
				Have questions or suggestions? Feel free to reach out through our 
				<a href="https://github.com/ebtrinh/ebtlabs" target="_blank" rel="noopener noreferrer">GitHub repository</a>.
			</p>
		</section>
	</div>
</div>

<style>
	.about-page {
		max-width: 900px;
		margin: 0 auto;
		padding: 2rem 1rem;
	}

	.page-header {
		text-align: center;
		margin-bottom: 3rem;
	}

	.page-header h1 {
		font-size: 2.5rem;
		font-weight: 700;
		color: var(--color-text);
		margin: 0 0 0.5rem 0;
	}

	.page-header p {
		font-size: 1.1rem;
		color: var(--color-text-muted);
		margin: 0;
	}

	.content-grid {
		display: grid;
		gap: 2.5rem;
	}

	.about-section h2 {
		font-size: 1.5rem;
		font-weight: 600;
		color: var(--color-text);
		margin: 0 0 1rem 0;
	}

	.about-section p {
		color: var(--color-text-muted);
		line-height: 1.6;
		margin: 0 0 1rem 0;
	}

	.about-section a {
		color: var(--color-theme-1);
		text-decoration: none;
	}

	.about-section a:hover {
		text-decoration: underline;
	}

	.project-list {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.project-item {
		display: flex;
		align-items: center;
		gap: 1rem;
		padding: 1rem;
		background: var(--color-surface-1);
		border: 1px solid var(--color-surface-2);
		border-radius: 8px;
	}

	.project-icon {
		font-size: 2rem;
	}

	.project-info h3 {
		font-size: 1.1rem;
		font-weight: 600;
		color: var(--color-text);
		margin: 0 0 0.25rem 0;
	}

	.project-info p {
		margin: 0;
		font-size: 0.875rem;
	}

	.tech-stack {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
		margin-top: 1rem;
	}

	.tech-tag {
		background: var(--color-surface-2);
		color: var(--color-text);
		padding: 0.25rem 0.75rem;
		border-radius: 20px;
		font-size: 0.75rem;
		font-weight: 500;
	}

	@media (max-width: 768px) {
		.about-page {
			padding: 1rem 0.5rem;
		}

		.page-header h1 {
			font-size: 2rem;
		}

		.project-item {
			flex-direction: column;
			text-align: center;
		}
	}
</style>
