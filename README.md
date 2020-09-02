# gorm-logrus

```go
package main

import (
  "gorm.io/gorm"
  "gorm.io/driver/sqlite"
  "github.com/onrik/gorm-logrus"
)

type Product struct {
  gorm.Model
  Code  string
  Price uint
}

func main() {
  db, err := gorm.Open(sqlite.Open("test.db"), &gorm.Config{
	  Logger: gorm_logrus.New(),
  })
  if err != nil {
    panic("failed to connect database")
  }
}
```