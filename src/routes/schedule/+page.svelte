<script lang="ts">
    let activeTab = 'day1'; // Default tab
    const tabs = ['day1', 'day2', 'track1', 'track2'];

    let schedule = [
        { date: "March 15, 2025", time: "10:00 AM", topic: "Keynote Speech", speaker: "Dr. Jane Doe" },
        { date: "March 15, 2025", time: "11:30 AM", topic: "AI in 2025", speaker: "Dr. Jane Doe" },
        { date: "March 15, 2025", time: "2:00 PM", topic: "Web3 & Blockchain", speaker: "John Smith" },
        { date: "March 16, 2025", time: "10:00 AM", topic: "Cloud Innovations", speaker: "Lisa Wong" },
        { date: "March 16, 2025", time: "1:00 PM", topic: "Cybersecurity Trends", speaker: "Alex Carter" },
        { date: "March 17, 2025", time: "9:00 AM", topic: "Closing Panel", speaker: "Various Experts" }
    ];
</script>

<style>
    .schedule-container {
        padding: 60px 20px;
        text-align: center;
        background-color: white;
    }

    h1 {
        font-size: 2.5rem;
        color: #1e293b;
        text-transform: uppercase;
        margin-bottom: 30px;
        position: relative;
        display: inline-block;
        padding-bottom: 10px;
    }

    h1::after {
        content: '';
        display: block;
        width: 80px;
        height: 4px;
        background-color: #2563eb;
        margin: 10px auto 0;
        border-radius: 2px;
    }

    .table-container {
        max-width: 900px;
        margin: auto;
        overflow-x: auto;
    }

    table {
        width: 100%;
        border-collapse: collapse;
        background: white;
        border-radius: 10px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    }

    th, td {
        padding: 12px 20px;
        text-align: left;
        border-bottom: 1px solid #ddd;
    }

    th {
        background: #2563eb;
        color: white;
        font-weight: bold;
        text-transform: uppercase;
    }

    tr:nth-child(even) {
        background: #f3f4f6;
    }

    tr:hover {
        background: #e5e7eb;
        transition: background 0.3s ease;
    }

    /* Tab Navigation */
    .tabs {
        display: flex;
        justify-content: center;
        gap: 15px;
        margin-top: 30px;
        margin-bottom: 20px;
    }

    .tabs button {
        padding: 10px 20px;
        border: none;
        background: #yellow;
        cursor: pointer;
        font-size: 1rem;
        border-radius: 5px;
        transition: background 0.3s ease;
    }

    .tabs button.active {
        background: #2563eb;
        color: Yellow;
        font-weight: bold;
    }

    .content {
        text-align: center;
        font-size: 1.2rem;
        margin-top: 20px;
        color: #333;
    }
</style>

<div class="schedule-container">
    <h1>📅 Conference Schedule</h1>
    <div class="table-container">
        <table>
            <thead>
                <tr>
                    <th>Date</th>
                    <th>Time</th>
                    <th>Topic</th>
                    <th>Speaker</th>
                </tr>
            </thead>
            <tbody>
                {#each schedule as session}
                    <tr>
                        <td>{session.date}</td>
                        <td>{session.time}</td>
                        <td>{session.topic}</td>
                        <td>{session.speaker}</td>
                    </tr>
                {/each}
            </tbody>
        </table>
    </div>
</div>

<!-- Tabs for Filtering -->
<div class="tabs">
    {#each tabs as tab}
        <button on:click={() => activeTab = tab} class:active={activeTab === tab}>
            {tab.toUpperCase()}
        </button>
    {/each}
</div>

<!-- Tab Content -->
<div class="content">
    {#if activeTab === 'day1'}
        <p>🔹 Content for Day 1</p>
    {:else if activeTab === 'day2'}
        <p>🔹 Content for Day 2</p>
    {:else if activeTab === 'track1'}
        <p>🔹 Content for Track 1</p>
    {:else if activeTab === 'track2'}
        <p>🔹 Content for Track 2</p>
    {/if}
</div>
