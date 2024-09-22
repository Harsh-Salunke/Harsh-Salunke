<h1 align="center">Hi 👋, I'm Harsh Salunke</h1>
<h3 align="center">Explore, Set Up, and Contribute!</h3>

<p align="left"> <img src="https://komarev.com/ghpvc/?username=harsh-salunke&label=Profile%20views&color=0e75b6&style=flat" alt="harsh-salunke" /> </p>

- 📫 How to reach me **harshsalunkesir@gmail.com**

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://linkedin.com/in/harsh salunke" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="harsh salunke" height="30" width="40" /></a>
<a href="https://instagram.com/harshbaba_002" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="harshbaba_002" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40"/> </a> <a href="https://www.w3schools.com/cpp/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="cplusplus" width="40" height="40"/> </a> <a href="https://www.figma.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" width="40" height="40"/> </a> <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a> </p>

<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=harsh-salunke&show_icons=true&locale=en&layout=compact" alt="harsh-salunke" /></p>

<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=harsh-salunke&show_icons=true&locale=en" alt="harsh-salunke" /></p>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=harsh-salunke&" alt="harsh-salunke" /></p>================================================================================
  Licensed to the Apache Software Foundation (ASF) under one or more
  contributor license agreements.  See the NOTICE file distributed with
  this work for additional information regarding copyright ownership.
  The ASF licenses this file to You under the Apache License, Version 2.0
  (the "License"); you may not use this file except in compliance with
  the License.  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
================================================================================


                     Apache Tomcat Version 9.0.91
                            Release Notes


=========
CONTENTS:
=========

* Dependency Changes
* API Stability
* Bundled APIs
* Web application reloading and static fields in shared libraries
* Security manager URLs
* Symlinking static resources
* Viewing the Tomcat Change Log
* Cryptographic software notice
* When all else fails


===================
Dependency Changes:
===================
Tomcat 9.0 is designed to run on Java 8 and later.


==============
API Stability:
==============

The public interfaces for the following classes are fixed and will not be
changed at all during the remaining lifetime of the 9.x series:
- All classes in the javax namespace

The public interfaces for the following classes may be added to in order to
resolve bugs and/or add new features. No existing interface method will be
removed or changed although it may be deprecated.
- org.apache.catalina.* (excluding sub-packages)

Note: As Tomcat 9 matures, the above list will be added to. The list is not
      considered complete at this time.

The remaining classes are considered part of the Tomcat internals and may change
without notice between point releases.


=============
Bundled APIs:
=============
A standard installation of Tomcat 9.0 makes all of the following APIs available
for use by web applications (by placing them in "lib"):
* annotations-api.jar (Annotations package)
* catalina.jar (Tomcat Catalina implementation)
* catalina-ant.jar (Tomcat Catalina Ant tasks)
* catalina-ha.jar (High availability package)
* catalina-ssi.jar (Server-side Includes module)
* catalina-storeconfig.jar (Generation of XML configuration from current state)
* catalina-tribes.jar (Group communication)
* ecj-4.20.jar (Eclipse JDT Java compiler)
* el-api.jar (EL 3.0 API)
* jasper.jar (Jasper 2 Compiler and Runtime)
* jasper-el.jar (Jasper 2 EL implementation)
* jsp-api.jar (JSP 2.3 API)
* servlet-api.jar (Servlet 4.0 API)
* tomcat-api.jar (Interfaces shared by Catalina and Jasper)
* tomcat-coyote.jar (Tomcat connectors and utility classes)
* tomcat-dbcp.jar (package renamed database connection pool based on Commons DBCP 2)
* tomcat-jdbc.jar (Tomcat's database connection pooling solution)
* tomcat-jni.jar (Interface to the native component of the APR/native connector)
* tomcat-util.jar (Various utilities)
* tomcat-websocket.jar (WebSocket 1.1 implementation)
* websocket-api.jar (WebSocket 1.1 API)

You can make additional APIs available to all of your web applications by
putting unpacked classes into a "classes" directory (not created by default),
or by placing them in JAR files in the "lib" directory.

To override the XML parser implementation or interfaces, use the appropriate
feature for your JVM. For Java <= 8 use the endorsed standards override
feature. The default configuration defines JARs located in "endorsed" as endorsed.
For Java 9+ use the upgradeable modules feature.


================================================================
Web application reloading and static fields in shared libraries:
================================================================
Some shared libraries (many are part of the JDK) keep references to objects
instantiated by the web application. To avoid class loading related problems
(ClassCastExceptions, messages indicating that the classloader
is stopped, etc.), the shared libraries state should be reinitialized.

Something which might help is to avoid putting classes which would be
referenced by a shared static field in the web application classloader,
and putting them in the shared classloader instead (JARs should be put in the
"lib" folder, and classes should be put in the "classes" folder).


======================
Security manager URLs:
======================
In order to grant security permissions to JARs located inside the
web application repository, use URLs of the following format
in your policy file:

file:${catalina.base}/webapps/examples/WEB-INF/lib/driver.jar


============================
Symlinking static resources:
============================
By default, Unix symlinks will not work when used in a web application to link
resources located outside the web application root directory.

This behavior is optional, and the "allowLinking" flag may be used to deactivate
the check.


==============================
Viewing the Tomcat Change Log:
==============================
The full change log is available from https://tomcat.apache.org and is also
included in the documentation web application.


=============================
Cryptographic software notice
=============================
This distribution includes cryptographic software.  The country in
which you currently reside may have restrictions on the import,
possession, use, and/or re-export to another country, of
encryption software.  BEFORE using any encryption software, please
check your country's laws, regulations and policies concerning the
import, possession, or use, and re-export of encryption software, to
see if this is permitted.  See <http://www.wassenaar.org/> for more
information.

The U.S. Government Department of Commerce, Bureau of Industry and
Security (BIS), has classified this software as Export Commodity
Control Number (ECCN) 5D002.C.1, which includes information security
software using or performing cryptographic functions with asymmetric
algorithms.  The form and manner of this Apache Software Foundation
distribution makes it eligible for export under the License Exception
ENC Technology Software Unrestricted (TSU) exception (see the BIS
Export Administration Regulations, Section 740.13) for both object
code and source code.

The following provides more details on the included cryptographic
software:
  - Tomcat includes code designed to work with JSSE
  - Tomcat includes code designed to work with OpenSSL


====================
When all else fails:
====================
See the FAQ
https://tomcat.apache.org/faq/
