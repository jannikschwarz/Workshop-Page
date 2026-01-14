<script>
    import { onMount } from "svelte";

    //Window scroll states
    let content = $state();
    let yHeight = $state();
    let yScroll = $state(1);
    
    onMount(() => {
        yHeight = content.scrollHeight-content.clientHeight
    });

    function parseScroll(){
        if(content.scrollTop != 0)
            yScroll = Math.floor((content.scrollTop / yHeight) * 100);
        else 
            yScroll = 0;
    }
</script>

<div class="hobbies" bind:this={content} onscroll={() => parseScroll()}>
    <div class="content grid">
        <div class="hobby grid">
            
        </div>
        <div class="hobby grid">

        </div>
        <div class="hobby grid">

        </div>
    </div>
</div>

<!-- svelte-ignore element_invalid_self_closing_tag -->
<div class="scroll-indication grid">
    <div class="indication cursor-p {yScroll >= 0 && yScroll <= 23.3333 ? "inner-h-1 c-focus" : "inner-h-2 c-hide"}">Top part</div>
    <div class="line">
        <div class="inner-line"/>
    </div>
    <div class="indication cursor-p {yScroll >= 30.3333 && yScroll <= 61.6666 ? "inner-h-1 c-focus" : "inner-h-2 c-hide"}">Top part</div>
    <div class="line">
        <div class="inner-line"/>
    </div>
    <div class="indication {yScroll >= 70.6666 && yScroll <= 100 ? "inner-h-1 c-focus" : "inner-h-2 c-hide"}">Top part</div>
</div>

<style>
    .hobbies{
        height: 100%;
        width: 100%;
        background-color: #192428;
        overflow-y: scroll;
    }

    .hobbies::-webkit-scrollbar {
        display: none;
    }

    .content{
        height: 300vh;
        width: 100%;
        border-radius: 5px;
        background-color: #192428;
        -ms-overflow-style: none;
        scrollbar-width: none;
        grid-template-rows: 33.333% 33.333% 33.333%;
    }

    /*===Scroll indication===*/
    .scroll-indication{
        position: fixed;
        height: 150px;
        width: 150px;
        top: 40px;
        left: 40px;
        user-select: none;
        grid-template-rows: 40px auto 40px auto 40px;
    }

    .line{
        height: 100%;
        width: 2px;
    }
</style>