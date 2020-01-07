<script>
    import NavLogo from './NavLogo.svelte';
</script>

<style>
.nav{
    display: flex;
    flex-direction: row;
    position: absolute;
    left: 0%;
    right: 0%;
    top: 0%;
    bottom: 0%;
    right: 0;
    height: 97px;
    z-index: 50;
    border-bottom: 1px solid #3D3D3D;
}

</style>

<div class="nav text-primary">
    <NavLogo />
</div>
