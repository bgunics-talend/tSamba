## tSamba
Talend Component
Changes compared to other tSamba Components.

 * Changed JCIFS 1.x JAR file to: jcifs-ng 
More info at: https://github.com/AgNO3/jcifs-ng
* Under the advanced settings the key-value like Jcifs Config settings can be set. Previously the following was set, this was removed from the code: ("jcifs.netbios.wins", <%=host%>)
List of options  can be found here:
https://www.qvera.com/kb/index.php/2243/what-are-the-network-share-configuration-parameters 
https://github.com/AgNO3/jcifs-ng/blob/master/src/main/java/jcifs/config/PropertyConfiguration.java
* Dependencies are linked from Maven. This should make it easier to keep the jcifs library up to date, and also the jar can be obtained from Maven automatically. This renders this component to require at least Talend 6.0.
* Log4j logs have been implemented. If Log4J is turned off, then console will be used.
* JCIFS Debug logs can be enabled. If any component enables debug log, all other components after it will use debug logs.
* Cleartext passwords has been replaced with proper password field, including the proxy settings.

* __tSambaList__ is now based entirely on tFileList (7.2) component.
	- Include/Exclude filters have been updated, sorting has been implemented.
	- Return variables has been expanded, it also contains CURRENT_FILE, CURRENT_FILEPATH, CURRENT_FILEEXTENSION, CURRENT_FILEDIRECTORY just like tFileList.

* __tSambaPut__ accepts Streams as well. Don't use this with big files, as the file is cached in memory entirely.

* Components can be shared using Project Properties in studio via GIT / SVN.

## Source code:
Source code can be found at: https://github.com/bgunics-talend/tSamba


### TODO:
* tSambaFileCopy is not migrated.
* tSambaWaitForFile is not migrated.


### Changelog: 
v2.0 - 2020 July 02 - Initial release.

### Changelog: 
v2.1 - Added Streaming option for Input component

v2.2 - Changed the SDK to jcifs-ng
Refactored the connection to an external utils file.
No dedicated connection component yet.

v3 - Added tSambaConnection + use existing connection