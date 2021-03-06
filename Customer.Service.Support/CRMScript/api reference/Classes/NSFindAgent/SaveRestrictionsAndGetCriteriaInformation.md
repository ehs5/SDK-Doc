---
title: NSCriteriaInformation SaveRestrictionsAndGetCriteriaInformation(String storageType, String providerName, String storageKey, NSArchiveRestrictionInfo[] restrictions, String[] staticColumns)
path: /EJScript/Classes/NSFindAgent/Member functions/NSCriteriaInformation SaveRestrictionsAndGetCriteriaInformation(String p_0, String p_1, String p_2, NSArchiveRestrictionInfo[] p_3, String[] p_4)
intellisense: 1
classref: 1
sortOrder: 3667
keywords: SaveRestrictionsAndGetCriteriaInformation(String,String,String,NSArchiveRestrictionInfo[],String[])
---


Save an array of restrictions for later use as search criteria (including as dynamic selection and Find). Then, return the same result as a call to GetCriteriaInformation would have done. The purpose is to encapsulate saving and updating of a GUI in one round trip.



* **storageType:** Restriction storage type specification, either 'Criteria' or 'Reporter' (or possible extensions)
* **providerName:** Name of archive provider that is the intended consumer of the restrictions
* **storageKey:** Storage key to be interpreted by the restriction storage provider, when it saves the restrictions as criteria
* **restrictions:** Array of restrictions. The ColumnInfo member and the DisplayValues members need NOT be populated; it is enough to provide a name, operator and any values the operator may need. The IsActive is also saved. Values should be encoded using the CultureDataFormatter to ensure compatibility across cultures.
* **staticColumns:** Optional array of restrictions that are to be EXCLUDED from the CriteriaArchiveRows part of the result. In the Find dialogs, that corresponds to the 'static' fields, to avoid duplicating them in the 'Match also' criteria list. This array can be null, indicating that all restrictions should be included in the criteria list.
* **Returns:** The result contains the restrictions in two forms: fully populated ArchiveRestrictionInfo objects, used to display details and for saving changes; and as a list suitable for an Archive control


