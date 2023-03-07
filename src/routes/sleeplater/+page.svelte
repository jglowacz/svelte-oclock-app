<script>
    let time = "00:00";
    const calculateTime = (value) => {
        const cycleTotal = 6;
        const cycleLength = 90 * 60 * 1000; // 90 minutes to be considered as 1 cycle
        const beforeSleepLength = 14 * 60 * 1000; // 14 minutes as estimated time to fall asleep
        const hours = value.slice(0, 2);
        const minutes = value.slice(3, 5);
        const d = new Date();
        d.setHours(hours);
        d.setMinutes(minutes);
        d.setSeconds(0);
        const timestamp = d.getTime();
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
        console.log(getFinalHours)
        return getFinalHours;
    }
    // let hours = calculateTime(value);
</script>

<h4>Sleep Later</h4>
<input type="time" bind:value={time} />
<button on:click={calculateTime(time)} type="submit">Submit</button>
<p>{time}</p>
<ul>
    {#each calculateTime(time) as hour}
    <li>{hour}</li>
    {:else}
    <li>Empty list</li>
    {/each}
</ul>