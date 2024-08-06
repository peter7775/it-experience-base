Operátor yield dovoluje vytvářet generátory – funkce generující hodnoty, které můžeme používat v kódu, ze kterého generátor voláme. Klasickou ukázkou použití generátorů je funkce xrange(). Ta stejně jako vestavěná funkce range() vrací hodnoty z nějakého rozsahu, ale na rozdíl od této funkce to dělá průběžně – nepotřebuje výsledek uložit do paměti:

```
<?php
function xrange($start, $end, $step = 1) {
    for ($i = $start; $i <= $end; $i += $step) {
        yield $i;
    }
}

foreach (xrange(1, 5) as $i) {
    echo "$i\n";
}

// Po dobu 0.1 sekundy vypisuje čísla.
$start = microtime(true);
foreach (xrange(1, INF) as $i) {
    if (microtime(true) - $start > .1) {
        break;
    }
    echo "$i\n";
}
?>
```

Možnosti využití tohoto operátoru jsou mnohem bohatší. Řekněme, že chceme spustit sadu dlouhotrvajících testů a jejich výsledky vypisovat. Logiku pro provedení testu a vypsání jeho výsledku máme samozřejmě oddělenou. Nejjednodušší řešení je spustit všechny testy, výsledky si uložit do pole a to na konec projít a výsledky vypsat. Nevýhody jsou zřejmé – na první výsledek čekáme, až dokud nedoběhnou všechny testy, a potřebujeme paměť na uložení všech výsledků. S operátorem yield můžeme výsledky vracet a vypisovat průběžně. Samozřejmě to není jediné možné řešení – funkci pro výpis výsledků můžeme např. předat do spouštěče testů a volat ji z něj. Řešení s operátorem yield je ale elegantnější.

Operátor yield je také jedním z důležitých prvků pro výkon Facebooku. V zásadě všechny funkce, které potřebují nějaká data, před jejich získáním „yieldnou“. Všechny požadavky na data se sdruží, vyřídí najednou a rozdají zpátky funkcím. To dovoluje dramaticky snížit počet komunikací s úložištěm, který díky tomu závisí jen na počtu úrovní na sobě závislých požadavků, nikoliv na celkovém počtu míst, kde nějaká data potřebujeme. Facebook tento operátor používá už dlouhou dobu díky implementaci v kompilátoru HipHop for PHP.

Syntaxe je bohatší, z generátorů lze vracet i klíče a do generátoru můžeme zvenku poslat data, detaily naleznete v PHP manuálu nebo v RFC. Generátor lze detekovat metodou ReflectionFunctionAbstract::isGenerator.
* * *
(J. Vrána / https://zdrojak.cz/clanky/yield-a-dalsi-novinky-php-5-5/)