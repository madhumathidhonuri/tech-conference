<script lang="ts">
	import { onMount } from 'svelte';
	import Register from '$lib/Register.svelte';

	let isRegistered = false;
	let showForm = false; 
	let conferenceDate = 'March 15-17, 2025';

	let countdown = { days: 0, hours: 0, minutes: 0, seconds: 0 };
	let speakers = [
		{ name: 'Dr. Jane Doe', topic: 'AI & Future Tech' },
		{ name: 'John Smith', topic: 'Web3 & Blockchain' },
		{ name: 'Lisa Wong', topic: 'Cloud Innovations' }
	];
	let schedule = [
		{ time: '10:00 AM', event: 'Keynote Speech' },
		{ time: '11:30 AM', event: 'AI in 2025' },
		{ time: '2:00 PM', event: 'Web3 & Blockchain' }
	];

	function toggleForm() {
		showForm = !showForm;
	}

	function registerUser() {
		isRegistered = true;
		setTimeout(() => {
			showForm = false;
		}, 2000);
	}

	function updateCountdown() {
		const eventDate = new Date('2025-03-15T00:00:00Z').getTime();
		const now = new Date().getTime();
		const distance = eventDate - now;

		countdown =
			distance > 0
				? {
						days: Math.floor(distance / (1000 * 60 * 60 * 24)),
						hours: Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
						minutes: Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60)),
						seconds: Math.floor((distance % (1000 * 60)) / 1000)
					}
				: { days: 0, hours: 0, minutes: 0, seconds: 0 };
	}

	let timer;
	onMount(() => {
		updateCountdown();
		timer = setInterval(updateCountdown, 1000);
		return () => clearInterval(timer);
	});
</script>

<div class="container">
	{#if showForm}
		<Register on:registered={registerUser} />
	{/if}
</div>

<!-- Hero Section -->
<div class="hero">
	<div class="typewriter-container">
		<h1 class="typewriter">Welcome to the Tech Conference 2025</h1>
	</div>
	<p>📍 Join us on {conferenceDate} for an exciting event!</p>

	<!-- Countdown Timer -->
	<div class="countdown">
		<strong>Countdown to Event:</strong>
		{countdown.days} Days {countdown.hours} Hours {countdown.minutes} Minutes {countdown.seconds} Seconds
	</div>

	{#if !isRegistered}
		<button class="cta" on:click={toggleForm} aria-label="Register for Tech Conference">
			{showForm ? 'Close Form' : 'Register Now'}
		</button>
	{/if}
</div>

<!-- Event Schedule -->
<div class="section">
	<h2>📅 Event Schedule</h2>
	<div class="grid">
		{#each schedule as item}
			<div class="card">
				<strong class="time">{item.time}</strong>
				<p class="event">{item.event}</p>
			</div>
		{/each}
	</div>
</div>

<!-- Featured Speakers -->
<div class="section">
	<h2>🎤 Featured Speakers</h2>
	<div class="grid">
		{#each speakers as speaker}
			<div class="card">
				<strong>{speaker.name}</strong> - {speaker.topic}
			</div>
		{/each}
	</div>
</div>

<style>
	body {
		font-family: Arial, sans-serif;
		margin: 0;
		padding: 0;
		background-color: #f1f5f9;
		color: #1e293b;
	}

	.hero {
		text-align: center;
		padding: 80px 20px;
		background: #0f172a;
		color: white;
	}
	.hero h1 {
		font-size: 2.5rem;
		font-weight: 700;
		text-shadow: 2px 2px 10px rgba(255, 255, 255, 0.2);
		letter-spacing: 1.5px;
	}

	.typewriter-container {
		font-size: 1rem;
		font-weight: bold;
		color: #ffffff;
		border-right: 2px solid white;
		display: inline-block;
		white-space: nowrap;
		overflow: hidden;
		animation:
			typing 5s steps(30, end),
			blink 0.5s step-end infinite;
	}
	@keyframes typing {
		from {
			width: 0;
		}
		to {
			width: 100%;
		}
	}

	@keyframes blink {
		from {
			border-right-color: white;
		}
		to {
			border-right-color: transparent;
		}
	}

	.countdown {
		font-size: 1.5rem;
		font-weight: bold;
		color: #facc15;
		text-shadow: 1px 1px 10px rgba(255, 255, 255, 0.2);
	}

	.cta {
		background-color: #facc15;
		padding: 12px 24px;
		border-radius: 8px;
		font-size: 1.2rem;
		cursor: pointer;
		margin-top: 20px;
		transition:
			background 0.3s ease,
			transform 0.2s ease;
		box-shadow: 2px 2px 8px rgba(255, 255, 255, 0.1);
	}

	.cta:hover {
		background-color: #eab308;
		transform: scale(1.05);
		box-shadow: 2px 2px 15px rgba(255, 255, 255, 0.2);
	}

	.section {
		padding: 60px 20px;
		text-align: center;
		background-color: #0f172a;
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 20px;
		padding: 20px;
	}

	.card {
		background: #1e293b;
		color: white;
		padding: 20px;
		border-radius: 12px;
		transition:
			transform 0.3s ease,
			background 0.3s ease;
	}

	.card:hover {
		transform: translateY(-5px);
		background: #2563eb;
	}
</style>
