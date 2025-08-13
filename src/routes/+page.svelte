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
	<title>EBT Labs</title>
	<meta name="description" content="Dashboard for EBT Labs sites and projects" />
</svelte:head>

<div class="dashboard">
	<header class="app-header">
		<h1 class="app-title">EBT Labs</h1>
		<p class="app-subtitle">A collection of apps and services</p>
	</header>

	<section class="sites-grid">
		{#each sites as site}
			<div class="card site-card">
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
					<a href={site.url} target="_blank" rel="noopener noreferrer" class="primary-button">
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
	.dashboard { padding: 1rem 0; }

	.app-header {
		text-align: center;
		margin: 0 0 2rem 0;
		padding: 1rem 0 0.5rem 0;
	}

	.app-title {
		font-size: 3rem;
		font-weight: 800;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
		margin: 0 0 0.25rem 0;
	}

	.app-subtitle {
		font-size: 1.1rem;
		color: var(--color-text-muted);
		margin: 0;
	}

	.sites-grid {
		display: grid;
		grid-template-columns: repeat(2, minmax(0, 1fr));
		gap: 1.5rem;
		margin-bottom: 2rem;
	}

	.site-card { padding: 1.25rem; }

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

	.site-name { font-size: 1.25rem; font-weight: 700; margin: 0 0 0.25rem 0; color: var(--color-text); }

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

	.status-indicator.online { color: #10b981; }
	.status-indicator.offline { color: #ef4444; }

	.status-dot {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: currentColor;
	}

	.site-description { color: var(--color-text-muted); margin: 0 0 1.25rem 0; line-height: 1.6; }

	.site-actions { display: flex; gap: 0.75rem; }

	.primary-button {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		gap: 0.5rem;
		padding: 0.65rem 1.25rem;
		border-radius: 0.75rem;
		font-weight: 700;
		font-size: 0.95rem;
		color: white;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		border: none;
		text-decoration: none;
		box-shadow: 0 2px 8px rgba(102,126,234,0.25);
		transition: transform 0.2s ease, box-shadow 0.2s ease;
	}

	.primary-button:hover { transform: translateY(-2px); box-shadow: 0 8px 25px rgba(102,126,234,0.3); }



	.quick-stats {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 1.5rem;
	}

	.stat-card {
		background: #fff;
		border: 1px solid #e5e7eb;
		border-radius: 1rem;
		padding: 1.5rem;
		text-align: center;
		box-shadow: 0 4px 6px rgba(0,0,0,0.05);
	}

	.stat-card h3 {
		font-size: 0.875rem;
		font-weight: 500;
		color: var(--color-text-muted);
		margin: 0 0 0.5rem 0;
		text-transform: uppercase;
		letter-spacing: 0.05em;
	}

	.stat-number { font-size: 2rem; font-weight: 800; color: var(--color-text); margin: 0; }

	@media (max-width: 768px) {
		.dashboard { padding: 0.5rem 0.25rem; }
		.app-title { font-size: 2.4rem; }
		.sites-grid { grid-template-columns: 1fr; }
		.site-actions { flex-direction: column; }
		.quick-stats { grid-template-columns: 1fr; }
	}
</style>
