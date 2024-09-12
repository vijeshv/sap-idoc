# SAP-IDOC
SAP IDOC Advance Actions &amp; Sample Neoload project.                                                                                                                                                               
IDoc (intermediate document) is a standard data structure used in SAP applications to transfer data to and from SAP system applications and external systems over tRFC protocol. Using IDocs, companies with SAP ERP systems, for example, can exchange data with external entities like their partners or customers

## Overview

This repository contains NeoLoad Advanced Actions that allows performance testers using NeoLoad to connect SAP Server Server & make RF calls.
Implementation is in progress.

| Property           | Value                                                                         |
|--------------------|-------------------------------------------------------------------------------|
| Maturity           | Experimental                                                                  |
| Support            | Supported by Neotys                                                           |
| Author             | Neotys                                                                        |
| License            | [BSD Simplified](https://www.neotys.com/documents/legal/bsd-neotys.txt)       |
| NeoLoad            | 2024.2 (Enterprise or Professional Edition w/ Integration & Advanced Usage)    |
| Bundled in NeoLoad | No                                                                          |
| Download Binaries  | See the [latest release]() |


## Installation

### Setting up the NeoLoad Advance action for SAP RFC

1. Download the latest Advance Action jar [latest release](https://github.com/vijeshv/sap-idoc/releases/tag/sapidoc_0.0.1).
   Keept the Jar file in the extlib folder of yor Neoload Project

3. Download the External Refereces files from floder (https://github.com/Neotys-Labs/SAP_RFC/tree/main/ExternalReferences)
   keep sapjco3.jar & sapidoc3.jar (optional need only if you want IDOC transfer)in Jar file in the extlib folder of yor Neoload Project
   keep sapjco3.dll file <Neoload Installation folder>\lib\x64

4. restart neoload
## Advanced Actions definitions
## Start IDOC_Listener 
This Advanced Action helps you to register at gateway as partner, listen for  outbound IDOCS from source system, receive & save in local HDD
| Name                     | Description       |
| ---------------          | ----------------- |
| Host                     | SAP Server name or IP address to connect |
| SYSNR                    | SYSNR |
| Client                   | Client |
| LANG                     | LANG |
| Username                 | Username |
| Password                 | Password |
| GatewayHost              | Sap Gateway to connect by vendour system |
| GatewayService           | Service or port to listen |
| ProgramID                | ProgramID |
| Connectioncount          | Number of parallel connections |
| OuboundFileRepository    | Folder in LG box to store the outbound file received |

## Create IDOC Destination - Parameters
This Advanced Action helps you define tRFC connection to SAP gateway

| Name                     | Description       |
| ---------------          | ----------------- |
| Destination              | A name of the SAP connection. this name will be using in rest of teh actions            |
| Host                     | SAP Server name or IP address to connect |
| SYSNR                    | SYSNR |
| Client                   | Client |
| LANG                     | LANG |
| Username                 | Username |
| Password                 | Password |

## IDOC-Send Inbound - Parameters
This Advanced Action helps you simulate Inbound IDOC based on Inbound-IDOC payload template & outbound IDOCS received -Inputs & Oupputs parameters
| Name                     | Description       |
| ---------------          | ----------------- |
| Destination              | A name of the SAP connection. this name will be using in rest of the actions            |
| template_filepath        | Path of inboud payload template |
| template_filename        | Inbound-Template xml file name |
| parseXML                 | Whether to parse xml for varaible or not|
| responding to Outbound   | whether to scan outbound file received for variable |
| Outbound file directory  | Oubound file directory  at listener side |

Status Codes:
* NL-Idocs_ERROR :  Any IDOC Listener Error.
* NL-IDOCINBOUND_ERROR :  Any INBOUND IDOC Error. 

