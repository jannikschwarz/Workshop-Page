<script>
    import Header from "./Header.svelte";
    import Hobbies from "./Hobbies/Hobbies.svelte";

    //Window states
    let tab = $state(0);
    
</script>

<div class="main">
    <Hobbies/>
</div>

<style>
    :root {
        --color-bg: #03045e;
        --color-fg: #003366;
        --color-up: #0077b6;
        --color-high: #0096c7;
        --color-high-2: #00b4d8;
        --color-light: #48cae4;
        --color-hide: #003566;
    }

    .main{
        height: 100vh;
        width: 100vw;
        overflow-x: hidden;
        font-family: Segoe UI;
        background-color: var(--color-bg);
    }
    

    /*===Global styling===*/
    .inner-box-1{
        border-radius: 5px;
        background-color: var(--color-fg);
    }

    .inner-box-2{
        border-radius: 5px;
        background-color: var(--color-up);
    }

    /*Alignment*/
    .main :global(.grid){
        display: grid;
    }

    .main :global(.align-center){
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .main :global(.align-left){
        display: flex;
        justify-content: start;
        align-items: center;
    }

    .main :global(.align-right){
        display: flex;
        justify-content: end;
        align-items: center;
    }

    /*Headers*/
    .main :global(.h-1){
        font-size: 45px;
        color: #caf0f8;
        font-weight: 600;
    }

    .main :global(.h-2){
        font-size: 40px;
        color: #caf0f8;
    }

    .main :global(.inner-h-1){
        font-size: 35px;
        font-weight: 600;
        letter-spacing: .3;
    }

    /*Cursors*/
    .main :global(.c-p){
        cursor: pointer;
    }

    /*Styling*/
    .main :global(.c-focus){
        color: var(--color-high);
    }

    .main :global(.c-backdrop){
        color: var(--color-hide);
    }
</style>
