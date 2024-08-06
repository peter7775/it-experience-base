Solution for PHP 7.3 and up:

```
foreach($array as $key => $element) {
    if ($key === array_key_first($array))
        echo 'FIRST ELEMENT!';

    if ($key === array_key_last($array))
        echo 'LAST ELEMENT!';
}
```

Solution for all PHP versions:

```
foreach($array as $key => $element) {
    reset($array);
    if ($key === key($array))
        echo 'FIRST ELEMENT!';

    end($array);
    if ($key === key($array))
        echo 'LAST ELEMENT!';
}
```
* * *
/ ***Rok Kralj*** - https://stackoverflow.com/questions/1070244/how-to-determine-the-first-and-last-iteration-in-a-foreach-loop