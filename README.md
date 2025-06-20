# Linux System Logger Daemon

This is a lightweight Linux system logger daemon written in C++ that:
- Runs in the background as a daemon process
- Logs CPU and memory usage every few seconds
- Writes logs to rotating log files in `logs/`
- Handles UNIX signals (pause, resume, terminate)
- Designed for middleware learning and system-level development

## Project Status
  In Progress - Skeleton Created

## Planned 

1. Daemonization 
   - Runs in the background (detached from terminal)

2. Periodic system logging 
   - Logs CPU usage (%)
   - Logs Memory usage (%)
   - Logging interval configurable (default: x seconds)

3. Signal Control
   - 'SIGUSR1' : Pause logging
   - 'SIGUSR2' : Resume logging
   - 'SIGTERM' : Gracefully shutdown the daemon 

4. Log File Rotation
   - Each log file can store up to 1000 lines 
   - maintians a amximum of 5 log files: 'log1.txt' to 'log5.txt'
   - When rotating: old files renamed (log4 -> log5 -> log3 -> log4, etc.)

5. Log Format
   [Date Time]CPU:Data MEM:Data (Data in %)

6. Clean Shutdown 
   - On termination, writes final shutdown log
   - Deletes temp files or state files if any 

7. Extendable 
   - Code structure allows adding IPC via UNIX socket in future
   - Can add config file or CLI parser later 

   

