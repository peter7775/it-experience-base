# awk

Awk je také často používaný program pro práci s textem. Syntaxe je následující:

`$ awk 'program' [soubor]`

Program je série pravidel, která mohou obsahovat vzor, akci nebo obojí. Akce je uzavřena do {}. Když je ve vstupu nalezen vzor, vykoná se příslušná akce. Tento příklad nám ze souboru resolv.conf zobrazí pouze řádky obsahující slovo nameserver:

`$ awk '/nameserver/ {print}' /etc/resolv.conf`

Následující příklad zobrazí jen druhý sloupec našeho souboru. Všimněte si, že chybí vzor, proto bude akce aplikována na všechny řádky souboru:

`$ awk '{print $2}' osklivy_soubor`

V předchozím příkladu samo awk poznalo, že jsou sloupce oddělené mezerou a správně zobrazilo druhý sloupec. V případě jiného oddělovače sloupců si také poradíme. Chceme třeba vědět, který uživatel používá jaký shell:

`$ cat /etc/passwd | awk -F: '{print $1 " " $7}'`
