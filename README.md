# gorm-logrus
Logrus logger for gorm v2

```go
package main

import (
  "github.com/sirupsen/logrus"
  "gorm.io/gorm"
  "gorm.io/driver/sqlite"
  "github.com/onrik/gorm-logrus"
)

func main() {
  db, err := gorm.Open(sqlite.Open("test.db"), &gorm.Config{
    Logger: gorm_logrus.New(logrus.StandardLogger()),
  })
  if err != nil {
    panic("failed to connect database")
  }
}
```

