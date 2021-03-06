---
uid: netserver_configuration_documents
title: NetServer Documents Element
date: 2018-06-06
SortOrder: 76
---
Configuration used to access the SuperOffice documents. It is used by NetServer to identify which document archive and temporary directory are used. To restricted access to the document archive, specify domain credentials with read and write access to the archive for NetServer to impersonate.

```xml
<Documents>
  <add key="ArchivePath" value="c:\so_arc\" />
  <add key="TemporaryPath" value="c:\temp\" />
  <add key="ImpersonateUser" value="false" />
  <add key="ArchiveUser" value="" />
  <add key="ArchivePassword" value="" />
  <add key="ArchiveDomain" value="" />
  <add key="BufferSize" value="1024" />
</Documents>
```

|Name|Description|
|------------|----|
|ArchivePath|Path for SO_ARC.  Even it the so arc is not used, default path for document template folder is calculated from this folder.|
|ArchivePath1|Alternative/additional archive path to search for documents|
|ArchivePath2|Alternative/additional archive path to search for documents|
|ArchivePath3|Alternative/additional archive path to search for documents|
|ArchivePath4|Alternative/additional archive path to search for documents|
|ArchivePath5|Alternative/additional archive path to search for documents|
|ArchivePath6|Alternative/additional archive path to search for documents|
|ArchivePath7|Alternative/additional archive path to search for documents|
|ArchivePath8|Alternative/additional archive path to search for documents|
|ArchivePath9|Alternative/additional archive path to search for documents|
|ArchivePath10|Alternative/additional archive path to search for documents|
|TemplatePath|Path to document templates. If this value is not specified, the "Template" folder under ArchivePath is assumed.|
|TemporaryPath|Temporary folder for working with documents. If this value does not exist, the environment variable "TEMP" is used to find temporary folder.|
|ImpersonateUser|Impersonate the user to access the document archive. If true, see section ArchiveUser for further reference.|
|ArchiveUser|Username of the user to impersonate.|
|ArchivePassword|Password of the user to impersonate.|
|ArchiveDomain|Domain of the user to impersonate.|
|BufferSize|Size in kilobytes of the internal buffer used for file handling.  Default value is 1024.|
|CanCreateDocumentTemplates|New document templates can be stored in SoArc.|
