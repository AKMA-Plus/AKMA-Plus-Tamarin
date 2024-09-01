# 5G AKMA-PLUS

## build Dependencies

* OS: Ubuntu 20.04 LTS.
* [tamarin-prover 1.8.0](https://tamarin-prover.com/)


## prove manually
run tamarin
```sh
tamarin-prover interactive AKMA_plus.spthy --derivcheck-timeout=100 --quit-on-warning --auto-sources
```
You can see 

>Finished loading theories ... server ready at 
>
>    http://127.0.0.1:3001

Point your browser to http://localhost:3001, you can start to prove lemma.

## auto prove
You can replace *** with a specific lemma
```sh
tamarin-prover AKMA_plus.spthy --derivcheck-timeout=100 --quit-on-warning --auto-sources --prove=***
```