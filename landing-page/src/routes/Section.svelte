<!-- Section.svelte -->
<script>
    import GrafanaDashboard from "./GrafanaDashboard.svelte";

    export let id;
    export let title;
    function isIntropage() {
        return id === "section1" ;

    }
    function isProblemPage() {
        return id === "section2" ;
    }
    function isDashboard() {
        return id === "section3";
    }
    function isArchitecturePage() {
        return id === "section4" ;
    }
    function isObservabilityPage() {
        return id === "section6" ;
    }
    function isLearningPage() {
        return id === "section5" ;
    }

        function toggleFullScreen() {
        const iframe = document.getElementById('iframe');
        if (!document.fullscreenElement) {
        iframe.requestFullscreen().catch(err => {
        console.error(`Error attempting to enable full-screen mode: ${err.message}`);
    });
    } else {
        document.exitFullscreen();
    }
    }
</script>

<section id={id} class="section">

    {#if isDashboard()}
        <div class="dashboard ">
            <header class="header">{title}</header>
        </div>
        <GrafanaDashboard />
        <div class="button-wrapper">
            <button class="button" on:click={toggleFullScreen}>Expand</button>
        </div>
    {:else if isProblemPage()}
        <header class="different-header">{title}</header>
        <div class="containerwhite">
            <div class="white-rounded-text-field-the-idea">
                <div class="problemStatement">
                    <p class="line"><span class="icon">🖥️</span> You can use Grafana to display server usage data.</p>
                    <p class="line"><span class="icon">📊</span> You can use Grafana to display rack usage data.</p>
                    <p class="line"><span class="icon">🌡️</span> Let's use Grafana to display rack environment data.</p>
                </div>
            </div>
        </div>
    {:else if isArchitecturePage()}
        <div >
            <header class="header">{title}</header>
            <div style="justify-content: center; display: flex">
                <img class="our-approach-diagram" src="diagram.svg" alt="Description of the image">

            </div>
            <!--div class="containerwhite">
                <div class="white-rounded-text-field">
                    <h1 style="text-align: center;"> The Team</h1>
                </div>
                <div class="white-rounded-text-field">
                    <h1 style="text-align: center;"> Our Infrastructure</h1>
                </div>
            </div-->

        </div>
    {:else if isIntropage()}
        <div class="first-page">
            <h1 style="margin: 0px; ">{title}</h1>

            <div class="images">
                <img class="img" src="grafana.svg" alt="Description of the image">
                <img class="x-image" src="x-letter.svg" alt="Description of the image">
                <img class="img" src="namecheap.svg" alt="Description of the image">
            </div>

        </div>

    {:else if isLearningPage()}
        <header class="header">{title}</header>
        <div class="profile-pics">
            <div style="padding: 30px;">
                <img class="profile-pic" src="miika.svg" alt="Description of the image">
                <div class="personal-learning">Miika</div>
                <div class="personal-learning"> "I tackled embedded microcontroller programming for the first time and overcame server management challenges."</div>

            </div>
            <div style="padding: 30px;">
                <img class="profile-pic" src="pol.svg" alt="Description of the image">
                <div class="personal-learning">Pol</div>
                <div class="personal-learning"> "I mastered network management on low-power devices and dealt with cross compiling for embedded targets with no OS."</div>

            </div>
            <div style="padding: 30px;">
                <img class="profile-pic" src="valentin.svg" alt="Description of the image">
                <div class="personal-learning">Valentin</div>
                <div class="personal-learning"> "I used SvelteKit for the first time to build this website and thereby learned the intricacies of UI design and SVGs."</div>
            </div >

            <div style="padding: 30px;">
                <img class="profile-pic" src="justus.svg" alt="Description of the image">
                <div class="personal-learning">Justus</div>
                <div class="personal-learning"> "I discovered how valuable hardware prototyping with everyday items can be, boosting our project's uniqueness and team dynamics."</div>
            </div>

        </div>
        <div class="devpost-link-wrapper">
            <div class="devpost-link">
                Want to learn more about our project? Check out our&nbsp; <a href="https://devpost.com/software/serfana" class="devpost-link">devpost</a>!
            </div>

        </div>
    {/if}

</section>


<style>
    .our-approach-diagram {
        width: 700px;
        height: 700px;
    }
    .x-image {
        width: 40px;
        height: 40px;
        margin-right: 10px;
    }
    .personal-learning {
        display: grid;
        justify-content: center;
        width: 200px;
        margin-top: 15px;
        color: black;
        font-weight: bold;
    }
    .devpost-link {
        padding-bottom: 40px;
        font-weight: bold;
        color: black;
        justify-content: center;
        display: flex;
        font-size: 23px;
    }
    .devpost-link-wrapper {
        margin-top: 20px;

    }
    .profile-pic {
        width: 200px;
        height: 200px;
    }
    .profile-pics {
        display: flex;
        justify-content: center; /* Center horizontally */
        align-items: start; /* Center vertically */
        margin-left: 100px;
        margin-right: 100px;
    }
    .button-wrapper {
        margin-top: 20px;
        justify-content: center;
        display: flex;
    }
    .img {
        width: 60px;
        height: 60px;
        margin-right: 10px;
    }
    .dashboard {
        justify-content: center;
        display: flex;
        align-items: center;
    }
    .images {
        display: flex;
        justify-content: center; /* Center horizontally */
        align-items: center; /* Center vertically */
    }

    .first-page {
        text-align: center; /* Center the text horizontally */
        font-size: 70px; /* Set the font size to 36 pixels or adjust as needed */
        justify-content: center; /* Center horizontally */
        height: 100vh; /* Set height to 100% of viewport height */
        align-items: center;
        display: grid;
    }
    .button {
        display: grid;
        padding: 8px 16px;
        background-color: #3A5A40 ;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        height: 40px;
        align-items: center;
    }
    .header {
        margin-bottom: 30px;
        font-size: 50px;
        justify-content: center;
        display: grid;
        font-weight: bold;
        margin-top: 45px;
    }
    .different-header {
        margin-bottom: 30px;
        font-size: 50px;
        justify-content: center;
        display: grid;
        font-weight: bold;
        margin-top: 100px;
    }
    .section {

    }

    .white-rounded-text-field-the-idea {
        width: 90%; /* Adjust width as needed */
        padding: 20px;
        background-color: #f5f5f5; /* Light gray color */
        border-radius: 10px;
        color: black;
        justify-content: center;
    }

    .white-rounded-text-field:last-child {
        margin-right: 0; /* Remove right margin from the last box to prevent extra spacing */
    }
    .containerwhite {
        display: flex;
        justify-content: center;
    }
    .problemStatement {
        color: black;
        display:grid;
        justify-content: center;
        font-weight: bold;


    }


    .line {
        font-size: 1.5rem;
        font-weight: 600;
        margin-bottom: 10px;
        color: #444;
        display: flex;
        align-items: center;
        animation: fadeIn 1s ease-in;
    }

    .icon {
        margin-right: 10px;
    }

    @keyframes fadeIn {
        0% {
            opacity: 0;
            transform: translateX(-20%);
        }
        100% {
            opacity: 1;
            transform: translateX(0);
        }
    }



</style>
