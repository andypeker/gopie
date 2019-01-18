

# bloom
`import "github.com/andy2046/gopie/pkg/bloom"`

* [Overview](#pkg-overview)
* [Index](#pkg-index)

## <a name="pkg-overview">Overview</a>
Package bloom implements a Bloom filter.




## <a name="pkg-index">Index</a>
* [func Guess(n uint64, p float64) (m, k uint64)](#Guess)
* [type Bloom](#Bloom)
  * [func New(m, k uint64) (bf Bloom)](#New)
  * [func NewGuess(n uint64, p float64) (bf Bloom)](#NewGuess)


#### <a name="pkg-files">Package files</a>
[bloom.go](/src/github.com/andy2046/gopie/pkg/bloom/bloom.go) [siphash.go](/src/github.com/andy2046/gopie/pkg/bloom/siphash.go) 





## <a name="Guess">func</a> [Guess](/src/target/bloom.go?s=1357:1402#L59)
``` go
func Guess(n uint64, p float64) (m, k uint64)
```
Guess estimates m/k based on the provided n/p.




## <a name="Bloom">type</a> [Bloom](/src/target/bloom.go?s=140:354#L10)
``` go
type Bloom interface {
    Add([]byte)
    AddString(string)
    Exist([]byte) bool
    ExistString(string) bool
    FalsePositive() float64
    GuessFalsePositive(uint64) float64
    M() uint64
    K() uint64
    N() uint64
    Clear()
}
```
Bloom represents the interface for bloom filter.







### <a name="New">func</a> [New](/src/target/bloom.go?s=825:857#L39)
``` go
func New(m, k uint64) (bf Bloom)
```
New creates bloom filter based on the provided m/k.
m is the size of bloom filter bits.
k is the number of hash functions.


### <a name="NewGuess">func</a> [NewGuess](/src/target/bloom.go?s=1217:1262#L53)
``` go
func NewGuess(n uint64, p float64) (bf Bloom)
```
NewGuess estimates m/k based on the provided n/p then creates bloom filter.
n is the estimated number of elements in the bloom filter.
p is the false positive probability.









- - -
Generated by [godoc2md](http://godoc.org/github.com/davecheney/godoc2md)