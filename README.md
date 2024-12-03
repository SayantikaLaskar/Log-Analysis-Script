# Log Analysis Script

This Python script processes server log files to identify patterns of user activity, including the number of requests per IP address, the most frequently accessed endpoints, and suspicious activities based on failed login attempts. The analysis results are displayed on the terminal and saved to a CSV file for further review.

## Features

- **Request Count per IP Address**: Counts and displays the total number of requests made by each IP address.
- **Most Frequently Accessed Endpoint**: Identifies the endpoint that has been accessed the most times.
- **Suspicious Activity Detection**: Detects IP addresses that exceed a specified threshold for failed login attempts (e.g., status code `401`), flagging potential security threats.
- **CSV Export**: All results are saved in a CSV file (`log_analysis_results.csv`), which includes request counts, most accessed endpoints, and failed login attempts.

## Requirements

- Python 3.x
- No external libraries required (standard Python libraries used)

## Usage

1. Place the server log file (e.g., `sample.log`) in the same directory as the script.
2. Update the `log_file_path` variable in the `main()` function if your log file is located elsewhere.
3. Run the script using the following command:

   ```bash
   python log_analysis.py
   ```

4. The results will be printed to the terminal and saved to `log_analysis_results.csv`.

## Output

### Terminal Output Example

```plaintext
IP Address           Request Count
203.0.113.5          8
198.51.100.23        8
192.168.1.1          7
10.0.0.2             6
192.168.1.100        5

Most Frequently Accessed Endpoint:
/login                          (Accessed 13 times)

Suspicious Activity Detected:
No suspicious activity detected
```

### CSV Output Example

The script generates the following CSV file (`log_analysis_results.csv`):

```csv
IP Address,Request Count
203.0.113.5,8
198.51.100.23,8
192.168.1.1,7
10.0.0.2,6
192.168.1.100,5
Endpoint,Access Count
/login,13
IP Address,Failed Login Count
203.0.113.5,15
```

## Configuration

- **FAILED_LOGIN_THRESHOLD**: This constant defines the number of failed login attempts required to flag an IP address as suspicious. You can adjust this threshold to suit your needs.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
