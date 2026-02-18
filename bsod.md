# Blue Screen of Death (BSOD)

## What It Is
A BSOD occurs simply when windows crashes completely to prevent damage.

## Fix
1. Open **Event Viewer** and navigate to "Windows logs > System"
2. Filter the log for **Critical** or **Error** levels
3. Look for a **BugCheck** entry to find the specific file or driver that caused the crash

## What I Learned
A BSOD is not random — Windows logs exactly what caused it. Event Viewer is the key tool to find the guilty driver or file behind the crash.
