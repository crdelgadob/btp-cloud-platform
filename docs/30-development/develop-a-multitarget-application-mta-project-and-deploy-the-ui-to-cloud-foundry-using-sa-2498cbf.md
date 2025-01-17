<!-- loio2498cbfce1b14f3b9f62fab9fa4407f7 -->

# Develop a Multitarget Application \(MTA\) Project and Deploy the UI to Cloud Foundry Using SAP Business Application Studio

Get an overview about how to create and deploy an MTA to Cloud Foundry using SAP Business Application Studio.



> ### Note:  
> SAP Fiori tools extensions can be used in both SAP Business Application Studio and Visual Studio \(VS\) Code. See [Introduction](https://help.sap.com/viewer/454b7fb9aacd4e369e5be8f7e909d3ec/Latest/en-US/fd9e32d52c9e46e4ba77aba343656610.html).

> ### Recommendation:  
> We recommend using the same UI5 version that is being used by the ABAP environment system.
> 
> To check the UI5 version in the SAP Fiori launchpad of your ABAP environment system, use command ***Alt+Ctrl+Shift+P*** or navigate to the user actions menu and select *About*. See [User Actions Menu](https://help.sap.com/viewer/fd8f9fda63fa4c7a92bb1d4b4ac5582c/Cloud/en-US/27834b1aacf344f38910686d8fb0eb0a.html "The user actions menu offers user-related options e.g. to open apps, to change the launchpad layout or to contact support.") :arrow_upper_right:.



<a name="loio2498cbfce1b14f3b9f62fab9fa4407f7__section_mlb_hzb_z4b"/>

## Prerequisites

You have set up SAP Business Application Studio. See [Setup of UI Development in SAP Business Application Studio](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/37a896bfac604076ae825a1d37b0bd0a.html).



<a name="loio2498cbfce1b14f3b9f62fab9fa4407f7__section_dvd_t3k_hmb"/>

## Generating and Deploying Your Application

> ### Prerequisites:  
> -   You have exposed a RAP business service as an OData service. See [Using Service Binding Editor for OData V2 Service](https://help.sap.com/viewer/923180ddb98240829d935862025004d6/Cloud/en-US/81dc788fbda74883bd775a4036fa4b67.html).
> -   Business catalog `SAP_A4C_BC_DEV_UID_PC` is assigned to your user, which allows you to deploy your application.
> -   Business catalog `SAP_CORE_BC_EXT_TST` is assigned to your user, which allows you to preview your application and discover available OData services. See [Business Catalog for Key User Tasks](../50-administration-and-ops/business-catalog-for-key-user-tasks-65b70bf.md).

![](images/BAS_1S4HC_Step_2_3311af7.png)

1.  As a developer user in SAP Business Application Studio, create an MTA project with approuter configuration.
    1.  Use the destination that you have created for the SAP Business Application studio integration \(`SAP_Business_Application_Studio`\). See [Creating a Destination to the ABAP System for SAP Business Application Studio](../20-getting-started/creating-a-destination-to-the-abap-system-for-sap-business-application-studio-e597948.md).
    2.  To create an MTA with approuter configuration, use the*Fiori CF Application Router Generator*. See [Generate an MTA Deployment File](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/9c41152c5b8d4a658d7ef9f318b28917.html).

        This generates an application router configuration.

    3.  To create a Fiori application in the subfolder of the MTA file location, use the *SAP Fiori Generator*. See [Add a Fiori Application to an MTA Deployment File with the Fiori Generator](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/5a17ba6b62b2462aa0e25ffae7b8d728.html).
    4.  Add an SAP Fiori launchpad configuration for your UI project. See section *Add FLP configuration* in [Additional Configuration](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/9bea64e63b824261932d90037ce3c5ae.html).

        If you want to create you FLP configuration later, see [SAP Fiori Launchpad Configuration](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/bc3cb890dbb84d51ae80394821ce4990.html).

        > ### Restriction:  
        > -   The UIAD object is created upon deployment only if the intent is defined in the manifest
        > -   Only one intent is supported
        > -   If you change the ID of the intent, the existing SAP Fiori launchpad content content will break


2.  Continue with the development of the UI, for example, with the help of guided development. See [Implement Features using Guided Development](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/0c9e518ecf704b2f80a2bed0eaca60ae.html).
3.  Now you can preview the generated SAP Fiori application. See [Preview an Application](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/b962685bdf9246f6bced1d1cc1d9ba1c.html).
4.  Build the application by executing command ***npm run build***.

    This generates an `*.mtar` file and `mta_archives` folder.

5.  Log on to Cloud Foundry and deploy the SAP Fiori UI by executing command ***npm run deploy*** in the terminal of your project. See section *Deployment to Cloud Foundry* in [Deploy an Application](https://help.sap.com/viewer/17d50220bcd848aa854c9c182d65b699/Latest/en-US/607014e278d941fda4440f92f4a324a6.html).

**Related Information**  


[SAP Business Application Studio](https://help.sap.com/viewer/product/SAP%20Business%20Application%20Studio/Cloud/en-US)

[SAP Fiori Tools](https://help.sap.com/viewer/product/SAP_FIORI_tools/Latest/en-US)

[SAP Fiori Overview](https://help.sap.com/viewer/product/SAP_FIORI_OVERVIEW/5_OVERVIEW/en-US?task=discover_task)

[SAP Cloud Portal Service](https://help.sap.com/viewer/product/Portal_Service/1.0/en-US)

