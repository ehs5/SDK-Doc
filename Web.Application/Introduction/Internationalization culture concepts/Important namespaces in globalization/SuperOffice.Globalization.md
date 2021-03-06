<properties date="2016-06-24"
SortOrder="12"
/>

The classes in this namespace are mainly dedicated for the different providers that provide us the data within a page in the application. Listed below are important classes of the namespace and a brief description about them.

**CultureManager** – This class will provide methods that will give out the details on the language used and get the language that is supported by the system. The class will provide methods to convert a language name to its LCID (Locale ID) and back to language name from LCID.

**ResourceManager** – This is the manager class that will manage the resource providers and initialize them. In addition it provides a rich set of methods that deals with date formats and converting them to local standards.

**ResourceDllProvider** – This provider will provide us with the localized resource strings from the corresponding resource assemblies. For example this provider will provide us with the Spanish resource strings from the Spanish language resource assembly if we chose Spanish as the language when we log into the system.

**ResXmlFileProvider** – This provider will provide us with the localized resource strings from the Resx XML files without compiling into assemblies. You can provide your own custom strings or override built-in strings using this provider.

**FieldLabelProvider** – This class is responsible for reading the field label data from the SuperOffice database. The class will use a pre generated numeric id dictionary to map between the numeric ids that are given to the database fields and the resource string that are used in the web pages. All the resources will be read from the database and will be stored in the memory for the life time of this provider when it is initialized.
