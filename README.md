# `OffensiveYARA`

> battle-tested `YARA` detection rules for real-world `backdoors`, `RATs`, `ransomware`, `infostealers`, `exploits` and friends.

This tree is a fork of [`ReversingLabs/reversinglabs-yara-rules`](https://github.com/reversinglabs/reversinglabs-yara-rules) — production-grade detection rules written by ReversingLabs threat analysts, rebased current here. Kept for people who live on both sides of the glass: `red teams` use them to see what defenders actually match on, `blue teams` deploy them to catch the tradecraft.

## `what-you-get`

- `300+` rules across `10` categories: `backdoor`, `certificate`, `downloader`, `exploit`, `infostealer`, `pua`, `ransomware`, `rootkit`, `trojan`, `virus`
- precision-first design: unique byte patterns over lazy strings, readable transparent conditions
- tested upstream in ReversingLabs' cloud on `10B+` unique binaries, tuned for near-zero false positives

## `usage`

```bash
# compile the whole pack into one index
cat yara/*/*.yara > all.yarac 2>/dev/null

# scan a directory (recursive)
yara -r all.yarac /path/to/samples/

# single rule, single file
yara yara/ransomware/ByteCode.MSIL.Ransomware.Thanos.yara suspect.bin
```

## `prerequisites`

- `YARA` `>= 3.2.0` (standalone binary from [`VirusTotal/yara`](https://github.com/VirusTotal/yara) works)
- `PE` and `ELF` modules enabled

## `origins`

- rules: [`ReversingLabs`](https://github.com/reversinglabs/reversinglabs-yara-rules) threat analysts — every rule ships their `author`/`source` metadata intact, `MIT` licence kept verbatim
- fork packaging, README and rebase: `Foxcorn Lab`

## `Thanks to`

- `ReversingLabs` threat analysts for publishing and maintaining the rule set
- the `YARA` engine folks and the wider `YARA` community for keeping detection engineering sharp

## `disclaimer`

Detection signatures for research, threat hunting and defensive use only. Knowing a rule exists does not make you undetectable, and these rules alone will not secure your environment — layer your defences.

> Research by `Vineeth Kumar` (`foxcornlab`). Found a bug or want a feature, open an `issue`.
