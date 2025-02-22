<script lang="ts">
    let speakers = [
        { name: "Dr. Jane Doe", title: "AI Expert", bio: "Leading researcher in artificial intelligence.", image: "logos/jane_doe.jpg" },
        { name: "John Smith", title: "Blockchain Specialist", bio: "Expert in decentralized finance and Web3.", image: "logos/john_smith.jpg" },
        { name: "Lisa Wong", title: "Cloud Architect", bio: "Innovator in cloud computing solutions.", image: "logos/lisa_wong.jpg" }
    ];
</script>

<style>
    body {
        background: #0f172a;
        color: #e2e8f0;
        font-family: Arial, sans-serif;
    }

    .speakers-section {
        text-align: center;
        padding: 60px 20px;
    }

    .speakers-heading {
        font-size: 3rem;
        font-weight: bold;
        color: #facc15; 
        text-transform: uppercase;
        margin-bottom: 40px;
    }

    .speakers-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 30px;
        max-width: 1200px;
        margin: auto;
    }

    .speaker-card {
        background: #1e293b;
        padding: 20px;
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(255, 255, 255, 0.1);
        transition: transform 0.3s ease-in-out;
        text-align: center;
    }

    .speaker-card:hover {
        transform: scale(1.05);
        background: #334155; 
    }

    .speaker-img {
        width: 120px;
        height: 120px;
        border-radius: 50%;
        object-fit: cover;
        margin-bottom: 15px;
    }

    .speaker-name {
        font-size: 1.5rem;
        font-weight: bold;
        margin-bottom: 5px;
    }

    .speaker-title {
        font-size: 1.1rem;
        color: #93c5fd; 
        margin-bottom: 10px;
    }

    .speaker-bio {
        font-size: 1rem;
        color: #cbd5e1; 
    }
</style>

<div class="speakers-section">
    <h2 class="speakers-heading">🎤 Meet Our Speakers</h2>
    <div class="speakers-grid">
        {#each speakers as speaker}
            <div class="speaker-card">
                <img class="speaker-img" src={speaker.image} alt={speaker.name}>
                <div class="speaker-name">{speaker.name}</div>
                <div class="speaker-title">{speaker.title}</div>
                <p class="speaker-bio">{speaker.bio}</p>
            </div>
        {/each}
    </div>
</div>
