# GeneticCodeRandomizer
Generates a random codon/amino acid using the core \array_rand function, which internally uses the Mersenne Twister algorithm as of PHP 7.1+.

## Methods
### `__construct()`
#### Parameters
| Parameter              | Type                            | Description |
|------------------------|---------------------------------|-------------|
| `$geneticCodeSearcher` | `\Biospect\GeneticCodeSearcher` |             |

----
### `getRandomCodon()`
Returns a random codon out of all possible codons.

#### Returns
`string`: A random codon

----
### `getRandomNonStopCodon()`
Returns a random codon out of all non-stop codons.

#### Returns
`string`: A random non-stop codon

----
### `getRandomStopCodon()`
Returns a random codon out of all stop codons.

### Returns
`string`: A random stop codon

----
### `getRandomAminoAcid()`
Returns a random amino acid out of all possible amino acids.

#### Returns
`string`: A random amino acid

----
### `getRandomCodonByAminoAcid()`
Returns a random codon of a given amino acid.

#### Parameters
| Parameter    | Type     | Description |
|--------------|----------|-------------|
| `$aminoAcid` | `string` |             |
#### Returns
`string`: A random codon

## Example
> **Note**: The results shown are example results - the actual given result will not always be the same.

**Setup**:
```php
use Biospect\GeneticCodeSearcher;
use Biospect\GeneticCodeRandomizer;

$GeneticCodeRandomizer = new GeneticCodeRandomizer(
	new GeneticCodeSearcher()
);
```

### `getRandomCodon()`
```php
$GeneticCodeRandomizer->getRandomCodon(); // 'CAG'
```

----
### `getRandomNonStopCodon()`
```php
$GeneticCodeRandomizer->getRandomNonStopCodon(); // 'TGT'
```

### `getRandomStopCodon()`
```php
$GeneticCodeRandomizer->getRandomStopCodon(); // 'TAA'
```

---
### `getRandomAminoAcid()`
```php
$GeneticCodeRandomizer->getRandomAminoAcid(); // 'Arginine'
```

----
### `getRandomCodonByAminoAcid()`
```php
$GeneticCodeRandomizer->getRandomCodonByAminoAcid( `Proline` ); // 'CCG`
```
