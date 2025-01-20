# Maintain Efficient Process Utilization on Windows

This repository provides examples and PowerShell scripts to efficiently manage and terminate processes on Windows operating systems. It demonstrates the use of built-in tools like `Get-Process` and `taskkill` to monitor and manage processes.

## Example: Terminating a Specific Process

This example demonstrates how to:

1. Identify processes using `Get-Process`.
2. Terminate specific processes using `taskkill`.

### Steps

1. Use `Get-Process` to find the process by name.
2. Use the `taskkill` command with the `/F` flag to forcefully terminate the process.

#### Example Code

```powershell
# Identify a process by name
Get-Process -Name "totally_not_malicious"

# Output
# Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
# -------  ------    -----      -----     ------     --  -- -----------
#     196      13     5804       8708   1,206.03    584   0 totally_not_malicious

# Terminate the process
taskkill /F /PID 584

# Verify the process is terminated
Get-Process -Name "totally_not_malicious"

Use wildcard characters (*) to find processes with partial names:

powershell
Get-Process -Name "*razzle*"
Always confirm the process has been successfully terminated:

powershell
Get-Process -Name "process_name"



