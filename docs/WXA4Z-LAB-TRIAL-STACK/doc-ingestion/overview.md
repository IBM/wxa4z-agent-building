# Overview of Doc Ingestion

Now that you've already tested the **zRAG Agent** capabilities using the default IBM documentation, you will now demonstrate the ability to augment the zRAG with additional internal knowledge that may be unique to an organization. 


As an example, a client mentioned that their developers often need reference material on company-specific legacy code or company-specific syntax. The users must search through volumes of documentation to find it or look at old code. Also, there exists a need for their operational support group to quickly determine how to resolve technical issues using internal runbooks.

In this section, you will be able to demonstrate how watsonx Assistant for Z can assist developers and operational support personnel in finding answers about internal processes for code development and deployment. You will go through the steps of ingesting a set of sample documentation provided to illustrate this process.




## Overview of sample docs to ingest

To demonstrate this capability, a set of custom documents have already been uploaded to a remote S3 source, which you'll leverage to ingest the documents into your environment's client ingestion service. 

In this lab, there are three sample documents provided to illustrate the types of internal documentation a customer may want to ingest, which you will use for the purpose of this lab.

These documents include:

- ***Mainframe_COBOL_Error_Codes.pdf***
    This is a document containing company-specific mainframe COBOL error codes for their application. Developers within the organization typically review this document to quickly diagnose issues based on the application error codes returned.

- ***Mainframe_Operational_Incidents_Logs.xlsx***
  
    This is an Excel spreadsheet that is leveraged by the organization’s operational support team and contains historical records of production-level incidents that occurred. For each incident, there’s a record of what the incident was, the date, how it was resolved and who was involved in resolving the incident.

- ***COBOL-CICS-to-Java-Internal-Framework.pdf***

    This document is leveraged by the development team and contains details about the organization’s internal framework for developing applications consisting of legacy COBOL CICS interoperating with new Java code. Within the document contains company-specific coding practices and code syntax that the developers frequently reference.
