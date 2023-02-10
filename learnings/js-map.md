# JavaScript Map

A much cleaner and performant alternative to objects.

```tsx
const myPokemons = new Map();

const bulbasaur = { id: 1, name: "Bulbasaur" };

myPokemons.set(bulbasaur.id, bulbasaur);
myPokemons.delete(bulbasaur.id);
```

## Iterating

```tsx
for (const [key, value] of myPokemons) {
  ...
}
```

- Cleaner to iterate compared to objects.
- Iterates in the order of entry insertion.

## Iterators 

```tsx
// Iterator of all map keys
myPokemons.keys();

// Iterator of all map values
myPokemons.values();
```

## Cloning

```tsx
const clonedPokemons = new Map(myPokemons);

// deep cloning
const deepClone = structuredClone(myPokemons)
```

## Converting to objects

```tsx
const myObj = Object.fromEntries(myMap);
```

## Converting to Map

```tsx
const myMap = new Map(Object.entries(myObj))
```

## Use any type of object as keys

```tsx
myMap.set(document.body, value)
myMap.set(function() {}, value)
myMap.set(myPokemon, value)
```
