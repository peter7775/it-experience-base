Here is example use of using a callable as a parameter.

The wait_do_linebreak function below will sleep for a given time, then call a function with the tailing parameters given, and then echo a line break.

`...$params` packs the tailing parameters into an array called $params. Here it's being used to proxy arguments into the callables.

At the end of the examples you'll see a native function that takes a callable as a parameter.


```
<?php

function wait_do_linebreak($time, callable $something, ...$params)
{
    sleep($time);
    call_user_func_array($something, $params);
    echo "\n";
}

function earth_greeting() {
    echo 'hello earth';
}

class Echo_Two
{
    public function __invoke($baz, $bat)
    {
        echo $baz, " ", $bat;
    }
}

class Eat_Static
{
    static function another()
    {
        echo 'Another example.';
    }
}

class Foo
{
    public function more()
    {
        echo 'And here is another one.';
    }
}

wait_do_linebreak(0, 'earth_greeting');
$my_echo = function($str) {
    echo $str;
};
wait_do_linebreak(0, $my_echo, 'hello');
wait_do_linebreak(0, function() {
    echo "I'm on top of the world.";
});
wait_do_linebreak(0, new Echo_Two, 'The', 'Earth');
wait_do_linebreak(0, ['Eat_Static', 'another']);
wait_do_linebreak(0, [new Foo, 'more']);

$array = [
    'jim',
    'bones',
    'spock'
];

$word_contains_o = function (string $str) {
    return strpos($str, 'o') !== false;
};
print_r(array_filter($array, $word_contains_o));
```

**Output**:

hello earth
hello
I'm on top of the world.
The Earth
Another example.
And here is another one.
Array
(
    [1] => bones
    [2] => spock
)
