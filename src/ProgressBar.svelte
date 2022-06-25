<script>
    export let progress = 20;
</script>

<style>
    .progress-container{
        margin: 20px 0;
        border:solid #b7b7b7 1px;
    }

    .progress-bar{
        height: 30px;
        background-color: rgb(33, 187, 33);
    }
</style>

<div bp="grid">
    <div bp="offset-5@md 4@md 12@sm" 
    class="progress-container">
        <div class="progress-bar"
            style="width:{progress}%">
            <span class="sr-only">%</span>
        </div>
    </div>
</div>