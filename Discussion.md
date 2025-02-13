# Discussion

## Solutions Considered

### 1. **Line-by-Line Processing (Chosen Solution)**
- Reads the log file line by line, checking if the line starts with the given date.
- Memory efficient as it does not load the entire file into memory.
- Simple implementation and works well for large files.

### 2. **Indexing for Faster Retrieval**
- Preprocesses the log file to create an index mapping dates to file offsets.
- Allows quick retrieval of logs for a specific date without scanning the entire file.
- Requires extra storage for the index and an initial indexing step.

### 3. **Using External Databases**
- Stores logs in a structured database (e.g., SQLite, PostgreSQL).
- Enables efficient querying and filtering but adds complexity and storage overhead.
- Requires additional setup and maintenance.

## Final Solution Summary
We chose the **Line-by-Line Processing** approach because:
- It is **memory efficient**, avoiding excessive RAM usage even for large log files.
- It is **simple to implement and maintain** without requiring additional storage or indexing.
- It provides **acceptable performance** for sequential log retrieval.

## Steps to Run

1. **Ensure Python is Installed:**
   - Run `python --version` to check if Python 3.x is installed.

2. **Prepare the Log File:**
   - Place the `test_logs.log` file in the same directory as `extract_logs.py`.

3. **Run the Script:**
   ```sh
   python extract_logs.py YYYY-MM-DD
   ```
   Replace `YYYY-MM-DD` with the desired date.

4. **Check the Output:**
   - The extracted logs will be saved in the `output/` directory as `output_YYYY-MM-DD.txt`.

5. **Handling Errors:**
   - If the log file is missing, the script will print an error message.
   - Ensure the input date is formatted correctly (YYYY-MM-DD).

