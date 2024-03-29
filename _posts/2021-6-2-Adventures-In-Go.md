# Adventures In Go 
I think it would be wise for me to get a better handle on the go programming language.  I've used it somewhat in the past, but that use was mostly small code changes to an existing application.  A deeper dive would probably benefit me!  The way I like to learn a new programming language is through small bite-sized experiments, and the official go website allows us to experiment with go without even having to install anything on our system!  I'll be taking the tour route: https://tour.golang.org/  
Here's our first program:
```go
package main

import "fmt"

func main() {
	fmt.Println("Hello, world!")
}
```
And here's the output:
```
Hello, world!
```
So, we've defined that as soon as the program starts, it's to print `Hello, world!` and then exits.  One thing I notice right off the bat is that go is a little less verbose than some other server side languages such as Java or C/C++.  That's very nice and plus in my book!
### Packages
The first thing after the hello world program that we're introduced to is the concept of a package.
```go
package main

import (
	"fmt"
	"math/rand"
)

func main() {
	fmt.Println("My favorite number is", rand.Intn(10))
}
```
As you can see, we've imported two packages, `fmt` and `math/rand`.  `fmt` has functions for printing to the console--among other things-- and `math/rand` has a `Intn` function that can be use to generate a random integer.  
OUTPUT
```
My favorite number is 1
```
Now we get introduced to factored import statements.  We could write our code like this:
```go
package main

import "fmt"
import "math"

func main() {
	fmt.Printf("Now you have %g problems.\n", math.Sqrt(7))
}
```
But, we could make our code more concise by using a "factored" import statement, which looks like this:
```go
package main

import 
(
	"fmt"
	"math"
)

func main() {
	fmt.Printf("Now you have %g problems.\n", math.Sqrt(7))
}
```
### Exported Names
