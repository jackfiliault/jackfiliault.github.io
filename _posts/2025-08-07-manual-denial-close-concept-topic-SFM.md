---
layout: post
title: DITA and OxygenXML Sample - Concept
date: '2025-08-07 13:52:42 -0700'
categories: [Writing sample]
tags: [dita]     # TAG names should always be lowercase
---
This sample was written in Oxygen XML using the DITA structure. This sample is a concept topic following the DITA structure for one of the screens in Sunrise Financial manager. An accompanying procedure topic is included in my portfolio.  

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE concept PUBLIC>
<concept id="xxxXXXXXXXXXXXXX" xml:lang="en-us">
	<title>Manual denial close and auto adjustment configuration</title>
<shortdesc>Configure which transaction codes automatically adjust and close denials.</shortdesc>
    <prolog>
<metadata>
<keywords>
<indexterm>Manual Denial Close and Auto Adjust Configuration</indexterm>
<indexterm>Manual Denial</indexterm>
<indexterm>Auto Close</indexterm>
</keywords>
</metadata>
<data name="Manual_Denial_Close_and_Auto_Adjustment_Configuration">Manual Denial Close and Auto Adjustment Configuration</data>
</prolog>
    <conbody>
<p>You must have the correct permissions to access <wintitle>Manual Denial Close and Auto Adjust Configuration</wintitle>. Contact your administrator for more information.</p>
<section>
<title>Create Denials Management Batch by Facility</title>
<p>This option configures the logic <ph keyref="x_SFM"/> follows to batch adjustment transactions in <menucascade><uicontrol>Denials Management</uicontrol><uicontrol>Close Denial/Auto Adjust</uicontrol></menucascade>.</p>
<p><uicontrol>Create Denials Management Batch by Facility</uicontrol> is not selected by default. If not selected then the application generates all adjustment transactions into a single batch for all facilities within the enterprise. If selected then the application generates adjustment transactions into facility specific batches.</p>
</section>
<section>
<title>System Auto Close Batch</title>
<p>This option configures whether the application will automatically close batches of denial claims with the status <uicontrol>Marked for Closure</uicontrol> daily or if the application will require manual batch closure.</p>
<p>The <uicontrol>System Auto Close Batch</uicontrol> is not selected by default. If not selected then the application will require manual batch closure for <uicontrol>Marked for Closure</uicontrol> denial claims. If selected then the application will automatically close batches of <uicontrol>Marked for Closure</uicontrol> denial claims and make automatic adjustments at the time configured in <uicontrol>System Auto Close Batch Time</uicontrol>.</p>
</section>
<section>
<title>System Auto Close Batch Time</title>
<p>This option configures the time of day that all daily batch closures for denial claims with the <uicontrol>Marked for Closure</uicontrol> status are processed.</p>
<p>The <uicontrol>System Auto Close Batch Time</uicontrol> is midnight by default. This option is only enabled when <uicontrol>System Auto Close Batch</uicontrol> is selected.</p>
</section>
<section>
<title>Use Claim Denial's Linked Configuration for Auto Close Denial Transaction Code</title>
<p>This option configures what value, if any, automatically populates the <uicontrol>Auto Close Denial Adjustment Txn Code</uicontrol> field in <menucascade><uicontrol>Denials Management</uicontrol><uicontrol>Close Denial/Auto Adjust</uicontrol></menucascade>.</p>
<p><uicontrol>Use Claim Denial's Linked Configuration for Auto Close Denial Transaction Code</uicontrol> is not selected by default. If not selected then the <uicontrol>Auto Close Denial Adjustment Txn Code</uicontrol> field in <wintitle>Close Denial/Auto Adjust</wintitle> is populated with the <uicontrol>Auto Close Denial Adjustment Txn Code</uicontrol> configured in <wintitle>Manual Denial Close and Auto Adjustment Configuration</wintitle>. If that code is not configured then the field in <wintitle>Close Denial/Auto Adjust</wintitle>will be blank and require manual input.</p>
<p>If selected then the application will follow the <uicontrol>Contractual Adj Txn Code</uicontrol> in <wintitle>Adjustments and Denials Processing Configuration</wintitle> to populate the transaction code.</p>
</section>
<section>
<title>Additional configuration for facilities</title>
<p><uicontrol>Use the Enterprise Transaction Code for this facility</uicontrol> configures the selected facility to use the <uicontrol>Auto Close Denial Adjustment Txn Code</uicontrol> configured at the enterprise level.</p>
</section>
</conbody>
</concept>
```
