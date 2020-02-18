# SequenceSearcher
Allows checking if, where, and what codon/amino acid exists in a given sequence.

## Methods
### `__construct()`
#### Parameters
| Parameter       | Type                     | Description |
|-----------------|--------------------------|-------------|
| `$readingFrame` | `\Biospect\ReadingFrame` |             |

----
### `isCodonInSequence()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$codon`     | `string`             |             |
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`bool`: Whether or not the given codon exists in the sequence

----
### `isAminoAcidInSequence()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$aminoAcid` | `string`             |             |
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`bool`: Whether or not the given amino acid exists in the sequence

----
### `getNucleotideLength()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`int`: The total amount of nucleotides in the sequence

----
### `getCodonLength()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`int`: The total amount of codons in the sequence

---
### `getCodonCount()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`array<string,int>`: Associative array of codons to integers, where the integers represent how many times that codon has occured in the sequence

----
### `getAminoAcidCount()`
#### Parameters
| Parameter   | Type                 | Description |
|-------------|----------------------|-------------|
| `$sequence` | `\Biospect\Sequence` |             |
#### Returns
`array<string,int>`: Associative array of amino acids to integers, where the integers represent how many times that amino acid has occured in the sequence

---
### `getPositionsOfCodonInSequence()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$codon`     | `string`             |             |
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`array<int>`: An array of integers, where each integer represents the numerical index/position of the given codon's existence in the sequence

----
### `getPositionsOfAminoAcidInSequence()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$aminoAcid` | `string`             |             |
| `$sequence`  | `\Biospect\Sequence` |             |
#### Returns
`array<int>`: An array of integers, where each integer represents the numerical index/position of the given amino acid's existence in the sequence


## Example
**Setup**:
```php
use Biospect\GeneticCodeSearcher;
use Biospect\ReadingFrame;
use Biospect\Sequence;
use Biospect\SequenceAnalyzer;

$sequenceAnalyzer = new SequenceAnalyzer( new ReadingFrame( new GeneticCodeSearcher() ) );
$sequence = new Sequence( 'gcccatacgtattcccctgagagcgcatgccgactgctgacggggcctagctatcactatcgagcggtcgctttcgactctaatcgcataatccctttg', 0 );
```

### `isCodonInSequence()`
```php
$sequenceAnalyzer->isCodonInSequence( 'GCC', $sequence );
```
```
bool(true)
```

----
### `isAminoAcidInSequence()`
```php
$sequenceAnalyzer->isAminoAcidInSequence( 'Alanine', $sequence );
```
```
bool(true)
```

----
### `getNucleotideLength()`
```php
$sequenceAnalyzer->getNucleotideLength( $sequence );
```
```
99
```

----
### `getCodonLength()`
```php
$sequenceAnalyzer->getCodonLength( $sequence );
```
```
33
```

----
### `getCodonCount()`
```php
$sequenceAnalyzer->getCodonCount( $sequence );
```
```php
[
	'GCC' => 1,
	'CAT' => 1,
	'ACG' => 2,
	'TAT' => 3,
	'TCC' => 1,
	'CCT' => 3,
	'GAG' => 1,
	'AGC' => 2,
	'GCA' => 1,
	'TGC' => 1,
	'CGA' => 2,
	'CTG' => 2,
	'GGG' => 1,
	'CAC' => 1,
	'GCG' => 1,
	'GTC' => 1,
	'GCT' => 1,
	'TTC' => 1,
	'GAC' => 1,
	'TCT' => 1,
	'AAT' => 1,
	'CGC' => 1,
	'ATA' => 1,
	'ATC' => 1,
	'TTG' => 1,
]
```

----
### `getAminoAcidCount()`
```php
$sequenceAnalyzer->getAminoAcidCount( $sequence );
```
```php
[
	'Alanine' => 4,
	'Histidine' => 2,
	'Threonine' => 2,
	'Tyrosine' => 3,
	'Serine' => 4,
	'Proline' => 3,
	'Glutamic acid' => 1,
	'Cysteine' => 1,
	'Arginine' => 3,
	'Leucine' => 3,
	'Glycine' => 1,
	'Valine' => 1,
	'Phenylalanine' => 1,
	'Aspartic acid' => 1,
	'Asparagine' => 1,
	'Isoleucine' => 2,
]
```

----
### `getPositionsOfCodonInSequence()`
```php
$sequenceAnalyzer->getPositionsOfCodonInSequence( 'TTG', $sequence );
```
```php
[ 32 ]
```

----
### `getPositionsOfAminoAcidInSequence()`
```php
$sequenceAnalyzer->getPositionsOfAminoAcidInSequence( 'Alanine', $sequence );
```
```php
[ 0, 8, 21, 23 ]
```