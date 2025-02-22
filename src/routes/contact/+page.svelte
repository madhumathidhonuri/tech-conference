<script lang="ts">
    let name = "";
    let email = "";
    let message = "";

    function submitForm() {
        alert(`Thank you, ${name}! Your message has been sent.`);
        name = "";
        email = "";
        message = "";
    }
</script>

<style>
    .contact-container {
        max-width: 600px;
        margin: 80px auto;
        padding: 40px;
        background: #0f172a; 
        color: #e2e8f0; 
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        text-align: center;
    }

    .contact-container h2 {
        font-size: 2rem;
        color: #facc15; 
        margin-bottom: 20px;
    }

    .form-group {
        margin-bottom: 15px;
        text-align: left;
    }

    label {
        font-size: 1rem;
        font-weight: bold;
        display: block;
        margin-bottom: 5px;
        color: #e2e8f0;
    }

    input, textarea {
        width: 100%;
        padding: 12px;
        border-radius: 6px;
        border: none;
        background: #1e293b;
        color: #e2e8f0;
        font-size: 1rem;
        outline: none;
    }

    textarea {
        height: 100px;
        resize: none;
    }

    .submit-btn {
        width: 100%;
        padding: 12px;
        background: #2563eb; 
        color: white;
        font-size: 1rem;
        font-weight: bold;
        border: none;
        border-radius: 6px;
        cursor: pointer;
        transition: background 0.3s ease-in-out;
    }

    .submit-btn:hover {
        background: #1e40af; 
    }

    .social-links {
        margin-top: 20px;
    }

    .social-links a {
        display: inline-block;
        margin: 0 10px;
        color: #ffffff; 
        font-size: 1.5rem;
        transition: color 0.3s ease-in-out;
    }

    .social-links a:hover {
        color: #fbbf24; 
    }
</style>

<div class="contact-container">
    <h2>Contact Us</h2>
    <form on:submit|preventDefault={submitForm}>
        <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" bind:value={name} required>
        </div>
        <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" bind:value={email} required>
        </div>
        <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" bind:value={message} required></textarea>
        </div>
        <button type="submit" class="submit-btn">Send Message</button>
    </form>

    <div class="social-links">
        <a href="https://facebook.com" target="_blank">🌐 Facebook</a>
        <a href="https://twitter.com" target="_blank">🐦 Twitter</a>
        <a href="https://linkedin.com" target="_blank">🔗 LinkedIn</a>
    </div>
</div>
