# FastaFileParser
Allows parsing a file in a FASTA format into machine-readable data, as an associative array
of unique identifiers to sequences.

## Methods
### `parseFromString()`
#### Parameters
| Parameter      | Type     | Description                        |
|----------------|----------|------------------------------------|
| `$fastaString` | `string` | Direct string of the FASTA content |
#### Returns
`array<string,string>`: Associative array of unique sequence identifiers to sequences

----
### `parseFromFileName()`
#### Parameters
| Parameter        | Type     | Description            |
|------------------|----------|------------------------|
| `$fastaFileName` | `string` | Path to the FASTA file |
#### Returns
`array<string,string>`: Associative array of unique sequence identifiers to sequences

----
### `parse()`
#### Parameters
| Parameter     | Type            | Description                         |
|---------------|-----------------|-------------------------------------|
| `$fastaLines` | `array<string>` | Array of lines of the FASTA content |
#### Returns
`array<string,string>`: Associative array of unique sequence identifiers to sequences


## Example
**Setup**:
```php
use Biospect\FastaFileParser;

$fastaFileParser = new FastaFileParser();
```

### `parseFromFileName()`
```php
$fastaFileParser->parseFromFileName( 'docs/data/fasta/sample-1.fasta' );
```
```php
[
	'seq0' => 'FQTWEEFSRAAEKLYLADPMKVRVVLKYRHVDGNLCIKVTDDLVCLVYRTDQAQDVKKIEKF',
	'seq1' => 'KYRTWEEFTRAAEKLYQADPMKVRVVLKYRHCDGNLCIKVTDDVVCLLYRTDQAQDVKKIEKFHSQLMRLMELKVTDNKECLKFKTDQAQEAKKMEKLNNIFFTLM',
	'seq2' => 'EEYQTWEEFARAAEKLYLTDPMKVRVVLKYRHCDGNLCMKVTDDAVCLQYKTDQAQDVKKVEKLHGK',
	'seq3' => 'MYQVWEEFSRAVEKLYLTDPMKVRVVLKYRHCDGNLCIKVTDNSVCLQYKTDQAQDVK',
	'seq4' => 'EEFSRAVEKLYLTDPMKVRVVLKYRHCDGNLCIKVTDNSVVSYEMRLFGVQKDNFALEHSLL',
	'seq5' => 'SWEEFAKAAEVLYLEDPMKCRMCTKYRHVDHKLVVKLTDNHTVLKYVTDMAQDVKKIEKLTTLLMR',
	'seq6' => 'FTNWEEFAKAAERLHSANPEKCRFVTKYNHTKGELVLKLTDDVVCLQYSTNQLQDVKKLEKLSSTLLRSI',
	'seq7' => 'SWEEFVERSVQLFRGDPNATRYVMKYRHCEGKLVLKVTDDRECLKFKTDQAQDAKKMEKLNNIFF',
	'seq8' => 'SWDEFVDRSVQLFRADPESTRYVMKYRHCDGKLVLKVTDNKECLKFKTDQAQEAKKMEKLNNIFFTLM',
	'seq9' => 'KNWEDFEIAAENMYMANPQNCRYTMKYVHSKGHILLKMSDNVKCVQYRAENMPDLKK',
	'seq10' => 'FDSWDEFVSKSVELFRNHPDTTRYVVKYRHCEGKLVLKVTDNHECLKFKTDQAQDAKKMEK'
]
```