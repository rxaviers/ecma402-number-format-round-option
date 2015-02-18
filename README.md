# NumberFormat round option

## Proposal for stage 0

Allows to select a rounding function for NumberFormat different than round
"half-even". For example: ceil, floor, or truncate.

Such option is present on Unicode Technical Standard #35, part 3 Numbers, which
says "An implementation may allow the specification of a rounding mode to
determine how values are rounded".

http://www.unicode.org/reports/tr35/tr35-numbers.html#Roundingo

## Usage

```javascript
let formatUsingHalfEvenRounding = new Intl.NumberFormat("en").format(Math.PI);
// "3.142"

let formatUsingFloorRounding = new Intl.NumberFormat("en", {round: "floor"}).format(Math.PI);
// "3.141"

let formatCurrencyUsingCeilRounding = new Intl.NumberFormat("en", {
  style: "currency",
  currency: "USD",
  currencyDisplay: "symbol",
  round: "ceil"
}).format(9.991);
// "$10.00"
```
