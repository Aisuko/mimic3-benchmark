
## First step

```bash
python -m mimic3benchmark.scripts.extract_subjects {PATH TO MIMIC-III CSVs} data/root/

Processing LABEVENTS table: 100%|█████████████████████████████████████████████████▉| 27854055/27854056 [03:08<00:00, 147397.87it/s]
Processing OUTPUTEVENTS table: 100%|█████████████████████████████████████████████████▉| 4349218/4349219 [00:47<00:00, 90796.22it/s]
```

## Second step

* Fix some issues (ICU stay ID is missing)
* Removes the events that have missing information
* Remove all suspicious rows

```bash
python -m mimic3benchmark.scripts.validate_events data/root/

Iterating over subjects: 100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████| 33798/33798 [25:32<00:00, 22.05it/s]
n_events: 253116833
empty_hadm: 5162703
no_hadm_in_stay: 32266173
no_icustay: 15735688
recovered: 15735688
could_not_recover: 0
icustay_missing_in_stays: 7115720
```

## Third step

In this step we will get data file with specific format

```bash
python -m mimic3benchmark.scripts.extract_episodes_from_subjects data/root/

Iterating over subjects: 100%|████████████████████████████████████████████████████████████████████████████████| 33802/33802 [1:18:08<00:00,  7.21it/s]
```

## Fourth step(Split the dataset)

```bash
python -m mimic3benchmark.scripts.split_train_and_test data/root/

```

## Fifth step

```bash
python -m mimic3benchmark.scripts.create_in_hospital_mortality data/root/ data/in-hospital-mortality/

Number of created samples: 17903
```