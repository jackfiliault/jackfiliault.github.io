---
layout: post
title: DITA and OxygenXML Sample - Procedure
date: '2025-08-07 13:42:19 -0700'
categories: [Writing sample]
tags: [dita]     # TAG names should always be lowercase
---
This sample was written in Oxygen XML using the DITA structure. This sample is a procedure topic following the DITA structure. An accompanying concept topic is included in my portfolio.  

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE task PUBLIC>
<task id="xxxXXXXXXXXXXXXX" xml:lang="en-us">
    <title>Close a denial and create an automatic adjustment</title>
<shortdesc>Use <wintitle>Close Denial/Auto Adjust</wintitle> to create an automatic adjustment and mark a denial for closure in the next denials management batch.</shortdesc>
<prolog>
<metadata>
<keywords>
<indexterm>close<indexterm>denial</indexterm></indexterm>
<indexterm>Denial<index-see-also>Denial Management</index-see-also></indexterm>
<indexterm>Close Denial/Auto Adjust</indexterm>
<indexterm>Auto Adjust</indexterm>
</keywords>
</metadata>
</prolog>
<taskbody>
<prereq>After you have a denial claim in context, perform the following actions:</prereq>
<steps>
<step><cmd>Access <wintitle>Denials Management</wintitle> through one of the following paths:</cmd>
<choices>
<choice>Click <uicontrol>Denials Management</uicontrol>.</choice>
<choice><menucascade><uicontrol>SFM</uicontrol><uicontrol>Receivables Management</uicontrol><uicontrol>Denials Management</uicontrol></menucascade>.</choice>
</choices>
</step>
<step><cmd>Select one or more existing denials.</cmd>
</step>
<step><cmd>Click <uicontrol>Close Denial/Auto Adjust</uicontrol> to adjust the denial amount from the claim and complete processing of a denial.</cmd>
<stepresult><wintitle>Close Denial/Auto Adjust</wintitle> is displayed.</stepresult>
</step>
<step><cmd>In <uicontrol>Root Cause</uicontrol>, select a root cause from the list.</cmd>
</step>
<step><cmd>In <uicontrol>Responsible Area</uicontrol>, select the area responsible for the denial.</cmd>
</step>
<step><cmd>In <uicontrol>Denial Action</uicontrol>, select the action that must occur as a result of the denial.</cmd>
</step>
<step><cmd>In <uicontrol>Denial Result</uicontrol>, select the outcome of the denial.</cmd>
</step>
<step><cmd>In <uicontrol>Denial Close Reason</uicontrol>, select a description value predefined from the <uicontrol>Denial Close Reason</uicontrol> dictionary.</cmd>
</step>
<step><cmd>In <uicontrol>Auto Close Denial Adjustment Txn Code</uicontrol>, select <uicontrol>Search</uicontrol> to find the transaction code to be used for the adjustment.</cmd>
<info>The <uicontrol>Auto Close Denial Adjustment Txn Code</uicontrol> automatically populates with the default <uicontrol>Contractual Adj Txn Code</uicontrol> configured in <wintitle>Adjustments and Denials Processing Configuration</wintitle> or <wintitle>Manual Denial Close and Auto Adjustment Configuration</wintitle>. If no transaction code is displayed by default, then a code must be selected using <uicontrol>Search</uicontrol>.</info>
</step>
<step><cmd>Click <uicontrol>OK</uicontrol>.</cmd>
<stepresult>The denial status is changed to <uicontrol>Marked for Closure</uicontrol> and generated in the denials management batch. <uicontrol>Marked for Closure</uicontrol> denials are batched and closed according to the <wintitle>Manual Denial Close and Auto Adjustment Configuration</wintitle>.</stepresult>
</step>
</steps>
</taskbody>
</task>
```
