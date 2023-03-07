<script context="module">
    // const now = new Date()
    // const hour= now.toUTCString().slice(-12).slice(0,5)
    function getHours(){
        const cycleTotal = 6;
        const cycleLength = 90 * 60 * 1000; // 90 minutes to be considered as 1 cycle
        const beforeSleepLength = 14 * 60 * 1000; // 14 minutes as estimated time to fall asleep
        const currentDate = new Date();
        const timestamp = currentDate.getTime();
        let hoursArray = [];
        for (let i = 1; i < cycleTotal + 1; i++) {
            hoursArray.push(timestamp + cycleLength * i + beforeSleepLength);
        }
        let getDates = hoursArray.map((hour) => new Date(hour));
        let getLocaleTimeStrings = getDates.map(
            (hour) => `${hour.toLocaleTimeString("pl-PL")}`
        ); // In Date object hour
        let getFinalHours = getLocaleTimeStrings.map((hour) =>
            hour.slice(0, 5)
        );
        return getFinalHours;
    };
    const hours = getHours();
</script>

<h4>Sleep Now</h4>
<ul>
    {#each hours as hour}
    <li>{hour}</li>
    {:else}
    <li>Empty list</li>
    {/each}
</ul>
