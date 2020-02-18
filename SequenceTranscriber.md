# SequenceTranscriber
Allows putting a sequence through the transcription process.

## Methods
### `getTemplate()`
Gets the complement of the DNA sequence
#### Parameters
| Parameter   | Type                 | Description |
|-------------|----------------------|-------------|
| `$sequence` | `\Biospect\Sequence` |             |
#### Returns
`\Biospect\Sequence`: A new instance of a Sequence object, with starting position preserved

---
### `transcribe()`
Transcribes the sequence into RNA nucleotides
#### Parameters
| Parameter   | Type                 | Description |
|-------------|----------------------|-------------|
| `$sequence` | `\Biospect\Sequence` |             |
#### Returns
`\Biospect\Sequence`: A new instance of a Sequence object, with starting position preserved


## Example
**Setup**:
```php
use Biospect\Sequence;
use Biospect\SequenceTranscriber;

$sequenceTranscriber = new SequenceTranscriber();
$sequence = new Sequence( 'AAATCG', 0 );
```

### `getTemplate()`
```php
var_dump(
	$sequenceTranscriber->getTemplate( $sequence )
);
```
```
Biospect\Sequence Object
(
    [sequence:Biospect\Sequence:private] => TTAGCT
    [position:Biospect\Sequence:private] => 0
)
```

---
### `transcribe()`
```php
var_dump(
	$sequenceTranscriber->transcribe( $sequence )
);
```
```
Biospect\Sequence Object
(
    [sequence:Biospect\Sequence:private] => AAUCGA
    [position:Biospect\Sequence:private] => 0
)
```
