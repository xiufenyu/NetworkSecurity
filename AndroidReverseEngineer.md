# Methodology
	1. Test different versions of the App. Prefer a recent old version instead of the latest version   \
	2. Try an EMULATOR if the app crashes in a real phone   \
	3. Test the FIRST installation and NON-FIRST installation   \

## Log Analysis
	1. Analyze LOGS from logcat: understand the logic and code  \

## Dynamic Analysis
	1. Hook "Network"  \
	2. If hooking is not working, try to DEBUG the app.   \
	3. If hooking and Debugging is not working, try to PATCH the APK   \
	4. 

## Memory Analysis
	1. INSPECT the MEMORY (objection, r2frida)   \
	2. DUMP the MEMORY if you really cannot bypass the app (fridump, r2frida)   \


## Reverse Engineer
	1. Analyze NATIVE libraries  \
	2. Find all imported functions, like open, read, etc. They could be used to read special files to detect debugging activities.  \

## Static Analysis
	1. Start with hardcode values. Verify if domains, Ips, ports are hardcoded   \
	2. Analysis the app based on OWASP Security   \
	3. For bypassing anti-debugging/anti-hooking, do STATIC analysis of the JAVA code first.  \


# Android Knowledge
Native libraries are generally in Resources/lib directory.
