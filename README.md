# Price-Calculator

A tiny Go program that calculates tax-included prices for a set of input prices and tax rates. This repository is intended as a small, self-contained example to illustrate basic Go usage with slices and maps.

## Features

- Compute tax-included prices for multiple tax rates
- Keep results in a map keyed by tax rate (map[float64][]float64)
- Zero external dependencies — uses only the Go standard library

## Prerequisites

- Go 1.18 or later installed and available in your PATH

## Quick Start

Clone the repository:

```bash
git clone https://github.com/tanset/Price-Calculator.git
cd Price-Calculator
```

If this repository does not include a `go.mod` yet, initialize it (use the repository import path):

```bash
go mod init github.com/tanset/Price-Calculator
go mod tidy
```

Build and run:

```bash
go build -o bin/price-calculator
./bin/price-calculator
```

Or run directly with `go run`:

```bash
go run main.go
```

## Example output

The program prints a map whose keys are tax rates and values are slices of tax-included prices. Example:

```
map[0:[10 20 30] 0.07:[10.7 21.4 32.1] 0.1:[11 22 33] 0.15:[11.5 23 34.5]]
```

## Code notes

- The main logic is in `main.go`. It demonstrates:

  - Creating and initializing a map with `make(map[float64][]float64)`
  - Allocating slices with `make([]float64, len(prices))` and filling them by index

- If you plan to change how results are accumulated, consider using `make([]float64, 0, len(prices))` + `append` when variable-length construction is desired.

## Project structure

```
go.mod (optional)
main.go
README.md
```
