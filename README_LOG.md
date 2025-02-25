
## Second step

* Fix some issues (ICU stay ID is missing)
* Removes the events that have missing information
* Remove all suspicious rows

```bash
Iterating over subjects: 100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████| 33798/33798 [25:32<00:00, 22.05it/s]
n_events: 253116833
empty_hadm: 5162703
no_hadm_in_stay: 32266173
no_icustay: 15735688
recovered: 15735688
could_not_recover: 0
icustay_missing_in_stays: 7115720
```