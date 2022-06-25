<script>
    import ProgressBar from "./ProgressBar.svelte";
    const totalSeconds = 20;
    let secondLeft = totalSeconds;
    let isRunning = false;
    $: progress = ((totalSeconds - secondLeft) / totalSeconds) * 100;
    function startTimer(){
        isRunning = true;
        const timer = setInterval(() => {
            secondLeft--;
            if(secondLeft == 0){
                clearInterval(timer);
                isRunning = false;
                secondLeft = totalSeconds;
            }
        },1000);
    }

    // function startTimer(){  Solutia Dragos
    //     if(isRunning === false){ 
    //         setInterval(Timer,1000);
    //         function Timer(){
    //             if(secondLeft > 0){
    //             secondLeft--;
    //             }
    //         }
    //         isRunning = true;
    //     }
    // }

</script>
<style>
    h2{
        margin: 0;
    }
    .start{
        background-color: rgb(47, 71, 97);
        width:100%;
        margin: 10px 0;
    }
    .start[disabled]{
        background-color: #b7b7b7;
        cursor: not-allowed;
    }
</style>
<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">
        Second left: {secondLeft}
    </h2>
</div>
<ProgressBar progress={progress}/>

<div bp="grid">
    <button 
    disabled={isRunning}
    on:click="{startTimer}"
    bp="offset-5@md 4@md 12@sm" 
    class = "start">Start</button>
</div>
