# Project-3-LHLWorkflow
Workflow

I will develop a script that will save logs into a main file, and the script will also copy logs into a separate file, where it will count for any filtered status codes. The second file’s contents will be replaced when the script is ran with any new logs. The script will tally up any filtered codes, and if they reach the set threshold, it will proceed to send an email alerting staff/management to the anomaly. I will automate it using Cron, running it hourly, except for on Thursday, where the interval will be increased based on average traffic. Perhaps every 10-30 minutes or sooner. At the end of the week, I will collect any alerts sent out and compile them, analyse any patterns and include them in a weekly report.

Programming

Bash script used for purpose given 
“tail” command used to save recent logs
“grep -E” used to filter for error codes
Array used to simplify the counting commands by storing them in one variable.
For loop used to loop all filtered codes before continuing to next step
Mail command used to send alert email to staff
Cron used to automate script (* 1 * * * for not Thursday) and (*/10 * * * 4 for Thursday, as an example). Runs script hourly all days except Thursday, where intervals will be increased based on average traffic.
	
Expected Outcome

Logs will be stored in a master file of sorts. Important in case there is an issue and we need to look at the full logs.
Script will do counting of the status codes in a separate file and will replace the old logs when script runs again. Needed so that the script will alert staff and track any unusual traffic.
Script will count lines for repeat status codes within the last amount of logs it is set to check. Needed to generate alert emails.
Script will send an alert email if any count reaches a threshold. Necessary to mitigate any potential attack or damage.

Unusual Behaviour

High number of login failures in short timespan
Unusual access time
Same IP address generating logs in short period of time 
A user is trying to access abnormal places on web server
	
Potential iterations

Add to script to check for multiple instances of the same IP address. An attacker may generate different status codes, so the script might not catch them.
Rotate the master log file to store logs in a backup file. If the system fails or an attacker manages to get into our devices, a backup would add a level of security.
Add more status codes to monitor. Depending on developments in the cyber world, different status codes might indicate a different attack.
Make a script that would automate the weekly report. It would be beneficial for it to prepare the relevant logs and alerts to send to management.
