# REPL journal

Record REPL calls

## Usage

```r
repl_journal()
```

## Example

```r
> a <- 1
> Sys.sleep(2.3)
> stop("boom")
```

This writes to `.Rjournal`;

```plain
[2025-08-11T11:48:00.32] prompt: a <- 1
[2025-08-11T11:48:00.33] duration: 0.02 s; status: ok
[2025-08-11T11:48:12.01] prompt: Sys.sleep(2.3)
[2025-08-11T11:48:14.30] duration: 2.31 s; status: ok
[2025-08-11T11:49:01.01] prompt: stop("boom")
[2025-08-11T11:49:01.01] duration: 0.01 s; status: error
```
