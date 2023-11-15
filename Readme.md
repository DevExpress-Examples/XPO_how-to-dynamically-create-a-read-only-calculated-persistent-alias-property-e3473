<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128585826/19.2.7%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E3473)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [Program.cs](./CS/ConsoleApplication17/Program.cs) 
* [XPAliasedMemberInfo.cs](./CS/ConsoleApplication17/XPAliasedMemberInfo.cs) 
<!-- default file list end -->
# How to dynamically create a read-only calculated (persistent alias) property


<p>When building and extending persistent classes at runtime, it is often desirable to create a non-persistent calculated property. Currently available <a href="https://documentation.devexpress.com/#CoreLibraries/DevExpressXpoMetadataXPClassInfo_CreateMembertopic">XPClassInfo.CreateMember</a> method overrides are only capable of creating writable <a href="https://documentation.devexpress.com/CoreLibraries/clsDevExpressXpoMetadataXPCustomMemberInfotopic.aspx">XPCustomMemberInfo</a> instances and the XPCustomMemberInfo.ReadOnly property cannot be changed.</p>
<p>This example demonstrates how to create a custom XPAliasedMemberInfo class inherited directly from <a href="https://documentation.devexpress.com/CoreLibraries/clsDevExpressXpoMetadataXPMemberInfotopic.aspx">XPMemberInfo</a>. In this class constructor, we add <a href="https://documentation.devexpress.com/CoreLibraries/clsDevExpressXpoPersistentAliasAttributetopic.aspx">PersistentAliasAttribute</a> with a specified expression, and override the GetValue method to evaluate the alias expression in the same manner as it is done in the XPBaseObject class. The read-only behavior is achieved by passing an argument to the base class constructor.</p>
<p>Also, an extender is implemented to provide additional methods for XPClassInfo class.</p>
<p> </p>

<br/>


