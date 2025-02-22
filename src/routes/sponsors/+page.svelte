<script lang="ts">
	let sponsors = [
		{
			name: 'Google',
			logo: '/logos/google_logo.png',
			link: 'https://www.google.com',
			tier: 'Gold'
		},
		{
			name: 'Microsoft',
			logo: '/logos/microsoft_logo.png',
			link: 'https://www.microsoft.com',
			tier: 'Silver'
		},
		{
			name: 'Amazon Web Services',
			logo: '/logos/aws_logo.png',
			link: 'https://aws.amazon.com',
			tier: 'Bronze'
		},
		{ name: 'IBM', logo: '/logos/IBM-logo.png', link: 'https://www.ibm.com', tier: 'Gold' },
		{ name: 'Intel', logo: '/logos/intel_logo.png', link: 'https://www.intel.com', tier: 'Silver' }
	];

	// Add location details
	let location = {
		name: 'Tech Conference Venue',
		address: '123 Tech Lane, Hyderabad, India',
		mapUrl:
			'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3916.598586602702!2d78.40593361478386!3d17.42598518807371!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3badb5fd7f5ff3d7%3A0x8d00d5c63fc1d49e!2sTech%20Conference%20Venue!5e0!3m2!1sen!2sin!4v1648180690268!5m2!1sen!2sin'
	};
</script>

<!-- Sponsors Section -->
<div class="sponsors-container">
	<h1>🏆 Our Sponsors</h1>

	{#each ['Gold', 'Silver', 'Bronze'] as tier}
		<h2 class={tier.toLowerCase()}>{tier} Sponsors</h2>
		<div class="grid">
			{#each sponsors.filter((sponsor) => sponsor.tier === tier) as sponsor}
				<div class="sponsor-card">
					<img class="sponsor-logo" src={sponsor.logo} alt={sponsor.name} />
					<p class="sponsor-name">{sponsor.name}</p>
					<a class="sponsor-link" href={sponsor.link} target="_blank">Visit Website</a>
				</div>
			{/each}
		</div>
	{/each}

	<!-- Location Details -->
	<div class="location-container">
		<h2>📍 Location</h2>
		<p>{location.name}</p>
		<p>{location.address}</p>

		<!-- Embedded Google Map -->
		<div class="map-container">
			<iframe
				src={location.mapUrl}
				width="100%"
				height="100%"
				style="border:0;"
				allowfullscreen=""
				loading="lazy"
			></iframe>
		</div>
	</div>
</div>

<style>
	.sponsors-container {
		padding: 60px 20px;
		text-align: center;
		background: #0f172a;
		color: #e2e8f0;
		margin-bottom: 40px; /* Adds space below sponsors container */
	}

	h1 {
		font-size: 2.5rem;
		text-transform: uppercase;
		font-weight: bold;
		letter-spacing: 1.5px;
		margin: 40px 0;
		position: relative;
		display: inline-block;
		padding-bottom: 10px;
		text-align: center;
		width: 100%;
	}

	h1::after {
		content: '';
		display: block;
		width: 20%; /* Responsive width */
		max-width: 120px; /* Prevents it from getting too wide */
		height: 4px;
		background: #06b6d4; /* Vibrant cyan */
		margin: 10px auto 0;
		border-radius: 2px;
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 40px; /* Increase gap between cards */
		max-width: 1000px;
		margin: auto;
	}
	.sponsor-card {
		background: #f3f4f6;
		border-radius: 12px;
		padding: 30px;
		text-align: center;
		box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
		transition:
			transform 0.3s ease-in-out,
			box-shadow 0.3s ease-in-out;
		margin: 20px; /* Adds space around each card */
	}
	.sponsor-card:hover {
		transform: scale(1.05);
		box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
	}

	.sponsor-logo {
		max-width: 100px;
		height: auto;
		margin-bottom: 15px;
	}

	.sponsor-name {
		font-size: 1.3rem;
		font-weight: bold;
        color: #1e293b;
	}

	.sponsor-link {
		display: inline-block;
		margin-top: 12px;
		text-decoration: none;
		font-size: 1rem;
		color: #0284c7; /* Bright blue */
		font-weight: bold;
		transition: color 0.3s ease-in-out;
	}

	.sponsor-link:hover {
		color: #0369a1; /* Darker blue on hover */
	}

	.gold {
		color: gold;
		text-shadow: 0px 0px 10px rgba(255, 215, 0, 0.7); /* Glowing gold effect */
	}

	.silver {
		color: #bfc9d1; /* Metallic silver */
		text-shadow: 0px 0px 8px rgba(191, 201, 209, 0.5);
	}

	.bronze {
		color: #b87333; /* Rich bronze */
		text-shadow: 0px 0px 8px rgba(184, 115, 51, 0.5);
	}

	.location-container {
		margin-top: 40px;
		text-align: left;
	}

	.map-container {
		width: 100%;
		height: 400px;
		margin-top: 20px;
	}
</style>
