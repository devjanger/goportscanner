# goportscanner

``` go
package main

import (
	"fmt"
	"portcanner/port"
)

func main() {
	fmt.Println("Port Scanner in go")

	open := port.ScanPort("tcp", "localhost", 80)
	fmt.Println("Port 80 open:", open)

	results := port.InitialScan("localhost")

	for _, result := range results {
		if result.State == "open" {
			fmt.Println("Port", result.Port, "is open")
		}
	}
}
```
