
# Group Trials

Services related to trials. Trials comprise of multiple studies. 

A "trial" in BrAPI represents an "investigation" in MIAPPE (Minimal Information about a Plant Phenotyping Experiment).





### Post - /search/trials [POST /brapi/v2/search/trials]

Advanced searching for the programs resource.
See Search Services for additional implementation details.

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|active|boolean|Is this trail currently active|
|commonCropNames|array[string]|Common name for the crop which this program is for|
|contactDbIds|array[string]|List of contact entities associated with this trial|
|externalReferenceIDs|array[string]|List of external references for the trait to search for|
|externalReferenceSources|array[string]|List of external references sources for the trait to search for|
|locationDbIds|array[string]|The location ids to search for|
|locationNames|array[string]|A human readable names to search for|
|page|integer|Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.|
|pageSize|integer|The size of the pages to be returned. Default is `1000`.|
|programDbIds|array[string]|A program identifier to search for|
|programNames|array[string]|A name of a program to search for|
|searchDateRangeEnd|string (date)|The end of the overlapping search date range. `searchDateRangeStart` must be before `searchDateRangeEnd`.  Return a Trial entity if any of the following cases are true  - `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is null   - `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is after `trial.startDate`  - `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is null  - `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is before `trial.endDate`|
|searchDateRangeStart|string (date)|The start of the overlapping search date range. `searchDateRangeStart` must be before `searchDateRangeEnd`.  Return a Trial entity if any of the following cases are true  - `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is null   - `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is after `trial.startDate`  - `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is null  - `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is before `trial.endDate`|
|studyDbIds|array[string]|List of study identifiers to search for|
|studyNames|array[string]|List of study names to filter search results|
|trialDbIds|array[string]|The ID which uniquely identifies a trial to search for|
|trialNames|array[string]|The human readable name of a trial to search for|
|trialPUIs|array[string]|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|active|boolean|Is this trail currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this trial|
|contacts|array[object]|List of contact entities associated with this trial|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|datasetAuthorships|array[object]|License and citation information for the data in this trial|
|datasetPUI|string||
|license|string|MIAPPE V1.1 (DM-7) License - License for the reuse of the data associated with this investigation. The Creative Commons licenses cover most use cases and are recommended.|
|publicReleaseDate|string (date)|MIAPPE V1.1 (DM-6) Public release date - Date of first public release of the dataset presently being described.|
|submissionDate|string (date)|MIAPPE V1.1 (DM-5) Submission date - Date of submission of the dataset presently being described to a host repository.|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date)|The date this trial ends|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|A program identifier to search for|
|programName|string|Human readable name of the program|
|publications|array[object]|MIAPPE V1.1 (DM-9) Associated publication - An identifier for a literature publication where the investigation is described. Use of DOIs is recommended.|
|publicationPUI|string||
|publicationReference|string||
|startDate|string (date)|The date this trial started|
|trialDbId|string|The ID which uniquely identifies a trial  MIAPPE V1.1 (DM-2) Investigation unique ID - Identifier comprising the unique name of the institution/database hosting the submission of the investigation data, and the accession number of the investigation in that institution.|
|trialDescription|string|The human readable description of a trial  MIAPPE V1.1 (DM-4) Investigation description - Human-readable text describing the investigation in more detail.|
|trialName|string|The human readable name of a trial  MIAPPE V1.1 (DM-3) Investigation title - Human-readable string summarising the investigation.|
|trialPUI|string|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "active": true,
    "commonCropNames": [
        "Tomatillo",
        "Paw Paw"
    ],
    "contactDbIds": [
        "e0f70c2a",
        "b82f0967"
    ],
    "externalReferenceIDs": [
        "http://purl.obolibrary.org/obo/ro.owl",
        "14a19841"
    ],
    "externalReferenceSources": [
        "OBO Library",
        "Field App Name"
    ],
    "locationDbIds": [
        "b28911cf",
        "5071d1e4"
    ],
    "locationNames": [
        "Location Alpha",
        "The Large Hadron Collider"
    ],
    "page": 0,
    "pageSize": 1000,
    "programDbIds": [
        "8f5de35b",
        "0e2d4a13"
    ],
    "programNames": [
        "Better Breeding Program",
        "Best Breeding Program"
    ],
    "searchDateRangeEnd": "2018-01-01",
    "searchDateRangeStart": "2018-01-01",
    "studyDbIds": [
        "cf6c4bd4",
        "691e69d6"
    ],
    "studyNames": [
        "The First Bob Study 2017",
        "Wheat Yield Trial 246"
    ],
    "trialDbIds": [
        "d2593dc2",
        "9431a731"
    ],
    "trialNames": [
        "All Yield Trials 2016",
        "Disease Resistance Study Comparison Group"
    ],
    "trialPUIs": [
        "https://doi.org/01093190",
        "https://doi.org/11192409"
    ]
}
```



+ Response 200 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "data": [
            {
                "active": true,
                "additionalInfo": {},
                "commonCropName": "Wheat",
                "contacts": [
                    {
                        "contactDbId": "5f4e5509",
                        "email": "bob@bob.com",
                        "instituteName": "The BrAPI Institute",
                        "name": "Bob Robertson",
                        "orcid": "http://orcid.org/0000-0001-8640-1750",
                        "type": "PI"
                    }
                ],
                "datasetAuthorships": [
                    {
                        "datasetPUI": "doi:10.15454/312953986E3",
                        "license": "https://CreativeCommons.org/licenses/by/4.0",
                        "publicReleaseDate": "2018-01-01",
                        "submissionDate": "2018-01-01"
                    }
                ],
                "documentationURL": "https://wiki.brapi.org",
                "endDate": "2018-01-01",
                "externalReferences": [
                    {
                        "referenceID": "doi:10.155454/12349537E12",
                        "referenceSource": "DOI"
                    },
                    {
                        "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                        "referenceSource": "OBO Library"
                    },
                    {
                        "referenceID": "75a50e76",
                        "referenceSource": "Remote Data Collection Upload Tool"
                    }
                ],
                "programDbId": "673f378a",
                "programName": "Tomatillo_Breeding_Program",
                "publications": [
                    {
                        "publicationPUI": "doi:10.15454/312953986E3",
                        "publicationReference": "Selby, BrAPI - An application programming interface for plant breeding applications, Bioinformatics, https://doi.org/10.1093/bioinformatics/190"
                    }
                ],
                "startDate": "2018-01-01",
                "trialDbId": "1883b402",
                "trialDescription": "General drought resistance trial initiated in Peru before duplication in Africa",
                "trialName": "Peru Yield Trial 1",
                "trialPUI": "https://doi.org/101093190"
            }
        ]
    }
}
```

+ Response 202 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "searchResultsDbId": "551ae08c"
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Malformed JSON Request Object\n\nERROR - 2018-10-08T18:15:11Z - Invalid query parameter\n\nERROR - 2018-10-08T18:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - User does not have permission to perform this action"
```




### Get - /search/trials/{searchResultsDbId} [GET /brapi/v2/search/trials/{searchResultsDbId}{?page}{?pageSize}]

Advanced searching for the trials resource.
See Search Services for additional implementation details.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|active|boolean|Is this trail currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this trial|
|contacts|array[object]|List of contact entities associated with this trial|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|datasetAuthorships|array[object]|License and citation information for the data in this trial|
|datasetPUI|string||
|license|string|MIAPPE V1.1 (DM-7) License - License for the reuse of the data associated with this investigation. The Creative Commons licenses cover most use cases and are recommended.|
|publicReleaseDate|string (date)|MIAPPE V1.1 (DM-6) Public release date - Date of first public release of the dataset presently being described.|
|submissionDate|string (date)|MIAPPE V1.1 (DM-5) Submission date - Date of submission of the dataset presently being described to a host repository.|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date)|The date this trial ends|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|A program identifier to search for|
|programName|string|Human readable name of the program|
|publications|array[object]|MIAPPE V1.1 (DM-9) Associated publication - An identifier for a literature publication where the investigation is described. Use of DOIs is recommended.|
|publicationPUI|string||
|publicationReference|string||
|startDate|string (date)|The date this trial started|
|trialDbId|string|The ID which uniquely identifies a trial  MIAPPE V1.1 (DM-2) Investigation unique ID - Identifier comprising the unique name of the institution/database hosting the submission of the investigation data, and the accession number of the investigation in that institution.|
|trialDescription|string|The human readable description of a trial  MIAPPE V1.1 (DM-4) Investigation description - Human-readable text describing the investigation in more detail.|
|trialName|string|The human readable name of a trial  MIAPPE V1.1 (DM-3) Investigation title - Human-readable string summarising the investigation.|
|trialPUI|string|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


 

+ Parameters
    + searchResultsDbId (Required, ) ... Permanent unique identifier which references the search results
    + page (Optional, ) ... Used to request a specific page of data to be returned.The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.
    + pageSize (Optional, ) ... The size of the pages to be returned. Default is `1000`.
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>




+ Response 102 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "searchResultsDbId": "551ae08c"
    }
}
```

+ Response 200 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "data": [
            {
                "active": true,
                "additionalInfo": {},
                "commonCropName": "Wheat",
                "contacts": [
                    {
                        "contactDbId": "5f4e5509",
                        "email": "bob@bob.com",
                        "instituteName": "The BrAPI Institute",
                        "name": "Bob Robertson",
                        "orcid": "http://orcid.org/0000-0001-8640-1750",
                        "type": "PI"
                    }
                ],
                "datasetAuthorships": [
                    {
                        "datasetPUI": "doi:10.15454/312953986E3",
                        "license": "https://CreativeCommons.org/licenses/by/4.0",
                        "publicReleaseDate": "2018-01-01",
                        "submissionDate": "2018-01-01"
                    }
                ],
                "documentationURL": "https://wiki.brapi.org",
                "endDate": "2018-01-01",
                "externalReferences": [
                    {
                        "referenceID": "doi:10.155454/12349537E12",
                        "referenceSource": "DOI"
                    },
                    {
                        "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                        "referenceSource": "OBO Library"
                    },
                    {
                        "referenceID": "75a50e76",
                        "referenceSource": "Remote Data Collection Upload Tool"
                    }
                ],
                "programDbId": "673f378a",
                "programName": "Tomatillo_Breeding_Program",
                "publications": [
                    {
                        "publicationPUI": "doi:10.15454/312953986E3",
                        "publicationReference": "Selby, BrAPI - An application programming interface for plant breeding applications, Bioinformatics, https://doi.org/10.1093/bioinformatics/190"
                    }
                ],
                "startDate": "2018-01-01",
                "trialDbId": "1883b402",
                "trialDescription": "General drought resistance trial initiated in Peru before duplication in Africa",
                "trialName": "Peru Yield Trial 1",
                "trialPUI": "https://doi.org/101093190"
            }
        ]
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Malformed JSON Request Object\n\nERROR - 2018-10-08T18:15:11Z - Invalid query parameter\n\nERROR - 2018-10-08T18:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - User does not have permission to perform this action"
```

+ Response 404 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - The requested object DbId is not found"
```




### Get - /trials [GET /brapi/v2/trials{?active}{?commonCropName}{?contactDbId}{?programDbId}{?locationDbId}{?searchDateRangeStart}{?searchDateRangeEnd}{?studyDbId}{?trialDbId}{?trialName}{?trialPUI}{?sortBy}{?sortOrder}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Retrieve a filtered list of breeding Trials. A Trial is a collection of Studies



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|active|boolean|Is this trail currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this trial|
|contacts|array[object]|List of contact entities associated with this trial|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|datasetAuthorships|array[object]|License and citation information for the data in this trial|
|datasetPUI|string||
|license|string|MIAPPE V1.1 (DM-7) License - License for the reuse of the data associated with this investigation. The Creative Commons licenses cover most use cases and are recommended.|
|publicReleaseDate|string (date)|MIAPPE V1.1 (DM-6) Public release date - Date of first public release of the dataset presently being described.|
|submissionDate|string (date)|MIAPPE V1.1 (DM-5) Submission date - Date of submission of the dataset presently being described to a host repository.|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date)|The date this trial ends|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|A program identifier to search for|
|programName|string|Human readable name of the program|
|publications|array[object]|MIAPPE V1.1 (DM-9) Associated publication - An identifier for a literature publication where the investigation is described. Use of DOIs is recommended.|
|publicationPUI|string||
|publicationReference|string||
|startDate|string (date)|The date this trial started|
|trialDbId|string|The ID which uniquely identifies a trial  MIAPPE V1.1 (DM-2) Investigation unique ID - Identifier comprising the unique name of the institution/database hosting the submission of the investigation data, and the accession number of the investigation in that institution.|
|trialDescription|string|The human readable description of a trial  MIAPPE V1.1 (DM-4) Investigation description - Human-readable text describing the investigation in more detail.|
|trialName|string|The human readable name of a trial  MIAPPE V1.1 (DM-3) Investigation title - Human-readable string summarising the investigation.|
|trialPUI|string|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


 

+ Parameters
    + active (Optional, ) ... Filter active status true/false.
    + commonCropName (Optional, ) ... Common name for the crop associated with this trial
    + contactDbId (Optional, ) ... Contact entities associated with this trial
    + programDbId (Optional, ) ... Program filter to only return trials associated with given program id.
    + locationDbId (Optional, ) ... Filter by location
    + searchDateRangeStart (Optional, ) ... The start of the overlapping search date range. `searchDateRangeStart` must be before `searchDateRangeEnd`.Return a Trial entity if any of the following cases are true- `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is null - `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is after `trial.startDate`- `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is null- `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is before `trial.endDate`
    + searchDateRangeEnd (Optional, ) ... The start of the overlapping search date range. `searchDateRangeStart` must be before `searchDateRangeEnd`.Return a Trial entity if any of the following cases are true- `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is null - `searchDateRangeStart` is before `trial.endDate` AND `searchDateRangeEnd` is after `trial.startDate`- `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is null- `searchDateRangeEnd` is after `trial.startDate` AND `searchDateRangeStart` is before `trial.endDate`
    + studyDbId (Optional, ) ... Filter by connected studyDbId
    + trialDbId (Optional, ) ... Filter by trialDbId
    + trialName (Optional, ) ... Filter by trial name
    + trialPUI (Optional, ) ... Filter by trial PUI
    + sortBy (Optional, ) ... Sort order. Name of the field to sort by.
    + sortOrder (Optional, ) ... Sort order direction: asc/desc
    + externalReferenceID (Optional, ) ... Search for Germplasm by an external reference
    + externalReferenceSource (Optional, ) ... Search for Germplasm by an external reference
    + page (Optional, ) ... Used to request a specific page of data to be returned.The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.
    + pageSize (Optional, ) ... The size of the pages to be returned. Default is `1000`.
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>




+ Response 200 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "data": [
            {
                "active": true,
                "additionalInfo": {},
                "commonCropName": "Wheat",
                "contacts": [
                    {
                        "contactDbId": "5f4e5509",
                        "email": "bob@bob.com",
                        "instituteName": "The BrAPI Institute",
                        "name": "Bob Robertson",
                        "orcid": "http://orcid.org/0000-0001-8640-1750",
                        "type": "PI"
                    }
                ],
                "datasetAuthorships": [
                    {
                        "datasetPUI": "doi:10.15454/312953986E3",
                        "license": "https://CreativeCommons.org/licenses/by/4.0",
                        "publicReleaseDate": "2018-01-01",
                        "submissionDate": "2018-01-01"
                    }
                ],
                "documentationURL": "https://wiki.brapi.org",
                "endDate": "2018-01-01",
                "externalReferences": [
                    {
                        "referenceID": "doi:10.155454/12349537E12",
                        "referenceSource": "DOI"
                    },
                    {
                        "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                        "referenceSource": "OBO Library"
                    },
                    {
                        "referenceID": "75a50e76",
                        "referenceSource": "Remote Data Collection Upload Tool"
                    }
                ],
                "programDbId": "673f378a",
                "programName": "Tomatillo_Breeding_Program",
                "publications": [
                    {
                        "publicationPUI": "doi:10.15454/312953986E3",
                        "publicationReference": "Selby, BrAPI - An application programming interface for plant breeding applications, Bioinformatics, https://doi.org/10.1093/bioinformatics/190"
                    }
                ],
                "startDate": "2018-01-01",
                "trialDbId": "1883b402",
                "trialDescription": "General drought resistance trial initiated in Peru before duplication in Africa",
                "trialName": "Peru Yield Trial 1",
                "trialPUI": "https://doi.org/101093190"
            }
        ]
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Malformed JSON Request Object\n\nERROR - 2018-10-08T18:15:11Z - Invalid query parameter\n\nERROR - 2018-10-08T18:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - User does not have permission to perform this action"
```




### Post - /trials [POST /brapi/v2/trials]

Create new breeding Trials. A Trial represents a collection of related Studies. `trialDbId` is generated by the server.

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|active|boolean|Is this trail currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this trial|
|contacts|array[object]|List of contact entities associated with this trial|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|datasetAuthorships|array[object]|License and citation information for the data in this trial|
|datasetPUI|string||
|license|string|MIAPPE V1.1 (DM-7) License - License for the reuse of the data associated with this investigation. The Creative Commons licenses cover most use cases and are recommended.|
|publicReleaseDate|string (date)|MIAPPE V1.1 (DM-6) Public release date - Date of first public release of the dataset presently being described.|
|submissionDate|string (date)|MIAPPE V1.1 (DM-5) Submission date - Date of submission of the dataset presently being described to a host repository.|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date)|The date this trial ends|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|A program identifier to search for|
|programName|string|Human readable name of the program|
|publications|array[object]|MIAPPE V1.1 (DM-9) Associated publication - An identifier for a literature publication where the investigation is described. Use of DOIs is recommended.|
|publicationPUI|string||
|publicationReference|string||
|startDate|string (date)|The date this trial started|
|trialDescription|string|The human readable description of a trial  MIAPPE V1.1 (DM-4) Investigation description - Human-readable text describing the investigation in more detail.|
|trialName|string|The human readable name of a trial  MIAPPE V1.1 (DM-3) Investigation title - Human-readable string summarising the investigation.|
|trialPUI|string|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|active|boolean|Is this trail currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this trial|
|contacts|array[object]|List of contact entities associated with this trial|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|datasetAuthorships|array[object]|License and citation information for the data in this trial|
|datasetPUI|string||
|license|string|MIAPPE V1.1 (DM-7) License - License for the reuse of the data associated with this investigation. The Creative Commons licenses cover most use cases and are recommended.|
|publicReleaseDate|string (date)|MIAPPE V1.1 (DM-6) Public release date - Date of first public release of the dataset presently being described.|
|submissionDate|string (date)|MIAPPE V1.1 (DM-5) Submission date - Date of submission of the dataset presently being described to a host repository.|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date)|The date this trial ends|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|A program identifier to search for|
|programName|string|Human readable name of the program|
|publications|array[object]|MIAPPE V1.1 (DM-9) Associated publication - An identifier for a literature publication where the investigation is described. Use of DOIs is recommended.|
|publicationPUI|string||
|publicationReference|string||
|startDate|string (date)|The date this trial started|
|trialDbId|string|The ID which uniquely identifies a trial  MIAPPE V1.1 (DM-2) Investigation unique ID - Identifier comprising the unique name of the institution/database hosting the submission of the investigation data, and the accession number of the investigation in that institution.|
|trialDescription|string|The human readable description of a trial  MIAPPE V1.1 (DM-4) Investigation description - Human-readable text describing the investigation in more detail.|
|trialName|string|The human readable name of a trial  MIAPPE V1.1 (DM-3) Investigation title - Human-readable string summarising the investigation.|
|trialPUI|string|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "active": true,
        "additionalInfo": {},
        "commonCropName": "Wheat",
        "contacts": [
            {
                "contactDbId": "5f4e5509",
                "email": "bob@bob.com",
                "instituteName": "The BrAPI Institute",
                "name": "Bob Robertson",
                "orcid": "http://orcid.org/0000-0001-8640-1750",
                "type": "PI"
            }
        ],
        "datasetAuthorships": [
            {
                "datasetPUI": "doi:10.15454/312953986E3",
                "license": "https://CreativeCommons.org/licenses/by/4.0",
                "publicReleaseDate": "2018-01-01",
                "submissionDate": "2018-01-01"
            }
        ],
        "documentationURL": "https://wiki.brapi.org",
        "endDate": "2018-01-01",
        "externalReferences": [
            {
                "referenceID": "doi:10.155454/12349537E12",
                "referenceSource": "DOI"
            },
            {
                "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                "referenceSource": "OBO Library"
            },
            {
                "referenceID": "75a50e76",
                "referenceSource": "Remote Data Collection Upload Tool"
            }
        ],
        "programDbId": "673f378a",
        "programName": "Tomatillo_Breeding_Program",
        "publications": [
            {
                "publicationPUI": "doi:10.15454/312953986E3",
                "publicationReference": "Selby, BrAPI - An application programming interface for plant breeding applications, Bioinformatics, https://doi.org/10.1093/bioinformatics/190"
            }
        ],
        "startDate": "2018-01-01",
        "trialDescription": "General drought resistance trial initiated in Peru before duplication in Africa",
        "trialName": "Peru Yield Trial 1",
        "trialPUI": "https://doi.org/101093190"
    }
]
```



+ Response 200 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "data": [
            {
                "active": true,
                "additionalInfo": {},
                "commonCropName": "Wheat",
                "contacts": [
                    {
                        "contactDbId": "5f4e5509",
                        "email": "bob@bob.com",
                        "instituteName": "The BrAPI Institute",
                        "name": "Bob Robertson",
                        "orcid": "http://orcid.org/0000-0001-8640-1750",
                        "type": "PI"
                    }
                ],
                "datasetAuthorships": [
                    {
                        "datasetPUI": "doi:10.15454/312953986E3",
                        "license": "https://CreativeCommons.org/licenses/by/4.0",
                        "publicReleaseDate": "2018-01-01",
                        "submissionDate": "2018-01-01"
                    }
                ],
                "documentationURL": "https://wiki.brapi.org",
                "endDate": "2018-01-01",
                "externalReferences": [
                    {
                        "referenceID": "doi:10.155454/12349537E12",
                        "referenceSource": "DOI"
                    },
                    {
                        "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                        "referenceSource": "OBO Library"
                    },
                    {
                        "referenceID": "75a50e76",
                        "referenceSource": "Remote Data Collection Upload Tool"
                    }
                ],
                "programDbId": "673f378a",
                "programName": "Tomatillo_Breeding_Program",
                "publications": [
                    {
                        "publicationPUI": "doi:10.15454/312953986E3",
                        "publicationReference": "Selby, BrAPI - An application programming interface for plant breeding applications, Bioinformatics, https://doi.org/10.1093/bioinformatics/190"
                    }
                ],
                "startDate": "2018-01-01",
                "trialDbId": "1883b402",
                "trialDescription": "General drought resistance trial initiated in Peru before duplication in Africa",
                "trialName": "Peru Yield Trial 1",
                "trialPUI": "https://doi.org/101093190"
            }
        ]
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Malformed JSON Request Object\n\nERROR - 2018-10-08T18:15:11Z - Invalid query parameter\n\nERROR - 2018-10-08T18:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - User does not have permission to perform this action"
```




### Get - /trials/{trialDbId} [GET /brapi/v2/trials/{trialDbId}]

Get the details of a specific Trial



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|active|boolean|Is this study currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this study|
|contacts|array[object]|List of contact entities associated with this study|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|culturalPractices|string|MIAPPE V1.1 (DM-28) Cultural practices - General description of the cultural practices of the study.|
|dataLinks|array[object]|List of links to extra data files associated with this study. Extra data could include notes, images, and reference data.|
|dataFormat|string|The structure of the data within a file. For example - VCF, table, image archive, multispectral image archives in EDAM ontology (used in Galaxy)|
|description|string|The general description of this data link|
|fileFormat|string|The MIME type of the file (ie text/csv, application/excel, application/zip).|
|name|string|The name of the external data link  MIAPPE V1.1 (DM-38) Data file description - Description of the format of the data file. May be a standard file format name, or a description of organization of the data in a tabular file.|
|provenance|string|The description of the origin or ownership of this linked data. Could be a formal reference to software, method, or workflow.|
|scientificType|string|The general type of data. For example- Genotyping, Phenotyping raw data, Phenotyping reduced data, Environmental, etc|
|url|string (uri)|MIAPPE V1.1 (DM-37) Data file link - Link to the data file (or digital object) in a public database or in a persistent institutional repository; or identifier of the data file when submitted together with the MIAPPE submission.|
|version|string|MIAPPE V1.1 (DM-39) Data file version - The version of the dataset (the actual data).|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date-time)|The date the study ends  MIAPPE V1.1 (DM-15) End date of study - Date and, if relevant, time when the experiment ended|
|environmentParameters|array[object]|Environmental parameters that were kept constant throughout the study and did not change between observation units.|
|description|string|Human-readable value of the environment parameter (defined above) constant within the experiment|
|parameterName|string|Name of the environment parameter constant within the experiment|
|parameterPUI|string|URI pointing to an ontology class for the parameter|
|unit|string|Unit of the value for this parameter|
|unitPUI|string|URI pointing to an ontology class for the unit|
|value|string|Numerical or categorical value|
|valuePUI|string|URI pointing to an ontology class for the parameter value|
|experimentalDesign|object|The experimental and statistical design full description plus a category PUI taken from crop research ontology or agronomy ontology|
|PUI|string|MIAPPE V1.1 (DM-23) Type of experimental design - Type of experimental  design of the study, in the form of an accession number from the Crop Ontology.|
|description|string|MIAPPE V1.1 (DM-22) Description of the experimental design - Short description of the experimental design, possibly including statistical design. In specific cases, e.g. legacy datasets or data computed from several studies, the experimental design can be "unknown"/"NA", "aggregated/reduced data", or simply 'none'.|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthFacility|object|Short description of the facility in which the study was carried out.|
|PUI|string|MIAPPE V1.1 (DM-27) Type of growth facility - Type of growth facility in which the study was carried out, in the form of an accession number from the Crop Ontology.|
|description|string|MIAPPE V1.1 (DM-26) Description of growth facility - Short description of the facility in which the study was carried out.|
|lastUpdate|object|The date and time when this study was last modified|
|timestamp|string (date-time)||
|version|string||
|license|string|The usage license associated with the study data|
|locationDbId|string|The unique identifier for a Location|
|locationName|string|A human readable name for this location  MIAPPE V1.1 (DM-18) Experimental site name - The name of the natural site, experimental field, greenhouse, phenotyping facility, etc. where the experiment took place.|
|observationLevels|array[object]|Observation levels indicate the granularity level at which the measurements are taken. `levelName` defines the level, `levelOrder` defines where that level exists in the hierarchy of levels. `levelOrder`s lower numbers are at the top of the hierarchy (ie field > 0) and higher numbers are at the bottom of the hierarchy (ie plant > 6). |
|levelName|string|A name for this level|
|levelOrder|integer|`levelOrder` defines where that level exists in the hierarchy of levels. `levelOrder`'s lower numbers are at the top of the hierarchy (ie field -> 1) and higher numbers are at the bottom of the hierarchy (ie plant -> 9).|
|observationUnitsDescription|string|MIAPPE V1.1 (DM-25) Observation unit description - General description of the observation units in the study.|
|seasons|array[string]|List of seasons over which this study was performed.|
|startDate|string (date-time)|The date this study started  MIAPPE V1.1 (DM-14) Start date of study - Date and, if relevant, time when the experiment started|
|studyCode|string|A short human readable code for a study|
|studyDbId|string|The ID which uniquely identifies a study within the given database server  MIAPPE V1.1 (DM-11) Study unique ID - Unique identifier comprising the name or identifier for the institution/database hosting the submission of the study data, and the identifier of the study in that institution.|
|studyDescription|string|The description of this study  MIAPPE V1.1 (DM-13) Study description - Human-readable text describing the study|
|studyName|string|The human readable name for a study  MIAPPE V1.1 (DM-12) Study title - Human-readable text summarising the study|
|studyPUI|string|A permanent unique identifier associated with this study data. For example, a URI or DOI|
|studyType|string|The type of study being performed. ex. "Yield Trial", etc|
|trialDbId|string|The ID which uniquely identifies a trial|
|trialName|string|The human readable name of a trial|


 

+ Parameters
    + trialDbId (Required, ) ... The internal trialDbId
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>




+ Response 200 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "active": true,
        "additionalInfo": {},
        "commonCropName": "Grape",
        "contacts": [
            {
                "contactDbId": "5f4e5509",
                "email": "bob@bob.com",
                "instituteName": "The BrAPI Institute",
                "name": "Bob Robertson",
                "orcid": "http://orcid.org/0000-0001-8640-1750",
                "type": "PI"
            }
        ],
        "culturalPractices": "Irrigation was applied according needs during summer to prevent water stress.",
        "dataLinks": [
            {
                "dataFormat": "Image Archive",
                "description": "Raw drone images collected for this study",
                "fileFormat": "application/zip",
                "name": "image-archive.zip",
                "provenance": "Image Processing Pipeline, built at the University of Antarctica: https://github.com/antarctica/pipeline",
                "scientificType": "Environmental",
                "url": "https://brapi.org/image-archive.zip",
                "version": "1.0.3"
            }
        ],
        "documentationURL": "https://wiki.brapi.org",
        "endDate": "2018-01-01T14:47:23-0600",
        "environmentParameters": [
            {
                "description": "the soil type was clay",
                "parameterName": "soil type",
                "parameterPUI": "PECO:0007155",
                "unit": "pH",
                "unitPUI": "PECO:0007059",
                "value": "clay soil",
                "valuePUI": "ENVO:00002262"
            }
        ],
        "experimentalDesign": {
            "PUI": "CO_715:0000145",
            "description": "Lines were repeated twice at each location using a complete block design. In order to limit competition effects, each block was organized into four sub-blocks corresponding to earliest groups based on a prior information."
        },
        "externalReferences": [
            {
                "referenceID": "doi:10.155454/12349537E12",
                "referenceSource": "DOI"
            },
            {
                "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                "referenceSource": "OBO Library"
            },
            {
                "referenceID": "75a50e76",
                "referenceSource": "Remote Data Collection Upload Tool"
            }
        ],
        "growthFacility": {
            "PUI": "CO_715:0000162",
            "description": "field environment condition, greenhouse"
        },
        "lastUpdate": {
            "timestamp": "2018-01-01T14:47:23-0600",
            "version": "1.2.3"
        },
        "license": "MIT License",
        "locationDbId": "3cfdd67d",
        "locationName": "Location 1",
        "observationLevels": [
            {
                "levelName": "field",
                "levelOrder": 0
            },
            {
                "levelName": "block",
                "levelOrder": 1
            },
            {
                "levelName": "plot",
                "levelOrder": 2
            }
        ],
        "observationUnitsDescription": "Observation units consisted in individual plots themselves consisting of a row of 15 plants at a density of approximately six plants per square meter.",
        "seasons": [
            "Spring_2018"
        ],
        "startDate": "2018-01-01T14:47:23-0600",
        "studyCode": "Grape_Yield_Spring_2018",
        "studyDbId": "175ac75a",
        "studyDescription": "This is a yield study for Spring 2018",
        "studyName": "INRA's Walnut Genetic Resources Observation at Kenya",
        "studyPUI": "doi:10.155454/12349537312",
        "studyType": "Phenotyping",
        "trialDbId": "48b327ea",
        "trialName": "Grape_Yield_Trial"
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Malformed JSON Request Object\n\nERROR - 2018-10-08T18:15:11Z - Invalid query parameter\n\nERROR - 2018-10-08T18:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - User does not have permission to perform this action"
```

+ Response 404 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - The requested object DbId is not found"
```




### Put - /trials/{trialDbId} [PUT /brapi/v2/trials/{trialDbId}]

Update the details of an existing Trial

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|active|boolean|Is this trail currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this trial|
|contacts|array[object]|List of contact entities associated with this trial|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|datasetAuthorships|array[object]|License and citation information for the data in this trial|
|datasetPUI|string||
|license|string|MIAPPE V1.1 (DM-7) License - License for the reuse of the data associated with this investigation. The Creative Commons licenses cover most use cases and are recommended.|
|publicReleaseDate|string (date)|MIAPPE V1.1 (DM-6) Public release date - Date of first public release of the dataset presently being described.|
|submissionDate|string (date)|MIAPPE V1.1 (DM-5) Submission date - Date of submission of the dataset presently being described to a host repository.|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date)|The date this trial ends|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|A program identifier to search for|
|programName|string|Human readable name of the program|
|publications|array[object]|MIAPPE V1.1 (DM-9) Associated publication - An identifier for a literature publication where the investigation is described. Use of DOIs is recommended.|
|publicationPUI|string||
|publicationReference|string||
|startDate|string (date)|The date this trial started|
|trialDescription|string|The human readable description of a trial  MIAPPE V1.1 (DM-4) Investigation description - Human-readable text describing the investigation in more detail.|
|trialName|string|The human readable name of a trial  MIAPPE V1.1 (DM-3) Investigation title - Human-readable string summarising the investigation.|
|trialPUI|string|A permanent identifier for a trial. Could be DOI or other URI formatted identifier.|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|active|boolean|Is this study currently active|
|additionalInfo|object|Additional arbitrary info|
|commonCropName|string|Common name for the crop associated with this study|
|contacts|array[object]|List of contact entities associated with this study|
|contactDbId|string|The ID which uniquely identifies this contact  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|email|string|The contacts email address  MIAPPE V1.1 (DM-32) Person email - The electronic mail address of the person.|
|instituteName|string|The name of the institution which this contact is part of  MIAPPE V1.1 (DM-35) Person affiliation - The institution the person belongs to|
|name|string|The full name of this contact person  MIAPPE V1.1 (DM-31) Person name - The name of the person (either full name or as used in scientific publications)|
|orcid|string|The Open Researcher and Contributor ID for this contact person (orcid.org)  MIAPPE V1.1 (DM-33) Person ID - An identifier for the data submitter. If that submitter is an individual, ORCID identifiers are recommended.|
|type|string|The type of person this contact represents (ex: Coordinator, Scientist, PI, etc.)  MIAPPE V1.1 (DM-34) Person role - Type of contribution of the person to the investigation|
|culturalPractices|string|MIAPPE V1.1 (DM-28) Cultural practices - General description of the cultural practices of the study.|
|dataLinks|array[object]|List of links to extra data files associated with this study. Extra data could include notes, images, and reference data.|
|dataFormat|string|The structure of the data within a file. For example - VCF, table, image archive, multispectral image archives in EDAM ontology (used in Galaxy)|
|description|string|The general description of this data link|
|fileFormat|string|The MIME type of the file (ie text/csv, application/excel, application/zip).|
|name|string|The name of the external data link  MIAPPE V1.1 (DM-38) Data file description - Description of the format of the data file. May be a standard file format name, or a description of organization of the data in a tabular file.|
|provenance|string|The description of the origin or ownership of this linked data. Could be a formal reference to software, method, or workflow.|
|scientificType|string|The general type of data. For example- Genotyping, Phenotyping raw data, Phenotyping reduced data, Environmental, etc|
|url|string (uri)|MIAPPE V1.1 (DM-37) Data file link - Link to the data file (or digital object) in a public database or in a persistent institutional repository; or identifier of the data file when submitted together with the MIAPPE submission.|
|version|string|MIAPPE V1.1 (DM-39) Data file version - The version of the dataset (the actual data).|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|endDate|string (date-time)|The date the study ends  MIAPPE V1.1 (DM-15) End date of study - Date and, if relevant, time when the experiment ended|
|environmentParameters|array[object]|Environmental parameters that were kept constant throughout the study and did not change between observation units.|
|description|string|Human-readable value of the environment parameter (defined above) constant within the experiment|
|parameterName|string|Name of the environment parameter constant within the experiment|
|parameterPUI|string|URI pointing to an ontology class for the parameter|
|unit|string|Unit of the value for this parameter|
|unitPUI|string|URI pointing to an ontology class for the unit|
|value|string|Numerical or categorical value|
|valuePUI|string|URI pointing to an ontology class for the parameter value|
|experimentalDesign|object|The experimental and statistical design full description plus a category PUI taken from crop research ontology or agronomy ontology|
|PUI|string|MIAPPE V1.1 (DM-23) Type of experimental design - Type of experimental  design of the study, in the form of an accession number from the Crop Ontology.|
|description|string|MIAPPE V1.1 (DM-22) Description of the experimental design - Short description of the experimental design, possibly including statistical design. In specific cases, e.g. legacy datasets or data computed from several studies, the experimental design can be "unknown"/"NA", "aggregated/reduced data", or simply 'none'.|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthFacility|object|Short description of the facility in which the study was carried out.|
|PUI|string|MIAPPE V1.1 (DM-27) Type of growth facility - Type of growth facility in which the study was carried out, in the form of an accession number from the Crop Ontology.|
|description|string|MIAPPE V1.1 (DM-26) Description of growth facility - Short description of the facility in which the study was carried out.|
|lastUpdate|object|The date and time when this study was last modified|
|timestamp|string (date-time)||
|version|string||
|license|string|The usage license associated with the study data|
|locationDbId|string|The unique identifier for a Location|
|locationName|string|A human readable name for this location  MIAPPE V1.1 (DM-18) Experimental site name - The name of the natural site, experimental field, greenhouse, phenotyping facility, etc. where the experiment took place.|
|observationLevels|array[object]|Observation levels indicate the granularity level at which the measurements are taken. `levelName` defines the level, `levelOrder` defines where that level exists in the hierarchy of levels. `levelOrder`s lower numbers are at the top of the hierarchy (ie field > 0) and higher numbers are at the bottom of the hierarchy (ie plant > 6). |
|levelName|string|A name for this level|
|levelOrder|integer|`levelOrder` defines where that level exists in the hierarchy of levels. `levelOrder`'s lower numbers are at the top of the hierarchy (ie field -> 1) and higher numbers are at the bottom of the hierarchy (ie plant -> 9).|
|observationUnitsDescription|string|MIAPPE V1.1 (DM-25) Observation unit description - General description of the observation units in the study.|
|seasons|array[string]|List of seasons over which this study was performed.|
|startDate|string (date-time)|The date this study started  MIAPPE V1.1 (DM-14) Start date of study - Date and, if relevant, time when the experiment started|
|studyCode|string|A short human readable code for a study|
|studyDbId|string|The ID which uniquely identifies a study within the given database server  MIAPPE V1.1 (DM-11) Study unique ID - Unique identifier comprising the name or identifier for the institution/database hosting the submission of the study data, and the identifier of the study in that institution.|
|studyDescription|string|The description of this study  MIAPPE V1.1 (DM-13) Study description - Human-readable text describing the study|
|studyName|string|The human readable name for a study  MIAPPE V1.1 (DM-12) Study title - Human-readable text summarising the study|
|studyPUI|string|A permanent unique identifier associated with this study data. For example, a URI or DOI|
|studyType|string|The type of study being performed. ex. "Yield Trial", etc|
|trialDbId|string|The ID which uniquely identifies a trial|
|trialName|string|The human readable name of a trial|


 

+ Parameters
    + trialDbId (Required, ) ... The internal trialDbId
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "active": true,
    "additionalInfo": {},
    "commonCropName": "Wheat",
    "contacts": [
        {
            "contactDbId": "5f4e5509",
            "email": "bob@bob.com",
            "instituteName": "The BrAPI Institute",
            "name": "Bob Robertson",
            "orcid": "http://orcid.org/0000-0001-8640-1750",
            "type": "PI"
        }
    ],
    "datasetAuthorships": [
        {
            "datasetPUI": "doi:10.15454/312953986E3",
            "license": "https://CreativeCommons.org/licenses/by/4.0",
            "publicReleaseDate": "2018-01-01",
            "submissionDate": "2018-01-01"
        }
    ],
    "documentationURL": "https://wiki.brapi.org",
    "endDate": "2018-01-01",
    "externalReferences": [
        {
            "referenceID": "doi:10.155454/12349537E12",
            "referenceSource": "DOI"
        },
        {
            "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
            "referenceSource": "OBO Library"
        },
        {
            "referenceID": "75a50e76",
            "referenceSource": "Remote Data Collection Upload Tool"
        }
    ],
    "programDbId": "673f378a",
    "programName": "Tomatillo_Breeding_Program",
    "publications": [
        {
            "publicationPUI": "doi:10.15454/312953986E3",
            "publicationReference": "Selby, BrAPI - An application programming interface for plant breeding applications, Bioinformatics, https://doi.org/10.1093/bioinformatics/190"
        }
    ],
    "startDate": "2018-01-01",
    "trialDescription": "General drought resistance trial initiated in Peru before duplication in Africa",
    "trialName": "Peru Yield Trial 1",
    "trialPUI": "https://doi.org/101093190"
}
```



+ Response 200 (application/json)
```
{
    "@context": [
        "https://brapi.org/jsonld/context/metadata.jsonld"
    ],
    "metadata": {
        "datafiles": [
            {
                "fileDescription": "This is an Excel data file",
                "fileMD5Hash": "c2365e900c81a89cf74d83dab60df146",
                "fileName": "datafile.xlsx",
                "fileSize": 4398,
                "fileType": "application/vnd.ms-excel",
                "fileURL": "https://wiki.brapi.org/examples/datafile.xlsx"
            }
        ],
        "pagination": {
            "currentPage": 0,
            "pageSize": 1000,
            "totalCount": 10,
            "totalPages": 1
        },
        "status": [
            {
                "message": "Request accepted, response successful",
                "messageType": "INFO"
            }
        ]
    },
    "result": {
        "active": true,
        "additionalInfo": {},
        "commonCropName": "Grape",
        "contacts": [
            {
                "contactDbId": "5f4e5509",
                "email": "bob@bob.com",
                "instituteName": "The BrAPI Institute",
                "name": "Bob Robertson",
                "orcid": "http://orcid.org/0000-0001-8640-1750",
                "type": "PI"
            }
        ],
        "culturalPractices": "Irrigation was applied according needs during summer to prevent water stress.",
        "dataLinks": [
            {
                "dataFormat": "Image Archive",
                "description": "Raw drone images collected for this study",
                "fileFormat": "application/zip",
                "name": "image-archive.zip",
                "provenance": "Image Processing Pipeline, built at the University of Antarctica: https://github.com/antarctica/pipeline",
                "scientificType": "Environmental",
                "url": "https://brapi.org/image-archive.zip",
                "version": "1.0.3"
            }
        ],
        "documentationURL": "https://wiki.brapi.org",
        "endDate": "2018-01-01T14:47:23-0600",
        "environmentParameters": [
            {
                "description": "the soil type was clay",
                "parameterName": "soil type",
                "parameterPUI": "PECO:0007155",
                "unit": "pH",
                "unitPUI": "PECO:0007059",
                "value": "clay soil",
                "valuePUI": "ENVO:00002262"
            }
        ],
        "experimentalDesign": {
            "PUI": "CO_715:0000145",
            "description": "Lines were repeated twice at each location using a complete block design. In order to limit competition effects, each block was organized into four sub-blocks corresponding to earliest groups based on a prior information."
        },
        "externalReferences": [
            {
                "referenceID": "doi:10.155454/12349537E12",
                "referenceSource": "DOI"
            },
            {
                "referenceID": "http://purl.obolibrary.org/obo/ro.owl",
                "referenceSource": "OBO Library"
            },
            {
                "referenceID": "75a50e76",
                "referenceSource": "Remote Data Collection Upload Tool"
            }
        ],
        "growthFacility": {
            "PUI": "CO_715:0000162",
            "description": "field environment condition, greenhouse"
        },
        "lastUpdate": {
            "timestamp": "2018-01-01T14:47:23-0600",
            "version": "1.2.3"
        },
        "license": "MIT License",
        "locationDbId": "3cfdd67d",
        "locationName": "Location 1",
        "observationLevels": [
            {
                "levelName": "field",
                "levelOrder": 0
            },
            {
                "levelName": "block",
                "levelOrder": 1
            },
            {
                "levelName": "plot",
                "levelOrder": 2
            }
        ],
        "observationUnitsDescription": "Observation units consisted in individual plots themselves consisting of a row of 15 plants at a density of approximately six plants per square meter.",
        "seasons": [
            "Spring_2018"
        ],
        "startDate": "2018-01-01T14:47:23-0600",
        "studyCode": "Grape_Yield_Spring_2018",
        "studyDbId": "175ac75a",
        "studyDescription": "This is a yield study for Spring 2018",
        "studyName": "INRA's Walnut Genetic Resources Observation at Kenya",
        "studyPUI": "doi:10.155454/12349537312",
        "studyType": "Phenotyping",
        "trialDbId": "48b327ea",
        "trialName": "Grape_Yield_Trial"
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Malformed JSON Request Object\n\nERROR - 2018-10-08T18:15:11Z - Invalid query parameter\n\nERROR - 2018-10-08T18:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - User does not have permission to perform this action"
```

+ Response 404 (application/json)
```
"ERROR - 2018-10-08T18:15:11Z - The requested object DbId is not found"
```
