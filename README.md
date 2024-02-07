# EME Widevine Tamarin Models

Dependency:
- `tamarin 1.8.0`


## Model WithoutKCB 
### Goal 1
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal1
```
processing time: 8.87s
--> all the lemmas are verified by Tamarin

### Goals 2, 3, and 4
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoalInitialPart
```
processing time: 9.19s
--> all the lemmas are verified by Tamarin

### Goals 5, 7, and 8 (extra goal)
```
tamarin-prover --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal578
```
processing time: 11.69s
--> none of these goals hold.
    The attack on goal 5 is stored in the file, and replayed when running the command.
    That same attack invalidates goals 7 and the extra goal 8, the corresponding lemmas are still present in the file but are unprovable.

### Goal 6
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal6
```
processing time: 27.13s
--> all the lemmas are verified by Tamarin

### Executability
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' --stop-on-trace=seqdfs widevine.spthy -DExecutability
```
processing time: 30.53s
--> all the lemmas are verified by Tamarin



## Model WithKCB 

### Goal 1
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal1
```
processing time: 9.93s
--> all the lemmas are verified by Tamarin

### Goals 2, 3, and 4
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoalInitialPart
```
processing time: 10.40s
--> all the lemmas are verified by Tamarin

### Goals 5, 7, and 8 (extra goal)
```
tamarin-prover --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal578
```
processing time: 25.65s
--> none of these goals hold.
    The attack on goal 5 is stored in the file, and replayed when running the command.
    That same attack invalidates goals 7 and 8, the corresponding lemmas are still present in the file but are unprovable.

### Goal 6
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal6
```
processing time: 71.59s
--> all the lemmas are verified by Tamarin

### Executability
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' --stop-on-trace=seqdfs widevine.spthy -DExecutability
```
processing time: 31.90s
--> all the lemmas are verified by Tamarin

## Model FixWithKCB

### Goal 1
```
tamarin-prover --prove --derivcheck-timeout=0  --heuristic=O --oraclename='widevine.oracle'   widevine.spthy -DSecrecy -DGoal1
```
processing time: 10.89s
--> all the lemmas are verified by Tamarin

### Goal 2, 3, and 4
```
tamarin-prover --prove --derivcheck-timeout=0  --heuristic=O --oraclename='widevine.oracle'   widevine.spthy -DSecrecy -DGoalInitialPart
```
processing time: 14.33s
--> all the lemmas are verified by Tamarin

### Goal 5, 6, 7, and 8 (extra Goal) 
```
tamarin-prover --prove --derivcheck-timeout=0  --heuristic=O --oraclename='widevine.oracle'   widevine.spthy -DSecrecy -DGoalRenewalPart
```
processing time: 178.97s
--> all the lemmas are verified by Tamarin using LoadUnique as a restriction

### Executability
```
tamarin-prover --prove --derivcheck-timeout=0  --heuristic=O --oraclename='widevine.oracle'    --stop-on-trace=seqdfs widevine.spthy -DExecutability
```
processing time: 37.27s
--> All the lemma are verified by Tamarin


## Model FixWithoutKCB 

### Goal 1
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoal1
```
processing time: 11.61s
--> all the lemmas are verified by Tamarin

### Goals 2, 3, and 4
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoalInitialPart
```
processing time: 13.28s
--> all the lemmas are verified by Tamarin

### Goals 5, 6, 7, and 8 (extra goal)
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' widevine.spthy -DSecrecy -DGoalRenewalPart
```
processing time: 69.84s
--> all the lemmas are verified by Tamarin (LoadUnique is a lemma
established relying on the restriction GenerateRequestUniquePerSession
as defined in the standard)

### Executability
```
tamarin-prover --prove --derivcheck-timeout=0 --heuristic=O --oraclename='widevine.oracle' --stop-on-trace=seqdfs widevine.spthy -DExecutability
```
processing time: 28.71s
--> all the lemmas are verified by Tamarin
