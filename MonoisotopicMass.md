# MonoisotopicMass
Allows calculating the monoisotopic mass of proteins.

## Methods
### `getMassOfAminoAcid()`
Given the 1-letter IUPAC code of an amino acid, return the (monoisotpic) mass of that amino acid.
#### Parameters
| Parameter    | Type     | Description                       |
|--------------|----------|-----------------------------------|
| `$aminoAcid` | `string` | 1-letter IUPAC code of amino acid |
#### Returns
`float`: Monoisotopic mass of amino acid in daltons

----
### `getMassOfProtein()`
Given a sequence of amino acids by their 1-letter IUPAC code, return the (monoisotopic) mass of the protein.
#### Parameters
| Parameter  | Type     | Description                                     |
|------------|----------|-------------------------------------------------|
| `$protein` | `string` | A series of 1-letter IUPAC codes of amino acids |
#### Returns
`float`: Monoisotopic mass of the protein in daltons


## Example
**Setup**:
```php
use Biospect\MonoisotopicMass;
$monoisoMass = new MonoisotopicMass();
```

### `getMassOfAminoAcid()`
```php
// Mass of Glutamine, Q for short
$monoisoMass->getMassOfAminoAcid( 'Q' ); // 128.05858
```

----
### `getMassOfProtein()`
```php
$monoisoMass->getMassOfProtein( 'SKADYEK' ); // 821.39192
```
