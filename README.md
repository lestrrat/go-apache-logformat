go-apache-logformat
===================

[![Build Status](https://travis-ci.org/lestrrat/go-apache-logformat.png?branch=master)](https://travis-ci.org/lestrrat/go-apache-logformat)

[![GoDoc](https://godoc.org/github.com/lestrrat/go-apache-logformat?status.svg)](https://godoc.org/github.com/lestrrat/go-apache-logformat)

[![Coverage Status](https://coveralls.io/repos/lestrrat/go-apache-logformat/badge.png?branch=topic%2Fgoveralls)](https://coveralls.io/r/lestrrat/go-apache-logformat?branch=topic%2Fgoveralls)

# WARNING

This repository has been moved to [github.com/lestrrat-go/apache-logformat](https://github.com/lestrrat-go/apache-logformat). This repository exists so that libraries pointing to this URL will keep functioning, but this repository will NOT be updated in the future. Please use the new import path.

# SYNOPSYS

```go
import (
  "net/http"
  "os"

  "github.com/lestrrat/go-apache-logformat"
)

func main() {
  var s http.ServeMux
  s.HandleFunc("/", handleIndex)
  s.HandleFunc("/foo", handleFoo)

  http.ListenAndServe(":8080", apachelog.CombinedLog.Wrap(s, os.Stderr))
}
```

# DESCRIPTION

This is a port of Perl5's [Apache::LogFormat::Compiler](https://metacpan.org/release/Apache-LogFormat-Compiler) to golang
