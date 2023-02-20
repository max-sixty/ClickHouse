---
slug: /en/sql-reference/functions/ulid-functions
sidebar_position: 54
sidebar_label: ULID
---

# Functions for Working with ULID

## generateULID

Generates the [ULID](https://github.com/ulid/spec).

**Syntax**

``` sql
generateULID([x])
```

**Arguments**

-   `x` — [Expression](../../sql-reference/syntax.md#syntax-expressions) resulting in any of the [supported data types](../../sql-reference/data-types/index.md#data_types). The resulting value is discarded, but the expression itself if used for bypassing [common subexpression elimination](../../sql-reference/functions/index.md#common-subexpression-elimination) if the function is called multiple times in one query. Optional parameter.

**Returned value**

The [FixedString](../data-types/fixedstring.md) type value.

**Usage example**

``` sql
SELECT generateULID()
```

``` text
┌─generateULID()─────────────┐
│ 01GNB2S2FGN2P93QPXDNB4EN2R │
└────────────────────────────┘
```

**Usage example if it is needed to generate multiple values in one row**

```sql
SELECT generateULID(1), generateULID(2)
```

``` text
┌─generateULID(1)────────────┬─generateULID(2)────────────┐
│ 01GNB2SGG4RHKVNT9ZGA4FFMNP │ 01GNB2SGG4V0HMQVH4VBVPSSRB │
└────────────────────────────┴────────────────────────────┘
```

## See Also

-   [UUID](../../sql-reference/functions/uuid-functions.md)