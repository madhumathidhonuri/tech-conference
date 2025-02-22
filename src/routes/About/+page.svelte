<script lang="ts">
    let conferenceName = "Tech Conference 2025";
    let conferenceDate = "March 15-17, 2025";
    let location = "Hyderabad, India";
    let aboutText = `
        Welcome to ${conferenceName}, the premier event for tech enthusiasts, innovators, and industry leaders. 
        Join us from ${conferenceDate} in ${location} for an immersive experience filled with insightful sessions, 
        groundbreaking keynotes, and unparalleled networking opportunities.
    `;
</script>

<style>
    .about-container {
        max-width: 900px;
        margin: auto;
        text-align: center;
        padding: 60px 20px;
        background: #0f172a;
        color: #e2e8f0; 
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        margin-top: 80px; 
    }


    .about-heading {
        font-size: 2.8rem;
        font-weight: bold;
        color: #facc15; 
        margin-bottom: 20px;
        text-transform: uppercase;
        letter-spacing: 1.5px;
    }

    .about-text {
        font-size: 1.2rem;
        line-height: 1.8;
        color: #94a3b8; 
        margin-bottom: 30px;
    }

    .highlight {
        color: #2563eb; 
        font-weight: bold;
    }

</style>

<div class="about-container">
    <h1 class="about-heading">About {conferenceName}</h1>
    <p class="about-text">{aboutText}</p>
    <p class="about-text">
        Experience <span class="highlight">AI, Web3, Cloud Computing, Cybersecurity</span>, and much more with experts 
        from around the world. Don't miss this opportunity to be part of the future of technology!
    </p>
</div>
