Getting Started with Blackberry
============================

Cordova for BlackBerry makes use of the [BlackBerry WebWorks framework](https://bdsc.webapps.blackberry.com/html5). BlackBerry WebWorks tooling is available for Windows or Mac environments. WebWorks applications can ONLY be deployed to BlackBerry devices running OS 5.0 and higher or the BlackBerry Playbook operating system.

Video Tutorials:
----------------

- [PhoneGap and BlackBerry Widgets quick Start Video](http://www.youtube.com/v/eF0h0K0OLwI?autoplay=1)

1. Requirements
---------------

- Windows XP (32-bit) or Windows 7 (32-bit and 64-bit) or Mac OSX 10.6.4+
- Java Development Kit (JDK)
    - Windows: [Oracle JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html#jdk) (32-Bit Version)
    - Mac OS X: Versions prior to Mac OS X 10.7 provided Java by default.  OS X 10.7+ requires installation of [Java](http://support.apple.com/kb/DL1421).
- Apache Ant
    - Windows: [Apache Ant](http://ant.apache.org/bindownload.cgi).
    - Mac OS X: Apache Ant is bundled with Java install.
- BlackBerry Desktop Software
	- http://us.blackberry.com/apps-software/desktop/
	
2. Install SDK + Cordova
-------------------------

- Download and install one or more of the WebWorks SDKs. Keep note of the install directory.
    - [BlackBerry WebWorks Smartphone SDK](https://bdsc.webapps.blackberry.com/html5/download/sdk) for smartphone development
    - [BlackBerry WebWorks Tablet OS SDK](https://bdsc.webapps.blackberry.com/html5/download/sdk) for Playbook development.
- Download the latest copy of [Cordova](http://phonegap.com/download) and extract its contents.

3. Setup New Project
--------------------

- Open up a command prompt/terminal and navigate to where you extracted Cordova.
- There is a directory for each platform that Cordova supports.  CD into the blackberry directory.
- The blackberry directory contains two directories, `sample` and `www`.  The `sample` folder contains a complete Cordova project.  Copy the `sample` folder to another location on your computer.
- Change to the newly created directory.
- Open up the project.properties file with your favorite editor and change the lines `blackberry.bbwp.dir=` and/or `playbook.bbwp.dir=` to equal the respective install locations of the SDKs you downloaded earlier.

4. Hello World
--------------

Build the Cordova sample project by typing `ant target build` in your command prompt/terminal while you are in your project's directory. Replace `target` with either `blackberry` or `playbook`. Note this is a sample Cordova project and not a basic hello world application. The provided index.html in the www contains example usages of many of the Cordova API.

5A. Deploy to Simulator
--------------------------------------

BlackBerry smartphone simulators are only available on Windows. PlayBook simulators require VMWare Player (Windows) or VMWare Fusion (Mac OS X). The WebWorks SDK provides a default simulator. Additional simulators are [available](http://us.blackberry.com/developers/resources/simulators.jsp).

- Open the project.properties file with your favorite editor and customize the following properties.
    - Smartphone (Optional)
        - `blackberry.sim.dir` : Path to directory containing simulator. On windows file separator '\' must be escaped '\\\'.
        - `blackberry.sim.bin` : Name of the simulator executable in the specified directory.
    - Playbook
        - `playbook.sim.ip` : IP address of simulator obtained when placing the simulator in developer mode through simulator security settings.
        - `playbook.sim.password` : Simulator password which can be set through simulator security settings.
- While in your project directory, in command prompt/terminal type `ant target load-simulator`. Replace `target` with either `blackberry` or `playbook`.  Note, for PlayBook the simulator virtual image must already be started.
- The application will be installed in the All Applications section in the simulator.  Note, on BlackBerry OS 5 the application is installed in the Downloads folder.

5B. Deploy to Device (Windows and Mac)
--------------------------------------

Deploying to a device requires signing keys which can be obtained from RIM by filling out this [form](https://www.blackberry.com/SignedKeys/).

- Open the project.properties file with your favorite editor and customize the following properties:
    - Smartphone (Optional)
        - `blackberry.sigtool.password` : Password used when code signing keys were registered.  If not specified, a prompt will occur.
    - Playbook
        - `playbook.sigtool.csk.password`
        - `playbook.sigtool.p12.password`
        - `playbook.device.ip` : IP address of device obtained when placing the device in developer mode through device security settings.
        - `playbook.device.password` : Device password which is set through device security settings.
- While in your project directory, in command prompt/terminal type `ant target load-device`. Replace `target` with either `blackberry` or `playbook`.
- The application will be installed in the All Applications section in the device.  Note, on BlackBerry OS 5 the application is installed in the Downloads folder.


Done!
-----

You can also checkout more detailed version of this guide [here](http://wiki.phonegap.com/w/page/31930982/Getting-Started-with-PhoneGap-BlackBerry-WebWorks).
