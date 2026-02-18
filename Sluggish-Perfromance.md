# Sluggish Performance

## What It Is
Sluggishness is caused by memory leaks, where apps don't release RAM after closing.

## Fix
1. Open **Task Manager** from your windows search bar
2. Click **More Details** and go to the **Processes** tab
3. Identify apps using excessive **CPU** or **Memory**
4. Select the offending app and click **End Task**
5. If the issue persists, run:
   "chkdsk" — checks the hard drive for errors
   

## What I Learned
Memory leaks happen when an app holds onto RAM it no longer needs. Task Manager lets you see exactly what is eating resources in real time.
