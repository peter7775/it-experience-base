# sed

Podobně funguje program sed. Jedná se o neinteraktivní textový editor. Sed čte řádky ze standardního vstupu a vykonává s nimi zadané příkazy, výsledek pak zobrazuje na standardním výstupu. Sed dále podporuje regulární výrazy. Několik příkladů. Toto nám zamění slova v zadaném textu:

`$ echo "maly priklad" | sed 's/maly/VELKY/'`
VELKY priklad

Pro náhradu řetězce v celém souboru stačí zadat:

`$ sed 's/retezec1/retezec2/g' soubor > soubor2`

Při použití regulárních výrazů získáváme mocného pomocníka. Toto nám odstraní všechny komentáře v souboru (začínají znakem #) a zároveň odstraní prázdné řádky:

`$ sed '/^#/d; /^ *$/d'  /cesta/k/souboru`

Ještě jedna praktická ukázka využití sedu. Chceme zkopírovat část souboru, konce dat, které nás zajímají, jsou určené nějakým výrazem:

`$ sed '/koncovy_retezec/q' /etc/rc.conf`
