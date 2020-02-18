# ReadingFrame

## Methods
### `__construct()`
#### Parameters
| Parameter              | Type                                                 | Description |
|------------------------|------------------------------------------------------|-------------|
| `$geneticCodeSearcher` | `\Biospect\GeneticCodeSearcher` |             |

---
### `getReadingFrame()`
#### Parameters
| Parameter   | Type                 | Description |
|-------------|----------------------|-------------|
| `$sequence` | `\Biospect\Sequence` |             |
#### Returns
`array<string,string>`: An associative array of codons to their amino acid

---
### `getReadingFrameAsCodons()`
#### Parameters
| Parameter   | Type                 | Description |
|-------------|----------------------|-------------|
| `$sequence` | `\Biospect\Sequence` |             |
#### Returns
`array<string>`: An array of codons

---
### `getReadingFrameAsAminoAcids()`
#### Parameters
| Parameter   | Type                 | Description |
|-------------|----------------------|-------------|
| `$sequence` | `\Biospect\Sequence` |             |
#### Returns
`array<string>`: An array of amino acids


## Example
**Setup**:
```php
use Biospect\GeneticCodeSearcher;
use Biospect\ReadingFrame;
use Biospect\Sequence;

$readingFrame = new ReadingFrame( new GeneticCodeSearcher() );
$sequence = new Sequence( 'gcccatacgtattcccctgagagcgcatgccgactgctgacggggcctagctatcactatcgagcggtcgctttcgactctaatcgcataatccctttg', 0 );
```

### `getReadingFrame()`
```php
$readingFrame->getReadingFrame( $sequence );
```
```php
[
	[ 'GCC', 'Alanine' ],
	[ 'CAT', 'Histidine' ],
	[ 'ACG', 'Threonine' ],
	[ 'TAT', 'Tyrosine' ],
	[ 'TCC', 'Serine' ],
	[ 'CCT', 'Proline' ],
	[ 'GAG', 'Glutamic acid' ],
	[ 'AGC', 'Serine' ],
	[ 'GCA', 'Alanine' ],
	[ 'TGC', 'Cysteine' ],
	[ 'CGA', 'Arginine' ],
	[ 'CTG', 'Leucine' ],
	[ 'CTG', 'Leucine' ],
	[ 'ACG', 'Threonine' ],
	[ 'GGG', 'Glycine' ],
	[ 'CCT', 'Proline' ],
	[ 'AGC', 'Serine' ],
	[ 'TAT', 'Tyrosine' ],
	[ 'CAC', 'Histidine' ],
	[ 'TAT', 'Tyrosine' ],
	[ 'CGA', 'Arginine' ],
	[ 'GCG', 'Alanine' ],
	[ 'GTC', 'Valine' ],
	[ 'GCT', 'Alanine' ],
	[ 'TTC', 'Phenylalanine' ],
	[ 'GAC', 'Aspartic acid' ],
	[ 'TCT', 'Serine' ],
	[ 'AAT', 'Asparagine' ],
	[ 'CGC', 'Arginine' ],
	[ 'ATA', 'Isoleucine' ],
	[ 'ATC', 'Isoleucine' ],
	[ 'CCT', 'Proline' ],
	[ 'TTG', 'Leucine' ],
]
```

----
### `getReadingFrameAsCodons()`
```php
$readingFrame->getReadingFrameAsCodons( $sequence );
```
```php
[
	'GCC', 'CAT', 'ACG', 'TAT', 'TCC', 'CCT', 'GAG', 'AGC',
	'GCA', 'TGC', 'CGA', 'CTG', 'CTG', 'ACG', 'GGG', 'CCT',
	'AGC', 'TAT', 'CAC', 'TAT', 'CGA', 'GCG', 'GTC', 'GCT',
	'TTC', 'GAC', 'TCT', 'AAT', 'CGC', 'ATA', 'ATC', 'CCT', 'TTG',
]
```

----
### `getReadingFrameAsAminoAcids()`
```php
$readingFrame->getReadingFrameAsAminoAcids( $sequence );
```
```php
[
	'Alanine', 'Histidine', 'Threonine', 'Tyrosine', 'Serine', 'Proline', 'Glutamic acid', 'Serine',
	'Alanine', 'Cysteine', 'Arginine', 'Leucine', 'Leucine', 'Threonine', 'Glycine', 'Proline',
	'Serine', 'Tyrosine', 'Histidine', 'Tyrosine', 'Arginine', 'Alanine', 'Valine', 'Alanine',
	'Phenylalanine', 'Aspartic acid', 'Serine', 'Asparagine', 'Arginine', 'Isoleucine', 'Isoleucine', 'Proline', 'Leucine'
]
```
