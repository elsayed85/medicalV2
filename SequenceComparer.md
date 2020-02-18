# SequenceComparer

## Methods
### `areSequencesEqual()`
#### Parameters
| Parameter    | Type                 | Description |
|--------------|----------------------|-------------|
| `$sequenceA` | `\Biospect\Sequence` |             |
| `$sequenceB` | `\Biospect\Sequence` |             |
#### Returns
`bool`: Whether or not the sequences from their given starting positions are equal

### `doesSequenceHaveSubSequence()`
#### Parameters
| Parameter       | Type                 | Description |
|-----------------|----------------------|-------------|
| `$mainSequence` | `\Biospect\Sequence` |             |
| `$subSequence`  | `\Biospect\Sequence` |             |
#### Returns
`bool`: Whether or not the main sequence contains the given sub-sequence

## Example
**Setup**:
```php
use Biospect\Sequence;
use Biospect\SequenceComparer;

$sequenceComparer = new SequenceComparer();
```

### `areSequencesEqual()`
```php
$sequenceComparer->areSequencesEqual(
	new Sequence( 'gcccatacgtattcccctgagagcgcatgccgactgctgacggggcctagctatcactatcgagcggtcgctttcgactctaatcgcataatccctttg', 24 ),
	new Sequence( 'gcatgccgactgctgacggggcctagctatcactatcgagcggtcgctttcgactctaatcgcataatccctttg', 0 )
);
```
```
bool(true)
```

----
### `doesSequenceHaveSubSequence()`
```php
$sequenceComparer->doesSequenceHaveSubSequence(
	new Sequence( 'gcccatacgtattcccctgagagcgcatgccgactgctgacggggcctagctatcactatcgagcggtcgctttcgactctaatcgcataatccctttg', 0 ),
	new Sequence( 'gcccatacgtattcccct', 0 )
);
```
```
bool(true)
```
