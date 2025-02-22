<script>
    import { createEventDispatcher } from "svelte";
    let name = "";
    let email = "";
    let phone = "";
    let isSubmitted = false;
    const dispatch = createEventDispatcher();

    const handleSubmit = () => {
        alert(`Registration Successful!\nName: ${name}\nEmail: ${email}\nPhone: ${phone}`);
        isSubmitted = true;
        dispatch("registered"); 
    };
</script>

<style>
    .form-container {
        max-width: 400px;
        margin: 40px auto;
        background: white;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
        text-align: center;
    }

    h2 {
        margin-bottom: 20px;
        font-size: 22px;
        font-weight: bold;
    }

    input {
        width: 100%;
        padding: 12px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 16px;
    }

    button {
        width: 100%;
        padding: 12px;
        background: #1E40AF;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
        font-weight: bold;
        margin-top: 10px;
    }

    button:hover {
        background: #1E3A8A;
    }
</style>

{#if !isSubmitted}
    <div class="form-container">
        <h2>Register for Tech Conference</h2>
        <form on:submit|preventDefault={handleSubmit}>
            <input type="text" bind:value={name} placeholder="Your Name" required />
            <input type="email" bind:value={email} placeholder="Your Email" required />
            <input type="tel" bind:value={phone} placeholder="Your Phone" required />
            <button type="submit">Submit</button>
        </form>
    </div>
{/if}
