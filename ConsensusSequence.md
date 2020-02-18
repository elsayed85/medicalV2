# ConsensusSequence
Allows finding the consensus sequence, or average DNA sequence, out of a series of given DNA sequences.

## Methods
### `find()`
#### Parameters
| Parameter    | Type            | Description                        |
|--------------|-----------------|------------------------------------|
| `$sequences` | `array<string>` | Array of DNA sequence strings      |
#### Returns
`string`: The average DNA sequence


## Example
**Setup**:
```php
use Biospect\ConsensusSequence;
$consensusSequence = new ConsensusSequence();
$sequences = [
	'ATCCAGCT',
	'GGGCAACT',
	'ATGGATCT',
	'AAGCAACC',
	'TTGGAACT',
	'ATGCCATT',
	'ATGGCACT',
];
```

### `find()`
```php
$consensusSequence->find( $sequences );
```
```
'ATGCAACT'
```
