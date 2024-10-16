<script>

</script>

<header>
    <nav>
        <a href="/">Home page</a>
        <a href="/">About</a>
        <a href="/">Svelte</a>
    </nav>
</header>

<style lang="scss">
    header{
        width: 100%;
        height: 100px;
        padding-right: 36px;
        box-sizing: border-box;
        background-color: rgba(63, 63, 65, 0.631);
        backdrop-filter: blur(10px);
        position: sticky;
        margin: 0;
        top: 0;
        z-index: 10;

        nav{
            width: 100%;
            height: 100%;
            display: flex;
            gap: 36px;
            justify-content: flex-end;
            align-items: center;

            a{
                color: white;
                font-weight: bold;
                text-decoration: none;
                transition: ease .3s;

                &:hover{
                    color: red;
                }
            }
        }
    }


</style>
