# Partner file record layout: `partner_fi.dat`

Northshore Credit Union, one of CBOJ's partner financial institutions, sends its transactions as a **fixed-width text file**, a common format for files exchanged with mainframe systems. There are no commas or delimiters: each field sits at a fixed position on the line, padded with spaces or zeros.

Every line is **78 characters** long and starts with a one-letter record type.

## Header record (first line, type `H`)

| Positions | Length | Field | Format |
| --- | --- | --- | --- |
| 1 | 1 | Record type | `H` |
| 2–9 | 8 | File date | `YYYYMMDD` |
| 10–15 | 6 | Partner code | Text |
| 16–45 | 30 | Partner name | Text, padded with spaces |
| 46–78 | 33 | Filler | Spaces |

## Detail record (one per transaction, type `D`)

| Positions | Length | Field | Format |
| --- | --- | --- | --- |
| 1 | 1 | Record type | `D` |
| 2–11 | 10 | Transaction ID | Text, padded with spaces |
| 12–25 | 14 | Timestamp | `YYYYMMDDHHMMSS` |
| 26–27 | 2 | Transaction type code | `PU` purchase · `WD` withdrawal · `DP` deposit · `TR` transfer |
| 28–35 | 8 | From account | Text, padded with spaces; blank if not applicable |
| 36–43 | 8 | To account | Text, padded with spaces; blank if not applicable |
| 44–54 | 11 | Amount | Digits only, zero-padded, **two implied decimal places** (`00000012550` = 125.50) |
| 55 | 1 | Amount sign | `+` or `-` |
| 56–58 | 3 | Currency | `CAD` |
| 59–78 | 20 | Description | Text, padded with spaces |

## Trailer record (last line, type `T`)

| Positions | Length | Field | Format |
| --- | --- | --- | --- |
| 1 | 1 | Record type | `T` |
| 2–10 | 9 | Detail record count | Zero-padded number |
| 11–25 | 15 | Control total | Sum of detail amounts, zero-padded, two implied decimals |
| 26 | 1 | Control total sign | `+` or `-` |
| 27–78 | 52 | Filler | Spaces |

Positions are 1-based, so the first character on a line is position 1.
