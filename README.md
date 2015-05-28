# The Quine-McCluskey Algorithm in Haskell
Ported to Haskell from the Python [qm](http://pypi.python.org/pypi/qm) Package and the [improved qm](http://github.com/prekageo/optistate) (including Petrick's method) by George Prekas.

## Installation
### From GitHub

```bash
git clone https://github.com/martinfinke/qm
```

### From Hackage

```bash
cabal install qm
```

### Installing Dependencies

```bash
cabal install --only-dependencies --enable-tests
```

### Running the Tests

```bash
cabal test
```

## Usage
**Note:** When `show`ing terms, leading zeros are dropped. So `0-10` is shown as `-10`.

### Set of Primes
Finding the set of all primes:

```haskell
import Qm
let terms = Set.fromList $ map getTerm $ map fromString [
        "0010", "0101", "0110", "1011", "1100", "1110", "1111"
        ]
compute_primes terms -- fromList [-10, 101, -110, 1-11, 11-0, 111-]
```

### Minimum Cover
Find the minimum cover for a list of minterms:

```haskell
import Qm
let terms = map getTerm $ map fromString [
        "0010", "0101", "0110", "1011", "1100", "1110", "1111"
        ]
qm terms [] [] -- [-10,101,1-11,11-0]
```


## License
See [LICENSE](LICENSE) file.