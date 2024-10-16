<section class="hero">
    <!--
        <section> - HTML tag pro oddíl stránky. Používá se pro logické rozdělení obsahu.
        Tato sekce má přiřazenou třídu "hero" pro stylování.
    -->
    <img src="https://www.souepl.cz/wp-content/uploads/2016/10/logo_stredni-1.jpg" alt="">
    <!--
        <img> - HTML tag pro zobrazení obrázku.
        src - Atribut obsahující URL adresu obrázku.
        alt - Alternativní text, který se zobrazí, pokud obrázek nelze načíst, a slouží také pro přístupnost.
    -->

    <h1>Střední odborné učiliště, elektrotechnické Plzeň</h1>
    <!--
        <h1> - HTML tag pro nadpis první úrovně. 
        Tento tag je určen pro hlavní nadpis stránky, který by měl být unikátní.
    -->

    <p>Pojďte stavět vaší budoucnost u nás na škole, kde propojujeme praxi se vzděláváním</p>
    <!--
        <p> - HTML tag pro odstavec textu.
        Tento tag se používá pro základní textový obsah na stránce.
    -->

    <div class="hero-buttons">
        <!--
            <div> - HTML kontejnerový tag pro skupinu elementů. 
            Tento <div> obsahuje tlačítka a má třídu "hero-buttons" pro specifické stylování.
        -->
        <a href="/about">Login</a>
        <!--
            <a> - HTML tag pro odkaz. 
            href - Atribut obsahující URL adresu, kam odkaz vede.
            Tento odkaz vede na stránku /about a text uvnitř je "Login".
        -->
        <a href="/" id="ghost">About</a>
        <!--
            Druhý odkaz se stejným HTML tagem <a>, tentokrát s id "ghost", což ho odlišuje pro stylování.
            ID je jedinečný identifikátor elementu na stránce.
        -->
    </div>
</section>

<style>
    /* 
        . - V CSS se tečka používá k selekci elementů podle jejich třídy.
        :global - Speciální selektor v Svelte pro aplikaci stylů na globální úrovni (na celou stránku).
    */
    
    /* 
        .hero - Selektor pro elementy s třídou "hero".
        Šířka sekce je nastavena na 100% šířky stránky a minimální výška na výšku okna (viewportu) minus 100px.
        max-width omezuje šířku na maximálně 1300px.
        Flexbox je použit pro vycentrování obsahu ve svislém i vodorovném směru.
    */
    .hero {
        width: 100%; /* Nastavuje šířku sekce na 100 % šířky okna. */
        min-height: calc(100vh - 100px); /* Výška sekce je minimálně rovna výšce okna mínus 100px. */
        max-width: 1300px; /* Maximální šířka sekce je omezena na 1300px. */
        display: flex; /* Použití Flexboxu pro uspořádání elementů. */
        flex-direction: column; /* Uspořádání elementů ve sloupci (svisle). */
        justify-content: center; /* Vertikální vycentrování obsahu. */
        align-items: center; /* Horizontální vycentrování obsahu. */
        text-align: center; /* Text uvnitř sekce je zarovnán na střed. */
    }

    /* 
        .hero img - Selektor pro obrázky uvnitř prvku s třídou "hero".
        Obrázek bude mít šířku 250px.
    */
    .hero img {
        width: 250px; /* Nastavení pevné šířky obrázku na 250 pixelů. */
    }

    /* 
        .hero-buttons - Selektor pro div s třídou "hero-buttons".
        Flexbox je zde použit pro uspořádání tlačítek vedle sebe, a gap určuje mezeru mezi nimi.
    */
    .hero-buttons {
        display: flex; /* Použití Flexboxu pro uspořádání tlačítek. */
        gap: 36px; /* Mezera 36px mezi tlačítky. */
    }

    /* 
        .hero-buttons a - Selektor pro všechny odkazy (<a>) uvnitř "hero-buttons".
        Nastavuje styl tlačítek, včetně jejich barvy, pozadí, velikosti, zarovnání a zaoblení rohů.
    */
    .hero-buttons a {
        color: white; /* Barva textu je bílá. */
        background-color: rgb(44, 158, 59); /* Zelená barva pozadí tlačítka. */
        text-decoration: none; /* Odstranění podtržení odkazu. */
        width: 150px; /* Pevná šířka tlačítka je 150px. */
        height: 50px; /* Pevná výška tlačítka je 50px. */
        display: flex; /* Flexbox pro snadné zarovnání obsahu uvnitř tlačítka. */
        justify-content: center; /* Horizontální vycentrování textu uvnitř tlačítka. */
        align-items: center; /* Vertikální vycentrování textu uvnitř tlačítka. */
        border-radius: 10px; /* Zaoblení rohů tlačítka na 10px. */
        font-weight: 500; /* Středně tučné písmo. */
        font-family: Arial, Helvetica, sans-serif; /* Font pro tlačítka. */
        transition: ease 0.5s; /* Přechod pro animaci při změně stylu (0.5 sekundy). */
    }

    /* 
        #ghost - Selektor pro element s ID "ghost" (jedinečný prvek).
        Tlačítko má černý text a rámeček, ale žádné pozadí.
    */
    #ghost {
        color: black; /* Černá barva textu. */
        background: none; /* Žádné pozadí tlačítka. */
        border: 1px solid black; /* Černý rámeček kolem tlačítka. */
        transition: ease 0.5s; /* Přechod při změně stylu (0.5 sekundy). */
    }

    /* 
        #ghost:hover - Selektor pro tlačítko s ID "ghost" při najetí myší (pseudo-třída :hover).
        Barva a pozadí tlačítka se změní při najetí myší.
    */
    #ghost:hover {
        color: white; /* Text se změní na bílý při najetí myší. */
        background: red; /* Pozadí tlačítka se změní na červené při najetí myší. */
        border: 1px solid rgba(0,0,0,0); /* Rámeček tlačítka zmizí (průhledný) při najetí myší. */
    }

    /* 
        .hero-buttons a:hover - Selektor pro všechny odkazy v hero-buttons při najetí myší.
        Pozadí tlačítek se změní na červené při najetí myší.
    */
    .hero-buttons a:hover {
        color: white; /* Text se změní na bílý. */
        background: red; /* Pozadí se změní na červené. */
    }

</style>
