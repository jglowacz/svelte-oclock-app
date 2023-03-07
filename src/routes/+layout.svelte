<!-- <nav class="nav flex-sm-column">
    <ul class="nav-link active>
    <a href="/">Main</a>
    <a href="/sleeplater">Sleep Later</a>
    <a href="/sleepnow">Sleep Now</a>
    <a href="/wakeup">Wake Up</a>
</nav> -->
<main>
<!-- <ul class="nav nav-tabs">
    <li class="nav-item"> -->

    <!-- </li> -->
    <!-- <li class="nav-item"> -->
        <a class="nav-link" href="/sleepnow">Sleep Now</a>
    <!-- </li> -->
    <!-- <li class="nav-item"> -->
        <a class="nav-link" href="/sleeplater">Sleep Later</a>
    <!-- </li> -->
    <!-- <li class="nav-item"> -->
        <a class="nav-link" href="/wakeup">Wake Up</a>
    <!-- </li>
</ul> -->

<slot />
</main>
<style>
    :global(:root) {
        --primary: #3949ab;
    }

    main {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
    }
</style>
