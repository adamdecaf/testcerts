# TestCerts: A Go package for creating temporary certificates for testing.

[![Build Status](https://travis-ci.org/madflojo/testcerts.svg?branch=master)](https://travis-ci.org/madflojo/testcerts) [![Go Report Card](https://goreportcard.com/badge/github.com/madflojo/testcerts)](https://goreportcard.com/report/github.com/madflojo/testcerts) [![Documentation](https://godoc.org/github.com/madflojo/testcerts?status.svg)](http://godoc.org/github.com/madflojo/testcerts)
[![license](https://img.shields.io/github/license/madflojo/testcerts.svg?maxAge=2592000)](https://github.com/madflojo/testcerts/LICENSE)

Package testcerts enables users to create temporary x509 Certificates for testing.

There are many Certificate generation tools out there, but most focus on being a CLI tool. This package is focused on providing helper functions for creating Certificates. These helper functions can be used as part of your unit and integration tests as per the example below.

```go
func TestSomething(t *testing.T) {
  err := testcerts.GenerateCertsToFile("/tmp/cert", "/tmp/key")
  if err != nil {
    // do stuff
  }

  _ = something.Run("/tmp/cert", "/tmp/key")
  // do more testing
}
```

The goal of this package, is to make testing TLS based services easier. Without having to leave the comfort of your editor, or place test certificates in your repo.
