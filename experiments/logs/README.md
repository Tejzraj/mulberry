# Raw Experimental Logs

This directory contains raw, unedited sensor logs, CSV telemetry captures, and trial data files.

## Guidelines
- Subdirectories must be organized by Experiment ID: `experiments/logs/EXP-[ID]/`
- File naming: `YYYYMMDD_HHMMSS_[TRIAL_NUM]_raw.csv`
- Never edit raw log files. Processed data should be saved separately with code scripts detailing all transformation and filtering steps.
- Large binary logs (> 50 MB) should be referenced via metadata descriptors and archived in external cloud/LFS storage.
