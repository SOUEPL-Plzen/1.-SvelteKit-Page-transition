<script>
	import { fly } from 'svelte/transition'; // Importujeme fly pro lepší efekt při page transtion
	import { page } from '$app/stores'; // Importujeme store pro sledování aktuální stránky
	import Header from "../lib/components/Header.svelte"; // Importujeme componentu z lib, vytvřáříme jí a voláme vždy velkým písmenem
	
	const { children } = $props(); // Vytvoření reaktivní proměné childern
	// children - Podle nového svelte 5 vykreslujeme potopky pomocí children
	// ve staré syntaxi stačilo napsat <slot />
	// $ - vytváříme runu
	/*
		$props() - Props v Svelte jsou způsob, jak předat data z nadřazené komponenty
		do podřazené komponenty. V Svelte 5 se props získávají pomocí funkce $props(), 
		která vrací objekt všech předaných hodnot.
	*/

	/*
		Children props umožňuje dynamicky vkládat obsah nebo další
		komponenty do podřazené komponenty. Díky tomu může komponenta
		vykreslit cokoliv, co jí nadřazená komponenta předá, a zůstává flexibilní a opakovaně použitelná.
	*/

	/*
		Const - definice proměné neboli deklarujeme do proměné funkci
	*/

	// Definice proměné			Název proměné(tímto voláme arrow funkci)   = - Přiřazení hodnoty		Anonymní arrow funkce
		const 					startTransition 							= 							() => {
			// Tělo funkce

		// document - vyheledej v documentu (html)
		// body - vyhledej body - to je integrovaná funkce v js - odkazuje na tělo html
		// classList - zpřesňujicí příkaz, který hledá classy (třídy v elementu)
		// add - Přidej classu, protože predchozí ClassList informuje kam to přidá
		// Obsah závorek píšeme název class co přidáváme	
		document.body.classList.add('page-transitioning');
	};

	const endTransition = () => {

		// remove - odeber classu
		document.body.classList.remove('page-transitioning');
	};

</script>

<!-- Voláme componentu jako header celé stránce
	Syntaxe zápisu /> je kratší zápis

	můžete napsat taktéž párový tag <Header></Header>
-->
<Header />

<!-- S použitím $page pro sledování změn URL -->

<!-- key - Zajistí, že při změně hodnoty dojde k přechodu, což znamená, že starý obsah bude odebrán a nový přidán. -->
<!-- $page.url - Reaktivní proměnná obsahující aktuální URL stránky, její změna vyvolá animaci při přechodu stránek. -->

{#key $page.url}

	<!-- in:fly - Definuje vstupní animaci, která element přesune z levé strany o 200px. -->
	<!-- x: -200 - Určuje horizontální posunutí o 200px doleva během animace. -->
	<!-- duration: 300 - Definuje trvání animace v milisekundách, v tomto případě 300ms. -->
	<!-- delay: 300 - Nastavuje zpoždění před začátkem animace na 300ms. -->

	<!-- out:fly - Definuje výstupní animaci, která posune element doprava o 200px při opuštění obrazovky. -->
	<!-- x: 200 - Určuje horizontální posunutí o 200px doprava během animace. -->
	<!-- duration: 300 - Trvání výstupní animace je 300ms. -->

	<!-- onintrostart - Spouští funkci `startTransition` při zahájení vstupní animace, často pro správu stavu přechodu. -->
	<!-- startTransition - Funkce, která provádí akce potřebné při zahájení animace (např. úprava stavu nebo přepnutí komponenty). -->

	<!-- onintroend - Spouští funkci `endTransition` po skončení vstupní animace, může signalizovat, že přechod je hotov. -->
	<!-- endTransition - Funkce, která ukončuje stav přechodu, např. obnovení normálního stavu aplikace. -->

	<!-- onoutrostart - Spouští funkci `startTransition` při zahájení výstupní animace, např. resetování stavu komponenty. -->

	<!-- onoutroend - Spouští funkci `endTransition` po skončení výstupní animace, což ukončuje animaci přechodu. -->

	<main
		in:fly={{ x: -200, duration: 300, delay: 300 }}
		out:fly={{ x: 200, duration: 300 }}
		onintrostart={startTransition}
		onintroend={endTransition}
		onoutrostart={startTransition}
		onoutroend={endTransition}
	>
		{@render children()}
	</main>
{/key} <!-- Ukončení key -->


<style>

	/* :global ve svelte pro tyto globální html tagy, které nejsou v kodu tady v documentu musíme volat pomocí svelte funkce :global(nazev_elementu) */
	:global(body) {
		width: 100%; /* Nastaví šířku těla stránky na 100% dostupné šířky okna. */
		min-height: 100vh; /* Zaručuje, že tělo stránky bude mít minimální výšku rovnající se 100 % výšky okna (viewportu). */
		margin: 0; /* Odstraní veškeré výchozí odsazení kolem těla stránky. */
		padding: 0; /* Odstraní veškeré výchozí vnitřní odsazení těla stránky. */
		overflow: visible; /* Povolení viditelného přetečení, pokud obsah překročí výšku těla. */
		font-family: Arial, sans-serif; /* Nastaví výchozí font stránky na Arial, pokud není k dispozici, použije se jakýkoliv dostupný bezpatkový (sans-serif) font. */
	}

	main {
		min-height: 100vh; /* Zaručuje, že hlavní obsah zabere minimálně 100 % výšky okna. */
		width: 100%; /* Nastaví šířku hlavního obsahu na 100 % rodičovského kontejneru (těla stránky). */
		max-width: 1200px; /* Omezí maximální šířku hlavního obsahu na 1200 pixelů, takže se nebude rozšiřovat přes tuto hodnotu. */
		margin: auto; /* Vycentruje hlavní obsah horizontálně na stránce. */
		box-sizing: border-box; /* Zajistí, že při změně velikosti se do šířky a výšky prvku započítává také padding a ohraničení. */
	}


</style>
