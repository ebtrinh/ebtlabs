<script lang="ts">
	// Dashboard data for your sites
	const sites = [
		{
			name: 'MusicBuddy',
			url: 'https://musicbuddy.ebtlabs.site',
			description: 'Your music companion app',
			status: 'online', // You can update this dynamically later
			icon: '🎵'
		}
		// Add more sites here as you create them
	];
</script>

<svelte:head>
	<title>EBT Labs Dashboard</title>
	<meta name="description" content="Dashboard for EBT Labs sites and projects" />
</svelte:head>

<div class="dashboard">
	<header class="dashboard-header">
		<h1>EBT Labs Dashboard</h1>
		<p class="subtitle">A collection of web applications and services</p>
	</header>

	<section class="sites-grid">
		{#each sites as site}
			<div class="site-card bg-slate-50 border-2 border-slate-200 hover:border-blue-500 hover:bg-slate-100 transition-all duration-200 shadow-sm hover:shadow-lg">
				<div class="site-header">
					<span class="site-icon">{site.icon}</span>
					<div class="site-info">
						<h3 class="site-name">{site.name}</h3>
						<span class="site-url">{site.url}</span>
					</div>
					<div class="status-indicator {site.status}">
						<span class="status-dot"></span>
						<span class="status-text">{site.status}</span>
					</div>
				</div>
				<p class="site-description">{site.description}</p>
				<div class="site-actions">
					<a href={site.url} target="_blank" rel="noopener noreferrer" class="btn btn-primary">
						Visit Site
					</a>
				</div>
			</div>
		{/each}
	</section>

	<section class="quick-stats">
		<div class="stat-card">
			<h3>Total Sites</h3>
			<p class="stat-number">{sites.length}</p>
		</div>
		<div class="stat-card">
			<h3>Online</h3>
			<p class="stat-number">{sites.filter(s => s.status === 'online').length}</p>
		</div>
		<div class="stat-card">
			<h3>Uptime</h3>
			<p class="stat-number">99.9%</p>
		</div>
	</section>
</div>

<style>
	.dashboard {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem 1rem;
	}

	.dashboard-header {
		text-align: center;
		margin-bottom: 3rem;
	}

	.dashboard-header h1 {
		font-size: 2.5rem;
		font-weight: 700;
		color: var(--color-text);
		margin: 0 0 0.5rem 0;
	}

	.subtitle {
		font-size: 1.1rem;
		color: var(--color-text-muted);
		margin: 0;
	}

	.sites-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
		gap: 1.5rem;
		margin-bottom: 3rem;
	}

	.site-card {
		border-radius: 12px;
		padding: 1.5rem;
		transform: translateY(0);
	}

	.site-card:hover {
		transform: translateY(-2px);
	}

	.site-header {
		display: flex;
		align-items: center;
		margin-bottom: 1rem;
	}

	.site-icon {
		font-size: 2rem;
		margin-right: 1rem;
	}

	.site-info {
		flex: 1;
	}

	.site-name {
		font-size: 1.25rem;
		font-weight: 600;
		margin: 0 0 0.25rem 0;
		color: var(--color-text);
	}

	.site-url {
		font-size: 0.875rem;
		color: var(--color-text);
		font-family: monospace;
		opacity: 0.8;
	}

	.status-indicator {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		font-size: 0.875rem;
		font-weight: 500;
	}

	.status-indicator.online {
		color: #10b981;
	}

	.status-indicator.offline {
		color: #ef4444;
	}

	.status-dot {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: currentColor;
	}

	.site-description {
		color: var(--color-text-muted);
		margin: 0 0 1.5rem 0;
		line-height: 1.5;
	}

	.site-actions {
		display: flex;
		gap: 0.75rem;
	}

	.btn {
		padding: 0.5rem 1rem;
		border-radius: 6px;
		font-weight: 500;
		text-decoration: none;
		border: none;
		cursor: pointer;
		transition: all 0.2s ease;
		font-size: 0.875rem;
	}

	.btn-primary {
		background: var(--color-theme-1);
		color: white;
	}

	.btn-primary:hover {
		background: var(--color-theme-2);
	}

	.btn-secondary {
		background: var(--color-surface-2);
		color: var(--color-text);
	}

	.btn-secondary:hover {
		background: var(--color-surface-3);
	}



	.quick-stats {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 1.5rem;
	}

	.stat-card {
		background: var(--color-surface-0);
		border: 1px solid var(--color-surface-2);
		border-radius: 8px;
		padding: 1.5rem;
		text-align: center;
	}

	.stat-card h3 {
		font-size: 0.875rem;
		font-weight: 500;
		color: var(--color-text-muted);
		margin: 0 0 0.5rem 0;
		text-transform: uppercase;
		letter-spacing: 0.05em;
	}

	.stat-number {
		font-size: 2rem;
		font-weight: 700;
		color: var(--color-text);
		margin: 0;
	}

	@media (max-width: 768px) {
		.dashboard {
			padding: 1rem 0.5rem;
		}

		.dashboard-header h1 {
			font-size: 2rem;
		}

		.sites-grid {
			grid-template-columns: 1fr;
		}

		.site-actions {
			flex-direction: column;
		}

		.quick-stats {
			grid-template-columns: 1fr;
		}
	}
</style>
