# CCS 3209 — Week 1 Simulation Lab

A small discrete-event simulation of students arriving at a single service desk. Students are served in first-in, first-out (FIFO) order by one officer.

## Files

- `sim_original.py` — the baseline scenario from the lab sheet.
- `sim_modified.py` — a what-if scenario with longer service times.
- `CCS_3209_Week_1_Three_Hour_Laboratory_Work.docx` — the lab instructions and manual calculations.

## Run

Python 3 is the only requirement:

```bash
python3 sim_original.py
python3 sim_modified.py
```

Each script prints the arrival time, service start, completion time, waiting time, and total time in the system for every student, followed by summary measures.

## Model

For each student *i*:

```text
start(i)      = max(arrival(i), completion(i - 1))
completion(i) = start(i) + service(i)
wait(i)       = start(i) - arrival(i)
```

The model assumes one officer, no interruptions, and a FIFO queue.

## Scenario comparison

| Measure | Baseline | Longer service times |
| --- | ---: | ---: |
| Average waiting time | 4.375 min | 7.875 min |
| Maximum waiting time | 7 min | 13 min |
| Average time in system | 7.75 min | 12.25 min |
| Students who waited | 7 of 8 | 7 of 8 |

The modified case illustrates how longer service times increase congestion even when the arrival pattern stays the same.
