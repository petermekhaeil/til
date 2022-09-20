# Today I Learned: PHP

I had the opportunity to work on some PHP this week and picked up a few new tricks that are very different from JavaScript:

## Computing the difference in arrays

```php
$array1 = array("a" => "green", "red", "blue", "red");
$array2 = array("b" => "green", "yellow", "red");

$result = array_diff($array1, $array2);
```

## Computing the intersection of arrays

```php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");

$result = array_intersect($array1, $array2);
```

## Inherit a variable inside an anonymous function

```php
$message = 'world';
$example = function () use ($message) {
    return "hello $message";
};
```

## Reference a private function as a callback

```php
class MyClass {

    public static function getDifference() {
        $array1 = array("a" => "green", "red", "blue");
        $array2 = array("b" => "green", "yellow", "red");

        $result = array_udiff($array1, $array2, array($this, 'filterById'));    
    }

    private function filterById($a, $b) {}
}
```

## Reference static members of a class using `self`

```php
class MyClass {
    public static $url = "https://petermekhaeil.com/";

    public static function getUrl() {
        return self::$url;
    }
}
```
