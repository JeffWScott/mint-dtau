<script>

    //Images
    import lamden_logo from './images/lamden_logo_new.svg';
    import lamden_words from './images/lamden_words.svg';

    function openLink(url){
        window.open(url, '_blank');
    }

</script>

<style>
.box{
    min-width: 354px;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.brand{
    display: flex;
    flex-direction: row;
    align-items: center;
}

.clickable{
    cursor: pointer;
}

.logo {
    width: 32px;
    margin-right: 15.5px;
    margin-left: 51px;
}

.words {
    width: 90px;
}

</style>

<div class="box">
    <div class="brand clickable" on:click={() => openLink('https://www.lamden.io')}>
        <div class="logo" >{@html lamden_logo} </div>
        <div class="words" >{@html lamden_words} </div>
    </div>
</div>