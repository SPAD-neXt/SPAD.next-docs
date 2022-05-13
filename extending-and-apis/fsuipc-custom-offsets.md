---
description: Adding custom offset to FSUIPC Data
---

# FSUIPC: Custom Offsets



{% file src="../.gitbook/assets/FSUIPC Local.xml" %}
FSUIPC Custom Offsets Sample XML&#x20;
{% endfile %}

Please make sure you keep Version at 1\
\
Each entry consists of one OffsetDefinition.\
Attribut Selectable : if false then Offset will not be offered in UI\
Name = Displayname of the offset in UI\
ValueType + Size = One of

* S8 = Signed Byte , Size = 1
* U8 = Unsigned bytes, Size = 1
* U16 = Unsigned SHort, Size = 2
* S16 = Signed Short , Size = 2
* U32/S32 = Un-/signed Int , Size = 4
* U64/S64 = Un-/Signed long , size = 8
* FLT32 = Float , size = 4
* FLT64 = Double , size = 8

Category = Main Category in Definition Brower (frist tree level)\
SubCategory = Sub Category in Definition Brower (second tree level). If more levels needed, seperate by "##"\
Access = R -> Readony , RW -> Read/write , R will not be offered in e.g. Change Data value\
Usage = Information shown in browser/mouseover. BBCode tags can be used here.\
Key = FSUIPC Offset in HEXADECIMAL as long HI-DWord:LO-Dword , usually HI-DWord should be 0000. Must always be formatted 000:0000 . Special: if the Offset represent just a BIT in a Value the Key is 0000:0000:BITNUMBER , an offsetentry for the main offset with Selectable="false" must exist then.\
\
optional Tag:\
LinkedEntry = Offset that will trigger value change for this offset as well. See example. If 000:0022 changes SPAD.neXt will also trigger a value changed for 0000:0021. Justleave it away if not needed.\
\
There some additional Tags which should not be necessary normally, e.g. for converting values on the fly (feet to meter etc). If you need those,let me know.\
\
Save the XML to Folder "%APDDATA%\SPAD.neXt\conf\data\_config\data" as "FSUIPC Local.xml"\
It will be read ONCE when starting up. if you change it you have to restart SPAD.neXt.\
If Problem occours reading the file, check the logfile.
