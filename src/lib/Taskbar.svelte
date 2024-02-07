<taskbar>
    <div class="blockOne">
        <img src="/overlay_transparent.png" alt="logo" width="300" height="300">
        <div>luc</div>
        <div class="g">21</div>

        <a class="menuOption" href="/">main</a>
        <a class="menuOption" href="/about">about</a>
        <a class="menuOption" href="/projects">projects</a>
        <a class="menuOption" href="/radio">radio</a>
    </div>
</taskbar>

<style>
    taskbar {
        border-right: 1px dotted white;
        height: 37.5rem;
        align-items: center;
    }

    img {
        margin-top: 20px;
        margin-bottom: 20px;
    }

    .g {
        margin-bottom: 20px;
    }

    .blockOne {
        flex-basis: 39%;
        display: flex;
        flex-direction: column;
    }

    .menuOption {
        margin: 0;
        font-family: "Redaction";
        font-size: 17px;
    }
</style>