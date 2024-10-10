# Articles

	1. Top 3 anti-debugging technqiues
https://www.appknox.com/blog/anti-debugging-techniques

	2. OWASP 
https://github.com/OWASP/owasp-mastg/blob/master/Document/0x05j-Testing-Resiliency-Against-Reverse-Engineering.md

	3. Inspect Android Memory:
https://mas.owasp.org/MASTG/tools/generic/MASTG-TOOL-0036/


# Patch APK
https://gist.github.com/rigwild/02729a128b878186ffe8b1982d31b4f4

## APKLAB
	1. Install APKLab in VSCode

	2. Open base.apk with the following options:
	Only main classes
	Decompile Java
	
	Shortcut: "Ctrl+Shift+P"
	
	3. Inspect the Java code in the java_src directory and find the function you want to edit.
	If found ,go to its .smali file equivalent  in the smali directory, do your edit and save
	
	
	4. Right-click on the apktool.yml file: APKLab: Rebuild the APK

	5. The APK file is generated at dist/base.apk

## APK-MITM:
	

## APKtool
	1. Decompile without decoding resources
$ apktool -r d base.apk

	2. Compile with debug mode
$ apktool b   com.security.xvpn.z35kb
$ apktool b   -d com.security.xvpn.z35kb


	3. Sign the apk
$ 
