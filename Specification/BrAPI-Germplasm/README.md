FORMAT: 1A

# BrAPI Germplasm

The Breeding API (BrAPI) is a Standardized REST ful Web Service API Specification for communicating Plant Breeding Data. BrAPI allows for easy data sharing between databases and tools involved in plant breeding.

### General Reference Documentation
- [URL Structure](https://github.com/plantbreeding/API/blob/master/Specification/GeneralInfo/URL_Structure.md)
- [Response Structure](https://github.com/plantbreeding/API/blob/master/Specification/GeneralInfo/Response_Structure.md)
- [Date/Time Encoding](https://github.com/plantbreeding/API/blob/master/Specification/GeneralInfo/Date_Time_Encoding.md)
- [Location Encoding](https://github.com/plantbreeding/API/blob/master/Specification/GeneralInfo/Location_Encoding.md)
- [Error Handling](https://github.com/plantbreeding/API/blob/master/Specification/GeneralInfo/Error_Handling.md)
- [Search Services](https://github.com/plantbreeding/API/blob/master/Specification/GeneralInfo/Search_Services.md)



### BrAPI Core
The BrAPI Core module contains high level entities used for organization and management. This includes Programs, Trials, Studies, Locations, People, and Lists

V2.0 - [GitHub](https://github.com/plantbreeding/API/tree/brapi-v2-dev/Specification/BrAPI-Core) - [SwaggerHub](https://app.swaggerhub.com/apis/PlantBreedingAPI/BrAPI-Core) - [Apiary](https://brapicore.docs.apiary.io)


### BrAPI Phenotyping
The BrAPI Phenotyping module contains entities related to phenotypic observations. This includes Observation Units, Observations, Observation Variables, Traits, Scales, Methods, and Images

V2.0 - [GitHub](https://github.com/plantbreeding/API/tree/brapi-v2-dev/Specification/BrAPI-Phenotyping) - [SwaggerHub](https://app.swaggerhub.com/apis/PlantBreedingAPI/BrAPI-Phenotyping) - [Apiary](https://brapiphenotyping.docs.apiary.io)


### BrAPI Genotyping
The BrAPI Genotyping module contains entities related to genotyping analysis. This includes Samples, Markers, Variant Sets, Variants, Call Sets, Calls, References, Reads, and Vendor Orders

V2.0 - [GitHub](https://github.com/plantbreeding/API/tree/brapi-v2-dev/Specification/BrAPI-Genotyping) - [SwaggerHub](https://app.swaggerhub.com/apis/PlantBreedingAPI/BrAPI-Genotyping) - [Apiary](https://brapigenotyping.docs.apiary.io)


### **BrAPI Germplasm**
The **BrAPI Germplasm** module contains entities related to germplasm management. This includes Germplasm, Germplasm Attributes, Seed Lots, Crosses, Pedigree, and Progeny

V2.0 - [GitHub](https://github.com/plantbreeding/API/tree/brapi-v2-dev/Specification/BrAPI-Germplasm) - [SwaggerHub](https://app.swaggerhub.com/apis/PlantBreedingAPI/BrAPI-Germplasm) - [Apiary](https://brapigermplasm.docs.apiary.io)


# Group Crosses






### Get - /crosses [GET /brapi/v2/crosses{?crossingProjectDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Get a filtered list of Cross entities.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|crossAttributes|array[object]|Set of custom attributes associated with a cross|
|crossAttributeName|string|the human readable name of a cross attribute|
|crossAttributeValue|string|the value of a cross attribute|
|crossDbId|string|the unique identifier for a cross|
|crossName|string|the human readable name for a cross|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|pollinationTimeStamp|string (date-time)|the timestamp when the pollination took place|


 

+ Parameters
    + crossingProjectDbId (Optional, ) ... Search for Crossing Projects with this unique id
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
                "additionalInfo": {},
                "crossAttributes": [
                    {
                        "crossAttributeName": "Humidity Percentage",
                        "crossAttributeValue": 45
                    }
                ],
                "crossDbId": "d105fd6f",
                "crossName": "my_Ibadan_Crosses_2018_01",
                "crossType": "BIPARENTAL",
                "crossingProjectDbId": "696d7c92",
                "crossingProjectName": "my_Ibadan_Crosses_2018",
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
                "parent1": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "parent2": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "pollinationTimeStamp": "2018-01-01T14:47:23-0600"
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




### Post - /crosses [POST /brapi/v2/crosses]

Create new Cross entities on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|crossAttributes|array[object]|Set of custom attributes associated with a cross|
|crossAttributeName|string|the human readable name of a cross attribute|
|crossAttributeValue|string|the value of a cross attribute|
|crossName|string|the human readable name for a cross|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|pollinationTimeStamp|string (date-time)|the timestamp when the pollination took place|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|crossAttributes|array[object]|Set of custom attributes associated with a cross|
|crossAttributeName|string|the human readable name of a cross attribute|
|crossAttributeValue|string|the value of a cross attribute|
|crossDbId|string|the unique identifier for a cross|
|crossName|string|the human readable name for a cross|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|pollinationTimeStamp|string (date-time)|the timestamp when the pollination took place|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "additionalInfo": {},
        "crossAttributes": [
            {
                "crossAttributeName": "Humidity Percentage",
                "crossAttributeValue": 45
            }
        ],
        "crossName": "my_Ibadan_Crosses_2018_01",
        "crossType": "BIPARENTAL",
        "crossingProjectDbId": "696d7c92",
        "crossingProjectName": "my_Ibadan_Crosses_2018",
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
        "parent1": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": [
                "MALE",
                "FEMALE",
                "SELF",
                "POPULATION"
            ]
        },
        "parent2": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": [
                "MALE",
                "FEMALE",
                "SELF",
                "POPULATION"
            ]
        },
        "pollinationTimeStamp": "2018-01-01T14:47:23-0600"
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
                "additionalInfo": {},
                "crossAttributes": [
                    {
                        "crossAttributeName": "Humidity Percentage",
                        "crossAttributeValue": 45
                    }
                ],
                "crossDbId": "d105fd6f",
                "crossName": "my_Ibadan_Crosses_2018_01",
                "crossType": "BIPARENTAL",
                "crossingProjectDbId": "696d7c92",
                "crossingProjectName": "my_Ibadan_Crosses_2018",
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
                "parent1": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "parent2": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "pollinationTimeStamp": "2018-01-01T14:47:23-0600"
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




### Put - /crosses [PUT /brapi/v2/crosses]

Update existing Cross entities on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|crossAttributes|array[object]|Set of custom attributes associated with a cross|
|crossAttributeName|string|the human readable name of a cross attribute|
|crossAttributeValue|string|the value of a cross attribute|
|crossDbId|string|the unique identifier for a cross|
|crossName|string|the human readable name for a cross|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|pollinationTimeStamp|string (date-time)|the timestamp when the pollination took place|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "d105fd6f": {
        "additionalInfo": {},
        "crossAttributes": [
            {
                "crossAttributeName": "string",
                "crossAttributeValue": "string"
            }
        ],
        "crossName": "my_Ibadan_Crosses_2018_01",
        "crossType": "BIPARENTAL",
        "crossingProjectDbId": "696d7c92",
        "crossingProjectName": "my_Ibadan_Crosses_2018",
        "parent1": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": "MALE"
        },
        "parent2": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": "MALE"
        },
        "pollinationTimeStamp": "2019-08-15T18:49:00.327Z"
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
                "additionalInfo": {},
                "crossAttributes": [
                    {
                        "crossAttributeName": "Humidity Percentage",
                        "crossAttributeValue": 45
                    }
                ],
                "crossDbId": "d105fd6f",
                "crossName": "my_Ibadan_Crosses_2018_01",
                "crossType": "BIPARENTAL",
                "crossingProjectDbId": "696d7c92",
                "crossingProjectName": "my_Ibadan_Crosses_2018",
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
                "parent1": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "parent2": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "pollinationTimeStamp": "2018-01-01T14:47:23-0600"
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

# Group Crossing Projects






### Get - /crossingprojects [GET /brapi/v2/crossingprojects{?crossingProjectDbId}{?page}{?pageSize}]

Get a filtered list of Crossing Projects.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|commonCropName|string|the common name of a crop (for multi-crop systems)|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectDescription|string|the description for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|the unique identifier for a program|
|programName|string|the human readable name for a program|


 

+ Parameters
    + crossingProjectDbId (Optional, ) ... Search for Crossing Projects with this unique id
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
                "commonCropName": "Cassava",
                "crossingProjectDbId": "ce0e1c29",
                "crossingProjectDescription": "Crosses between germplasm X and germplasm Y in male nursery study X_2018 and female nursery study Y_2018",
                "crossingProjectName": "Ibadan_Crosses_2018",
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
                "programDbId": "a088176c",
                "programName": "IITA Cassava"
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




### Post - /crossingprojects [POST /brapi/v2/crossingprojects]

Create new Crossing Project entities on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|commonCropName|string|the common name of a crop (for multi-crop systems)|
|crossingProjectDescription|string|the description for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|the unique identifier for a program|
|programName|string|the human readable name for a program|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|commonCropName|string|the common name of a crop (for multi-crop systems)|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectDescription|string|the description for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|the unique identifier for a program|
|programName|string|the human readable name for a program|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "commonCropName": "Cassava",
        "crossingProjectDescription": "Crosses between germplasm X and germplasm Y in male nursery study X_2018 and female nursery study Y_2018",
        "crossingProjectName": "Ibadan_Crosses_2018",
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
        "programDbId": "a088176c",
        "programName": "IITA Cassava"
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
                "commonCropName": "Cassava",
                "crossingProjectDbId": "ce0e1c29",
                "crossingProjectDescription": "Crosses between germplasm X and germplasm Y in male nursery study X_2018 and female nursery study Y_2018",
                "crossingProjectName": "Ibadan_Crosses_2018",
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
                "programDbId": "a088176c",
                "programName": "IITA Cassava"
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




### Get - /crossingprojects/{crossingProjectDbId} [GET /brapi/v2/crossingprojects/{crossingProjectDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Get a filtered list of Crossing Projects.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|commonCropName|string|the common name of a crop (for multi-crop systems)|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectDescription|string|the description for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|the unique identifier for a program|
|programName|string|the human readable name for a program|


 

+ Parameters
    + crossingProjectDbId (Required, ) ... Search for Crossing Projects with this unique id
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
        "commonCropName": "Cassava",
        "crossingProjectDbId": "ce0e1c29",
        "crossingProjectDescription": "Crosses between germplasm X and germplasm Y in male nursery study X_2018 and female nursery study Y_2018",
        "crossingProjectName": "Ibadan_Crosses_2018",
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
        "programDbId": "a088176c",
        "programName": "IITA Cassava"
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




### Put - /crossingprojects/{crossingProjectDbId} [PUT /brapi/v2/crossingprojects/{crossingProjectDbId}]

Update an existing Crossing Project entity on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|commonCropName|string|the common name of a crop (for multi-crop systems)|
|crossingProjectDescription|string|the description for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|the unique identifier for a program|
|programName|string|the human readable name for a program|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|commonCropName|string|the common name of a crop (for multi-crop systems)|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectDescription|string|the description for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|programDbId|string|the unique identifier for a program|
|programName|string|the human readable name for a program|


 

+ Parameters
    + crossingProjectDbId (Required, ) ... Search for Crossing Projects with this unique id
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "commonCropName": "Cassava",
    "crossingProjectDescription": "Crosses between germplasm X and germplasm Y in male nursery study X_2018 and female nursery study Y_2018",
    "crossingProjectName": "Ibadan_Crosses_2018",
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
    "programDbId": "a088176c",
    "programName": "IITA Cassava"
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
        "commonCropName": "Cassava",
        "crossingProjectDbId": "ce0e1c29",
        "crossingProjectDescription": "Crosses between germplasm X and germplasm Y in male nursery study X_2018 and female nursery study Y_2018",
        "crossingProjectName": "Ibadan_Crosses_2018",
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
        "programDbId": "a088176c",
        "programName": "IITA Cassava"
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

# Group Germplasm
Fun Fact: The plural of germplasm is germplasm (no "s").






### Get - /breedingmethods [GET /brapi/v2/breedingmethods{?page}{?pageSize}]

Get the list of germplasm breeding methods available in a system.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|abbreviation|string|an abbreviation for the name of this breeding method|
|breedingMethodDbId|string|the unique identifier for this breeding method|
|breedingMethodName|string|human readable name of the breeding method|
|description|string|human readable description of the breeding method|


 

+ Parameters
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
                "abbreviation": "MB",
                "breedingMethodDbId": "ffcce7ef",
                "breedingMethodName": "Male Backcross",
                "description": "Backcross to recover a specific gene."
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




### Get - /breedingmethods/{breedingMethodDbId} [GET /brapi/v2/breedingmethods/{breedingMethodDbId}]

Get the details of a specific Breeding Method used to produce Germplasm



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|abbreviation|string|an abbreviation for the name of this breeding method|
|breedingMethodDbId|string|the unique identifier for this breeding method|
|breedingMethodName|string|human readable name of the breeding method|
|description|string|human readable description of the breeding method|


 

+ Parameters
    + breedingMethodDbId (Required, ) ... Internal database identifier for a breeding method
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
        "abbreviation": "MB",
        "breedingMethodDbId": "ffcce7ef",
        "breedingMethodName": "Male Backcross",
        "description": "Backcross to recover a specific gene."
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




### Get - /germplasm [GET /brapi/v2/germplasm{?germplasmPUI}{?germplasmDbId}{?germplasmName}{?commonCropName}{?accessionNumber}{?collection}{?genus}{?species}{?studyDbId}{?synonym}{?parentDbId}{?progenyDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Addresses these needs

- General germplasm search mechanism that accepts POST for complex queries 

- Possibility to search germplasm by more parameters than those allowed by the existing germplasm search 

- Possibility to get MCPD details by PUID rather than dbId



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc. This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


 

+ Parameters
    + germplasmPUI (Optional, ) ... Permanent unique identifier (DOI, URI, etc.)
    + germplasmDbId (Optional, ) ... Internal database identifier
    + germplasmName (Optional, ) ... Name of the germplasm
    + commonCropName (Optional, ) ... The common crop name related to this germplasm
    + accessionNumber (Optional, ) ... Unique identifiers for accessions within a genebank
    + collection (Optional, ) ... A specific panel/collection/population name this germplasm belongs to.
    + genus (Optional, ) ... Genus name to identify germplasm
    + species (Optional, ) ... Species name to identify germplasm
    + studyDbId (Optional, ) ... Search for Germplasm that are associated with a particular Study
    + synonym (Optional, ) ... Alternative name or ID used to reference this germplasm
    + parentDbId (Optional, ) ... Search for Germplasm with this parent
    + progenyDbId (Optional, ) ... Search for Germplasm with this child
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
                "accessionNumber": "A0000003",
                "acquisitionDate": "2018-01-01",
                "additionalInfo": {},
                "biologicalStatusOfAccessionCode": "420",
                "biologicalStatusOfAccessionDescription": "Genetic stock",
                "breedingMethodDbId": "ffcce7ef",
                "collection": "Rice Diversity Panel 1 (RDP1)",
                "commonCropName": "Maize",
                "countryOfOriginCode": "BES",
                "defaultDisplayName": "A0000003",
                "documentationURL": "https://wiki.brapi.org",
                "donors": [
                    {
                        "donorAccessionNumber": "A0000123",
                        "donorInstituteCode": "PER001",
                        "germplasmPUI": "http://pui.per/accession/A0000003"
                    }
                ],
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
                "genus": "Aspergillus",
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "germplasmOrigin": [
                    {
                        "coordinateUncertainty": "20",
                        "coordinates": {
                            "geometry": {
                                "coordinates": [
                                    -76.506042,
                                    42.417373,
                                    123
                                ],
                                "type": "Point"
                            },
                            "type": "Feature"
                        }
                    }
                ],
                "germplasmPUI": "http://pui.per/accession/A0000003",
                "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute",
                "pedigree": "A0000001/A0000002",
                "seedSource": "A0000001/A0000002",
                "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
                "species": "fructus",
                "speciesAuthority": "Smith, 1822",
                "storageTypes": [
                    {
                        "code": "20",
                        "description": "Field collection"
                    },
                    {
                        "code": "11",
                        "description": "Short term"
                    }
                ],
                "subtaxa": "Aspergillus fructus A",
                "subtaxaAuthority": "Smith, 1822",
                "synonyms": [
                    {
                        "synonym": "variety_1",
                        "type": "Pre-Code"
                    }
                ],
                "taxonIds": [
                    {
                        "sourceName": "NCBI",
                        "taxonId": "2026747"
                    }
                ]
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




### Post - /germplasm [POST /brapi/v2/germplasm]

Create new Germplasm entities on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc. This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "accessionNumber": "A0000003",
        "acquisitionDate": "2018-01-01",
        "additionalInfo": {},
        "biologicalStatusOfAccessionCode": "420",
        "biologicalStatusOfAccessionDescription": "Genetic stock",
        "breedingMethodDbId": "ffcce7ef",
        "collection": "Rice Diversity Panel 1 (RDP1)",
        "commonCropName": "Maize",
        "countryOfOriginCode": "BES",
        "defaultDisplayName": "A0000003",
        "documentationURL": "https://wiki.brapi.org",
        "donors": [
            {
                "donorAccessionNumber": "A0000123",
                "donorInstituteCode": "PER001",
                "germplasmPUI": "http://pui.per/accession/A0000003"
            }
        ],
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
        "genus": "Aspergillus",
        "germplasmName": "A0000003",
        "germplasmOrigin": [
            {
                "coordinateUncertainty": "20",
                "coordinates": {
                    "geometry": {
                        "coordinates": [
                            -76.506042,
                            42.417373,
                            123
                        ],
                        "type": "Point"
                    },
                    "type": "Feature"
                }
            }
        ],
        "germplasmPUI": "http://pui.per/accession/A0000003",
        "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
        "instituteCode": "PER001",
        "instituteName": "The BrAPI Institute",
        "pedigree": "A0000001/A0000002",
        "seedSource": "A0000001/A0000002",
        "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
        "species": "fructus",
        "speciesAuthority": "Smith, 1822",
        "storageTypes": [
            {
                "code": "20",
                "description": "Field collection"
            },
            {
                "code": "11",
                "description": "Short term"
            }
        ],
        "subtaxa": "Aspergillus fructus A",
        "subtaxaAuthority": "Smith, 1822",
        "synonyms": [
            {
                "synonym": "variety_1",
                "type": "Pre-Code"
            }
        ],
        "taxonIds": [
            {
                "sourceName": "NCBI",
                "taxonId": "2026747"
            }
        ]
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
                "accessionNumber": "A0000003",
                "acquisitionDate": "2018-01-01",
                "additionalInfo": {},
                "biologicalStatusOfAccessionCode": "420",
                "biologicalStatusOfAccessionDescription": "Genetic stock",
                "breedingMethodDbId": "ffcce7ef",
                "collection": "Rice Diversity Panel 1 (RDP1)",
                "commonCropName": "Maize",
                "countryOfOriginCode": "BES",
                "defaultDisplayName": "A0000003",
                "documentationURL": "https://wiki.brapi.org",
                "donors": [
                    {
                        "donorAccessionNumber": "A0000123",
                        "donorInstituteCode": "PER001",
                        "germplasmPUI": "http://pui.per/accession/A0000003"
                    }
                ],
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
                "genus": "Aspergillus",
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "germplasmOrigin": [
                    {
                        "coordinateUncertainty": "20",
                        "coordinates": {
                            "geometry": {
                                "coordinates": [
                                    -76.506042,
                                    42.417373,
                                    123
                                ],
                                "type": "Point"
                            },
                            "type": "Feature"
                        }
                    }
                ],
                "germplasmPUI": "http://pui.per/accession/A0000003",
                "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute",
                "pedigree": "A0000001/A0000002",
                "seedSource": "A0000001/A0000002",
                "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
                "species": "fructus",
                "speciesAuthority": "Smith, 1822",
                "storageTypes": [
                    {
                        "code": "20",
                        "description": "Field collection"
                    },
                    {
                        "code": "11",
                        "description": "Short term"
                    }
                ],
                "subtaxa": "Aspergillus fructus A",
                "subtaxaAuthority": "Smith, 1822",
                "synonyms": [
                    {
                        "synonym": "variety_1",
                        "type": "Pre-Code"
                    }
                ],
                "taxonIds": [
                    {
                        "sourceName": "NCBI",
                        "taxonId": "2026747"
                    }
                ]
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




### Get - /germplasm/{germplasmDbId} [GET /brapi/v2/germplasm/{germplasmDbId}]

Germplasm Details by germplasmDbId was merged with Germplasm Multi Crop Passport Data. The MCPD fields are optional and marked with the prefix [MCPD].



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc. This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


 

+ Parameters
    + germplasmDbId (Required, ) ... The internal id of the germplasm
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
        "accessionNumber": "A0000003",
        "acquisitionDate": "2018-01-01",
        "additionalInfo": {},
        "biologicalStatusOfAccessionCode": "420",
        "biologicalStatusOfAccessionDescription": "Genetic stock",
        "breedingMethodDbId": "ffcce7ef",
        "collection": "Rice Diversity Panel 1 (RDP1)",
        "commonCropName": "Maize",
        "countryOfOriginCode": "BES",
        "defaultDisplayName": "A0000003",
        "documentationURL": "https://wiki.brapi.org",
        "donors": [
            {
                "donorAccessionNumber": "A0000123",
                "donorInstituteCode": "PER001",
                "germplasmPUI": "http://pui.per/accession/A0000003"
            }
        ],
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
        "genus": "Aspergillus",
        "germplasmDbId": "d4076594",
        "germplasmName": "A0000003",
        "germplasmOrigin": [
            {
                "coordinateUncertainty": "20",
                "coordinates": {
                    "geometry": {
                        "coordinates": [
                            -76.506042,
                            42.417373,
                            123
                        ],
                        "type": "Point"
                    },
                    "type": "Feature"
                }
            }
        ],
        "germplasmPUI": "http://pui.per/accession/A0000003",
        "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
        "instituteCode": "PER001",
        "instituteName": "The BrAPI Institute",
        "pedigree": "A0000001/A0000002",
        "seedSource": "A0000001/A0000002",
        "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
        "species": "fructus",
        "speciesAuthority": "Smith, 1822",
        "storageTypes": [
            {
                "code": "20",
                "description": "Field collection"
            },
            {
                "code": "11",
                "description": "Short term"
            }
        ],
        "subtaxa": "Aspergillus fructus A",
        "subtaxaAuthority": "Smith, 1822",
        "synonyms": [
            {
                "synonym": "variety_1",
                "type": "Pre-Code"
            }
        ],
        "taxonIds": [
            {
                "sourceName": "NCBI",
                "taxonId": "2026747"
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




### Put - /germplasm/{germplasmDbId} [PUT /brapi/v2/germplasm/{germplasmDbId}]

Germplasm Details by germplasmDbId was merged with Germplasm Multi Crop Passport Data. The MCPD fields are optional and marked with the prefix [MCPD].

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc. This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


 

+ Parameters
    + germplasmDbId (Required, ) ... The internal id of the germplasm
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "accessionNumber": "A0000003",
    "acquisitionDate": "2018-01-01",
    "additionalInfo": {},
    "biologicalStatusOfAccessionCode": "420",
    "biologicalStatusOfAccessionDescription": "Genetic stock",
    "breedingMethodDbId": "ffcce7ef",
    "collection": "Rice Diversity Panel 1 (RDP1)",
    "commonCropName": "Maize",
    "countryOfOriginCode": "BES",
    "defaultDisplayName": "A0000003",
    "documentationURL": "https://wiki.brapi.org",
    "donors": [
        {
            "donorAccessionNumber": "A0000123",
            "donorInstituteCode": "PER001",
            "germplasmPUI": "http://pui.per/accession/A0000003"
        }
    ],
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
    "genus": "Aspergillus",
    "germplasmName": "A0000003",
    "germplasmOrigin": [
        {
            "coordinateUncertainty": "20",
            "coordinates": {
                "geometry": {
                    "coordinates": [
                        -76.506042,
                        42.417373,
                        123
                    ],
                    "type": "Point"
                },
                "type": "Feature"
            }
        }
    ],
    "germplasmPUI": "http://pui.per/accession/A0000003",
    "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
    "instituteCode": "PER001",
    "instituteName": "The BrAPI Institute",
    "pedigree": "A0000001/A0000002",
    "seedSource": "A0000001/A0000002",
    "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
    "species": "fructus",
    "speciesAuthority": "Smith, 1822",
    "storageTypes": [
        {
            "code": "20",
            "description": "Field collection"
        },
        {
            "code": "11",
            "description": "Short term"
        }
    ],
    "subtaxa": "Aspergillus fructus A",
    "subtaxaAuthority": "Smith, 1822",
    "synonyms": [
        {
            "synonym": "variety_1",
            "type": "Pre-Code"
        }
    ],
    "taxonIds": [
        {
            "sourceName": "NCBI",
            "taxonId": "2026747"
        }
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
        "accessionNumber": "A0000003",
        "acquisitionDate": "2018-01-01",
        "additionalInfo": {},
        "biologicalStatusOfAccessionCode": "420",
        "biologicalStatusOfAccessionDescription": "Genetic stock",
        "breedingMethodDbId": "ffcce7ef",
        "collection": "Rice Diversity Panel 1 (RDP1)",
        "commonCropName": "Maize",
        "countryOfOriginCode": "BES",
        "defaultDisplayName": "A0000003",
        "documentationURL": "https://wiki.brapi.org",
        "donors": [
            {
                "donorAccessionNumber": "A0000123",
                "donorInstituteCode": "PER001",
                "germplasmPUI": "http://pui.per/accession/A0000003"
            }
        ],
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
        "genus": "Aspergillus",
        "germplasmDbId": "d4076594",
        "germplasmName": "A0000003",
        "germplasmOrigin": [
            {
                "coordinateUncertainty": "20",
                "coordinates": {
                    "geometry": {
                        "coordinates": [
                            -76.506042,
                            42.417373,
                            123
                        ],
                        "type": "Point"
                    },
                    "type": "Feature"
                }
            }
        ],
        "germplasmPUI": "http://pui.per/accession/A0000003",
        "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
        "instituteCode": "PER001",
        "instituteName": "The BrAPI Institute",
        "pedigree": "A0000001/A0000002",
        "seedSource": "A0000001/A0000002",
        "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
        "species": "fructus",
        "speciesAuthority": "Smith, 1822",
        "storageTypes": [
            {
                "code": "20",
                "description": "Field collection"
            },
            {
                "code": "11",
                "description": "Short term"
            }
        ],
        "subtaxa": "Aspergillus fructus A",
        "subtaxaAuthority": "Smith, 1822",
        "synonyms": [
            {
                "synonym": "variety_1",
                "type": "Pre-Code"
            }
        ],
        "taxonIds": [
            {
                "sourceName": "NCBI",
                "taxonId": "2026747"
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




### Get - /germplasm/{germplasmDbId}/mcpd [GET /brapi/v2/germplasm/{germplasmDbId}/mcpd]

Get all MCPD details of a germplasm

<a target="_blank" href="https://www.bioversityInternational.org/fileadmin/user_upload/online_library/publications/pdfs/FAOBIOVERSITY_MULTI-CROP_PASSPORT_DESCRIPTORS_V.2.1_2015_2020.pdf"> MCPD v2.1 spec can be found here </a>

Implementation Notes

- When the MCPD spec identifies a field which can have multiple values returned, the JSON response should be an array instead of a semi-colon separated string.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|accessionNames|array[string]|MCPD (v2.1) (ACCENAME) 11. Either a registered or other designation given to the material received, other than the donors accession number (23) or collecting number (3). First letter uppercase. Multiple names are separated by a semicolon without space.|
|accessionNumber|string|MCPD (v2.1) (ACCENUMB) 2. This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection (e.g. "PI 113869").|
|acquisitionDate|string (date)|MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|acquisitionSourceCode|string|MCPD (v2.1) (COLLSRC) 21. The coding scheme proposed can be used at 2 different levels of detail: either by using the general codes (in bold-face) such as 10, 20, 30, 40, etc., or by using the more specific codes, such as 11, 12, etc.   10) Wild habitat  11) Forest or woodland  12) Shrubland  13) Grassland  14) Desert or tundra  15) Aquatic habitat  20) Farm or cultivated habitat  21) Field  22) Orchard  23) Backyard, kitchen or home garden (urban, peri-urban or rural)  24) Fallow land  25) Pasture  26) Farm store  27) Threshing floor  28) Park  30) Market or shop  40) Institute, Experimental station, Research organization, Genebank  50) Seed company  60) Weedy, disturbed or ruderal habitat  61) Roadside  62) Field margin  99) Other (Elaborate in REMARKS field)|
|alternateIDs|array[string]|MCPD (v2.1) (OTHERNUMB) 24. Any other identifiers known to exist in other collections for this accession. Use the following format: INSTCODE:ACCENUMB;INSTCODE:identifier;INSTCODE and identifier are separated by a colon without space. Pairs of INSTCODE and identifier are separated by a semicolon without space. When the institute is not known, the identifier should be preceded by a colon. |
|ancestralData|string|MCPD (v2.1) (ANCEST) 20. Information about either pedigree or other description of ancestral information (e.g. parent variety in case of mutant or selection). For example a pedigree 'Hanna/7*Atlas//Turk/8*Atlas' or a description 'mutation found in Hanna', 'selection from Irene' or 'cross involving amongst others Hanna and Irene'.|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|breedingInstitutes|array[object]||
|instituteCode|string|MCPD (v2.1) (BREDCODE) 18. FAO WIEWS code of the institute that has bred the material. If the holding institute has bred the material, the breeding institute code (BREDCODE) should be the same as the holding institute code (INSTCODE). Follows INSTCODE standard. Multiple values are separated by a semicolon without space.|
|instituteName|string|MCPD (v2.1) (BREDNAME) 18.1  Name of the institute (or person) that bred the material. This descriptor should be used only if BREDCODE can not be filled because the FAO WIEWS code for this institute is not available. Multiple names are separated by a semicolon without space.|
|collectingInfo|object|Information about the collection of this germplasm|
|collectingDate|string (date)|MCPD (v2.1) (COLLDATE) 17. Collecting date of the sample [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|collectingInstitutes|array[object]|Institutes which collected the sample|
|instituteAddress|string|MCPD (v2.1) (COLLINSTADDRESS) 4.1.1  Address of the institute collecting the sample. This descriptor should be used only if COLLCODE can not be filled since the FAO WIEWS code for this institute is not available. Multiple values are separated by a semicolon without space.|
|instituteCode|string|MCPD (v2.1) (COLLCODE) 4.  FAO WIEWS code of the institute collecting the sample. If the holding institute has collected the material, the collecting institute code (COLLCODE) should be the same as the holding institute code (INSTCODE). Follows INSTCODE standard. Multiple values are separated by a semicolon without space.|
|instituteName|string|MCPD (v2.1) (COLLNAME) 4.1  Name of the institute collecting the sample. This descriptor should be used only if COLLCODE can not be filled because the FAO WIEWS code for this institute is not available. Multiple values are separated by a semicolon without space.|
|collectingMissionIdentifier|string|MCPD (v2.1) (COLLMISSID) 4.2 Identifier of the collecting mission used by the Collecting Institute (4 or 4.1) (e.g. "CIATFOR_052", "CN_426").|
|collectingNumber|string|MCPD (v2.1) (COLLNUMB) 3. Original identifier assigned by the collector(s) of the sample, normally composed of the name or initials of the collector(s) followed by a number (e.g. "ab109909"). This identifier is essential for identifying duplicates held in different collections.|
|collectingSite|object|Information about the location where the sample was collected|
|coordinateUncertainty|string|MCPD (v2.1) (COORDUNCERT) 15.5 Uncertainty associated with the coordinates in metres. Leave the value empty if the uncertainty is unknown.|
|elevation|string|MCPD (v2.1) (ELEVATION) 16. Elevation of collecting site expressed in metres above sea level. Negative values are allowed.|
|georeferencingMethod|string|MCPD (v2.1) (GEOREFMETH) 15.7  The georeferencing method used (GPS, determined from map, gazetteer, or estimated using software). Leave the value empty if georeferencing method is not known.|
|latitudeDecimal|string|MCPD (v2.1) (DECLATITUDE) 15.1 Latitude expressed in decimal degrees. Positive values are North of the Equator; negative values are South of the Equator (e.g. -44.6975).|
|latitudeDegrees|string|MCPD (v2.1) (LATITUDE) 15.2 Degrees (2 digits) minutes (2 digits), and seconds (2 digits) followed by N (North) or S (South) (e.g. 103020S). Every missing digit (minutes or seconds) should be indicated with a hyphen. Leading zeros are required (e.g. 10|
|locationDescription|string|MCPD (v2.1) (COLLSITE) 14. Location information below the country level that describes where the accession was collected, preferable in English. This might include the distance in kilometres and direction from the nearest town, village or map grid reference point, (e.g. 7 km south of Townsville).|
|longitudeDecimal|string|MCPD (v2.1) (DECLONGITUDE) 15.3 Longitude expressed in decimal degrees. Positive values are East of the Greenwich Meridian; negative values are West of the Greenwich Meridian (e.g. +120.9123).|
|longitudeDegrees|string|MCPD (v2.1) (LONGITUDE) 15.4 Degrees (3 digits), minutes (2 digits), and seconds (2 digits) followed by E (East) or W (West) (e.g. 0762510W). Every missing digit (minutes or seconds) should be indicated with a hyphen. Leading zeros are required (e.g. 076|
|spatialReferenceSystem|string|MCPD (v2.1) (COORDDATUM) 15.6 The geodetic datum or spatial reference system upon which the coordinates given in decimal latitude and decimal longitude are based (e.g. WGS84). The GPS uses the WGS84 datum.|
|commonCropName|string|MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas". |
|countryOfOrigin|string|MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers" variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note: Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|donorInfo|object|Information about the donor|
|donorAccessionNumber|string|MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorAccessionPui|string|PUI (DOI mostly) of the accession in the donor system.|
|donorInstitute|object||
|instituteCode|string|MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|instituteName|string|MCPD (v2.1) (DONORNAME) 22.1  Name of the donor institute (or person). This descriptor should be used only if DONORCODE can not be filled because the FAO WIEWS code for this institute is not available.|
|genus|string|MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.|
|germplasmDbId|string|A unique identifier which identifies a germplasm in this database|
|germplasmPUI|string|MCPD (v2.1) (PUID) 0. Any persistent, unique identifier assigned to the accession so it can be unambiguously referenced at the global level and the information associated with it harvested through automated means. Report one PUID for each accession. The Secretariat of the International Treaty on Plant Genetic Resources for Food and Agriculture (PGRFA) is facilitating the assignment of a persistent unique identifier (PUID), in the form of a DOI, to PGRFA at the accession level. Genebanks not applying a true PUID to their accessions should use, and request recipients to use, the concatenation of INSTCODE, ACCENUMB, and GENUS as a globally unique identifier similar in most respects to the PUID whenever they exchange information on accessions with third parties.|
|instituteCode|string|MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|mlsStatus|string|MCPD (v2.1) (MLSSTAT) 27. The status of an accession with regards to the Multilateral System (MLS) of the International Treaty on Plant Genetic Resources for Food and Agriculture. Leave the value empty if the status is not known 0 No (not included) 1 Yes (included) 99 Other (elaborate in REMARKS field, e.g. "under development")|
|remarks|string|MCPD (v2.1) (REMARKS) 28. The remarks field is used to add notes or to elaborate on descriptors with value 99 or 999 (= Other). Prefix remarks with the field name they refer to and a colon (:) without space (e.g. COLLSRC:riverside). Distinct remarks referring to different fields are separated by semi-colons without space.|
|safetyDuplicateInstitutes|array[object]||
|instituteCode|string|MCPD (v2.1) (DUPLSITE) 25. FAO WIEWS code of the institute(s) where a safety duplicate of the accession is maintained. Follows INSTCODE standard.|
|instituteName|string|MCPD (v2.1) (DUPLINSTNAME) 25.1  Name of the institute where a safety duplicate of the accession is maintained.|
|species|string|MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp." |
|speciesAuthority|string|MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypeCodes|array[string]|MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.) 10) Seed collection 11) Short term 12) Medium term 13) Long term 20) Field collection 30) In vitro collection 40) Cryo-preserved collection 50) DNA collection 99) Other (elaborate in REMARKS field)|
|subtaxon|string|MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").|
|subtaxonAuthority|string|MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|


 

+ Parameters
    + germplasmDbId (Required, ) ... the internal id of the germplasm
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
        "accessionNames": [
            "Symphony",
            "Emma"
        ],
        "accessionNumber": "A0000003",
        "acquisitionDate": "2018-01-01",
        "acquisitionSourceCode": "26",
        "alternateIDs": [
            "3",
            "http://pui.per/accession/A0000003",
            "A0000003"
        ],
        "ancestralData": "A0000001/A0000002",
        "biologicalStatusOfAccessionCode": "421",
        "breedingInstitutes": [
            {
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute"
            }
        ],
        "collectingInfo": {
            "collectingDate": "2018-01-01",
            "collectingInstitutes": [
                {
                    "instituteAddress": "123 Main Street, Lima, Peru, 5555",
                    "instituteCode": "PER001",
                    "instituteName": "The BrAPI Institute"
                }
            ],
            "collectingMissionIdentifier": "CIATFOR_052",
            "collectingNumber": "ab109909",
            "collectingSite": {
                "coordinateUncertainty": "20",
                "elevation": "35",
                "georeferencingMethod": "WGS84",
                "latitudeDecimal": "+42.445295",
                "latitudeDegrees": "42 26 43.1 N",
                "locationDescription": "South east hill near institute buildings",
                "longitudeDecimal": "-076.471934",
                "longitudeDegrees": "76 28 19.0 W",
                "spatialReferenceSystem": "WGS84"
            }
        },
        "commonCropName": "malting barley",
        "countryOfOrigin": "Peru",
        "donorInfo": {
            "donorAccessionNumber": "A0090204",
            "donorAccessionPui": "http://pui.per/accession/A0010025",
            "donorInstitute": {
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute"
            }
        },
        "genus": "Aspergillus",
        "germplasmDbId": "31c4efbc",
        "germplasmPUI": "http://pui.per/accession/A0403652",
        "instituteCode": "PER001",
        "mlsStatus": "0",
        "remarks": "This is an example remark to demonstrate that any notable information can be put here",
        "safetyDuplicateInstitutes": [
            {
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute"
            }
        ],
        "species": "fructus",
        "speciesAuthority": "Smith, 1822",
        "storageTypeCodes": [
            "11",
            "13'"
        ],
        "subtaxon": "Aspergillus fructus A",
        "subtaxonAuthority": "Smith, 1822"
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




### Get - /germplasm/{germplasmDbId}/pedigree [GET /brapi/v2/germplasm/{germplasmDbId}/pedigree{?notation}{?includeSiblings}]

Get the parentage information of a specific Germplasm



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|crossingProjectDbId|string|The crossing project used to generate this germplasm|
|crossingYear|integer|The year the parents were originally crossed|
|familyCode|string|The code representing the family|
|germplasmDbId|string|The ID which uniquely identifies a germplasm|
|germplasmName|string|A human readable name for a germplasm|
|parents|array[object]|List of parent nodes in the pedigree tree.|
|germplasmDbId|string|The germplasm DbId of the parent of this germplasm|
|germplasmName|string|the human readable name of the parent of this germplasm|
|parentType|string|The type of parent the parent is. ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|pedigree|string|The string representation of the pedigree.|
|siblings|array[object]|List of sibling germplasm|
|germplasmDbId|string|the germplasm DbId of the sibling|
|germplasmName|string|the germplasm name of the sibling|


 

+ Parameters
    + germplasmDbId (Required, ) ... the internal id of the germplasm
    + notation (Optional, ) ... text representation of the pedigree
    + includeSiblings (Optional, ) ... include array of siblings in response
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
        "crossingProjectDbId": "625e745a",
        "crossingYear": 2005,
        "familyCode": "F0000203",
        "germplasmDbId": "1098ebaf",
        "germplasmName": "A0021004",
        "parents": [
            {
                "germplasmDbId": "b66958de",
                "germplasmName": "A0000592",
                "parentType": "MALE"
            },
            {
                "germplasmDbId": "a55847ed",
                "germplasmName": "A0000592",
                "parentType": "FEMALE"
            }
        ],
        "pedigree": "A0000001/A0000002",
        "siblings": [
            {
                "germplasmDbId": "334f53a3",
                "germplasmName": "A0021005"
            },
            {
                "germplasmDbId": "7bbbda8c",
                "germplasmName": "A0021006"
            },
            {
                "germplasmDbId": "ab1d9b26",
                "germplasmName": "A0021007"
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




### Get - /germplasm/{germplasmDbId}/progeny [GET /brapi/v2/germplasm/{germplasmDbId}/progeny]

Get the germplasmDbIds for all the Progeny of a particular germplasm.

Implementation Notes

- Regarding the ''parentType'' field in the progeny object. Given a germplasm A having a progeny B and C, ''parentType'' for progeny B refers to the ''parentType'' of A toward B.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|germplasmDbId|string|The ID which uniquely identifies a germplasm|
|germplasmName|string|A human readable name for a germplasm|
|progeny|array[object]|List of germplasm entities which are direct children of this germplasm|
|germplasmDbId|string|The unique identifier of a progeny germplasm|
|germplasmName|string|The human readable name of a progeny germplasm|
|parentType|string|Given a germplasm A having a progeny B and C, 'parentType' for progeny B item refers to the 'parentType' of A toward B.|


 

+ Parameters
    + germplasmDbId (Required, ) ... the internal id of the germplasm
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
        "germplasmDbId": "01b974dc",
        "germplasmName": "A0021004",
        "progeny": [
            {
                "germplasmDbId": "e8d5dad7",
                "germplasmName": "A0021011",
                "parentType": "FEMALE"
            },
            {
                "germplasmDbId": "ac07fbd8",
                "germplasmName": "A0021012",
                "parentType": "FEMALE"
            },
            {
                "germplasmDbId": "07f45f67",
                "germplasmName": "A0021013",
                "parentType": "FEMALE"
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




### Post - /search/germplasm [POST /brapi/v2/search/germplasm]

Search for a set of germplasm based on some criteria

Addresses these needs 

- General germplasm search mechanism that accepts POST for complex queries 

- Possibility to search germplasm by more parameters than those allowed by the existing germplasm search 

- Possibility to get MCPD details by PUID rather than dbId

See Search Services for additional implementation details.

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|accessionNumbers|array[string]|List unique identifiers for accessions within a genebank|
|collections|array[string]|A specific panel/collection/population name this germplasm belongs to.|
|commonCropNames|array[string]|Common name for the crop which this program is for|
|externalReferenceIDs|array[string]|List of external references for the trait to search for|
|externalReferenceSources|array[string]|List of external references sources for the trait to search for|
|genus|array[string]|List of Genus names to identify germplasm|
|germplasmDbIds|array[string]|List of IDs which uniquely identify germplasm to search for|
|germplasmNames|array[string]|List of human readable names to identify germplasm to search for|
|germplasmPUIs|array[string]|List of Permanent Unique Identifiers to identify germplasm|
|page|integer|Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.|
|pageSize|integer|The size of the pages to be returned. Default is `1000`.|
|parentDbIds|array[string]|Search for Germplasm with these parents|
|progenyDbIds|array[string]|Search for Germplasm with these children|
|species|array[string]|List of Species names to identify germplasm|
|studyDbIds|array[string]|List of study identifiers to search for|
|studyNames|array[string]|List of study names to filter search results|
|synonyms|array[string]|List of alternative names or IDs used to reference this germplasm|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc. This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "accessionNumbers": [
        "A0000003",
        "A0000477"
    ],
    "collections": [
        "RDP1",
        "MDP1"
    ],
    "commonCropNames": [
        "Tomatillo",
        "Paw Paw"
    ],
    "externalReferenceIDs": [
        "http://purl.obolibrary.org/obo/ro.owl",
        "14a19841"
    ],
    "externalReferenceSources": [
        "OBO Library",
        "Field App Name"
    ],
    "genus": [
        "Aspergillus",
        "Zea"
    ],
    "germplasmDbIds": [
        "e9c6edd7",
        "1b1df4a6"
    ],
    "germplasmNames": [
        "A0000003",
        "A0000477"
    ],
    "germplasmPUIs": [
        "http://pui.per/accession/A0000003",
        "http://pui.per/accession/A0000477"
    ],
    "page": 0,
    "pageSize": 1000,
    "parentDbIds": [
        "72c1001f",
        "7346c553"
    ],
    "progenyDbIds": [
        "16e16a7e",
        "ce06cf9e"
    ],
    "species": [
        "fructus",
        "mays"
    ],
    "studyDbIds": [
        "cf6c4bd4",
        "691e69d6"
    ],
    "studyNames": [
        "The First Bob Study 2017",
        "Wheat Yield Trial 246"
    ],
    "synonyms": [
        "variety_1",
        "2c38f9b6"
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
                "accessionNumber": "A0000003",
                "acquisitionDate": "2018-01-01",
                "additionalInfo": {},
                "biologicalStatusOfAccessionCode": "420",
                "biologicalStatusOfAccessionDescription": "Genetic stock",
                "breedingMethodDbId": "ffcce7ef",
                "collection": "Rice Diversity Panel 1 (RDP1)",
                "commonCropName": "Maize",
                "countryOfOriginCode": "BES",
                "defaultDisplayName": "A0000003",
                "documentationURL": "https://wiki.brapi.org",
                "donors": [
                    {
                        "donorAccessionNumber": "A0000123",
                        "donorInstituteCode": "PER001",
                        "germplasmPUI": "http://pui.per/accession/A0000003"
                    }
                ],
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
                "genus": "Aspergillus",
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "germplasmOrigin": [
                    {
                        "coordinateUncertainty": "20",
                        "coordinates": {
                            "geometry": {
                                "coordinates": [
                                    -76.506042,
                                    42.417373,
                                    123
                                ],
                                "type": "Point"
                            },
                            "type": "Feature"
                        }
                    }
                ],
                "germplasmPUI": "http://pui.per/accession/A0000003",
                "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute",
                "pedigree": "A0000001/A0000002",
                "seedSource": "A0000001/A0000002",
                "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
                "species": "fructus",
                "speciesAuthority": "Smith, 1822",
                "storageTypes": [
                    {
                        "code": "20",
                        "description": "Field collection"
                    },
                    {
                        "code": "11",
                        "description": "Short term"
                    }
                ],
                "subtaxa": "Aspergillus fructus A",
                "subtaxaAuthority": "Smith, 1822",
                "synonyms": [
                    {
                        "synonym": "variety_1",
                        "type": "Pre-Code"
                    }
                ],
                "taxonIds": [
                    {
                        "sourceName": "NCBI",
                        "taxonId": "2026747"
                    }
                ]
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




### Get - /search/germplasm/{searchResultsDbId} [GET /brapi/v2/search/germplasm/{searchResultsDbId}{?page}{?pageSize}]

See Search Services for additional implementation details.

Addresses these needs: 

1. General germplasm search mechanism that accepts POST for complex queries 

2. possibility to search germplasm by more parameters than those allowed by the existing germplasm search 

3. possibility to get MCPD details by PUID rather than dbId



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|accessionNumber|string|This is the unique identifier for accessions within a genebank, and is assigned when a sample is entered into the genebank collection|
|acquisitionDate|string (date)|The date this germplasm was acquired by the genebank   MCPD (v2.1) (ACQDATE) 12. Date on which the accession entered the collection [YYYYMMDD] where YYYY is the year, MM is the month and DD is the day. Missing data (MM or DD) should be indicated with hyphens or "00" [double zero].|
|additionalInfo|object|Additional arbitrary info|
|biologicalStatusOfAccessionCode|string|MCPD (v2.1) (SAMPSTAT) 19. The coding scheme proposed can be used at 3 different levels of detail: either by using the general codes such as 100, 200, 300, 400, or by using the more specific codes such as 110, 120, etc.   100) Wild  110) Natural  120) Semi-natural/wild  130) Semi-natural/sown  200) Weedy  300) Traditional cultivar/landrace  400) Breeding/research material  410) Breeders line  411) Synthetic population  412) Hybrid  413) Founder stock/base population  414) Inbred line (parent of hybrid cultivar)  415) Segregating population  416) Clonal selection  420) Genetic stock  421) Mutant (e.g. induced/insertion mutants, tilling populations)  422) Cytogenetic stocks (e.g. chromosome addition/substitution, aneuploids,  amphiploids)  423) Other genetic stocks (e.g. mapping populations)  500) Advanced or improved cultivar (conventional breeding methods)  600) GMO (by genetic engineering)  999) Other (Elaborate in REMARKS field)|
|biologicalStatusOfAccessionDescription|string|Supplemental text description for 'biologicalStatusOfAccessionCode'|
|breedingMethodDbId|string|The unique identifier for the breeding method used to create this germplasm|
|collection|string|A specific panel/collection/population name this germplasm belongs to.|
|commonCropName|string|Common name for the crop   MCPD (v2.1) (CROPNAME) 10. Common name of the crop. Example: "malting barley", "mas".|
|countryOfOriginCode|string|3-letter ISO 3166-1 code of the country in which the sample was originally collected   MCPD (v2.1) (ORIGCTY) 13. 3-letter ISO 3166-1 code of the country in which the sample was originally collected (e.g. landrace, crop wild relative, farmers variety), bred or selected (breeding lines, GMOs, segregating populations, hybrids, modern cultivars, etc.). Note- Descriptors 14 to 16 below should be completed accordingly only if it was "collected".|
|defaultDisplayName|string|Human readable name used for display purposes|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|donors|array[object]|List of donor institutes|
|donorAccessionNumber|string|The accession number assigned by the donor  MCPD (v2.1) (DONORNUMB) 23. Identifier assigned to an accession by the donor. Follows ACCENUMB standard.|
|donorInstituteCode|string|The institute code for the donor institute  MCPD (v2.1) (DONORCODE) 22. FAO WIEWS code of the donor institute. Follows INSTCODE standard.|
|germplasmPUI|string||
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|genus|string|Genus name for taxon. Initial uppercase letter required.  MCPD (v2.1) (GENUS) 5. Genus name for taxon. Initial uppercase letter required.  MIAPPE V1.1 (DM-43) Genus - Genus name for the organism under study, according to standard scientific nomenclature.|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc. This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|germplasmOrigin|array[object]|Information for material (orchard, natural sites, ...). Geographic identification of the plants from which seeds or cutting have been taken to produce that germplasm.|
|coordinateUncertainty|string|Uncertainty associated with the coordinates in meters. Leave the value empty if the uncertainty is unknown.|
|coordinates|object|One geometry as defined by GeoJSON (RFC 7946). All coordinates are decimal values on the WGS84 geographic coordinate reference system.  Copied from RFC 7946 Section 3.1.1  A position is an array of numbers. There MUST be two or more elements. The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers. Altitude or elevation MAY be included as an optional third element.|
|geometry|object|A geometry as defined by GeoJSON (RFC 7946). In this context, only Point or Polygon geometry are allowed.|
|type|string|The literal string "Feature"|
|germplasmPUI|string|The Permanent Unique Identifier which represents a germplasm  MIAPPE V1.1 (DM-41) Biological material ID - Code used to identify the biological material in the data file. Should be unique within the Investigation. Can correspond to experimental plant ID, seed lot ID, etc This material identification is different from a BiosampleID which corresponds to Observation Unit or Samples sections below.|
|germplasmPreprocessing|string|Description of any process or treatment applied uniformly to the germplasm, prior to the study itself. Can be provided as free text or as an accession number from a suitable controlled vocabulary.|
|instituteCode|string|The code for the Institute that has bred the material.   MCPD (v2.1) (INSTCODE) 1. FAO WIEWS code of the institute where the accession is maintained. The codes consist of the 3-letter ISO 3166 country code of the country where the institute is located plus a number (e.g. PER001). The current set of institute codes is available from http://www.fao.org/wiews. For those institutes not yet having an FAO Code, or for those with "obsolete" codes, see "Common formatting rules (v)".|
|instituteName|string|The name of the institution which bred the material|
|pedigree|string|The cross name and optional selection history.|
|seedSource|string|The source of the seed |
|seedSourceDescription|string|Description of the material source|
|species|string|Specific epithet portion of the scientific name in lowercase letters.  MCPD (v2.1) (SPECIES) 6. Specific epithet portion of the scientific name in lowercase letters. Only the following abbreviation is allowed: "sp."   MIAPPE V1.1 (DM-44) Species - Species name (formally: specific epithet) for the organism under study, according to standard scientific nomenclature.|
|speciesAuthority|string|The authority organization responsible for tracking and maintaining the species name   MCPD (v2.1) (SPAUTHOR) 7. Provide the authority for the species name.|
|storageTypes|array[object]|The type of storage this germplasm is kept in at a genebank.|
|code|string|The 2 digit code representing the type of storage this germplasm is kept in at a genebank.   MCPD (v2.1) (STORAGE) 26. If germplasm is maintained under different types of storage, multiple choices are allowed, separated by a semicolon (e.g. 20;30). (Refer to FAO/IPGRI Genebank Standards 1994 for details on storage type.)   10) Seed collection  11) Short term  12) Medium term  13) Long term  20) Field collection  30) In vitro collection  40) Cryo-preserved collection  50) DNA collection  99) Other (elaborate in REMARKS field)|
|description|string|A supplemental text description of the storage type|
|subtaxa|string|Subtaxon can be used to store any additional taxonomic identifier.  MCPD (v2.1) (SUBTAXA) 8. Subtaxon can be used to store any additional taxonomic identifier. The following abbreviations are allowed: "subsp." (for subspecies); "convar." (for convariety); "var." (for variety); "f." (for form); "Group" (for "cultivar group").  MIAPPE V1.1 (DM-44) Infraspecific name - Name of any subtaxa level, including variety, crossing name, etc. It can be used to store any additional taxonomic identifier. Either free text description or key-value pair list format (the key is the name of the rank and the value is the value of  the rank). Ranks can be among the following terms: subspecies, cultivar, variety, subvariety, convariety, group, subgroup, hybrid, line, form, subform. For MCPD compliance, the following abbreviations are allowed: subsp. (subspecies); convar. (convariety); var. (variety); f. (form); Group (cultivar group).|
|subtaxaAuthority|string|The authority organization responsible for tracking and maintaining the subtaxon information  MCPD (v2.1) (SUBTAUTHOR) 9. Provide the subtaxon authority at the most detailed taxonomic level.|
|synonyms|array[object]|List of alternative names or IDs used to reference this germplasm|
|synonym|string|Alternative name or ID used to reference this germplasm|
|type|string|A descriptive classification for this synonym|
|taxonIds|array[object]|The list of IDs for this SPECIES from different sources. If present, NCBI Taxon should be always listed as "ncbiTaxon" preferably with a purl. The rank of this ID should be species.  MIAPPE V1.1 (DM-42) Organism - An identifier for the organism at the species level. Use of the NCBI taxon ID is recommended.|
|sourceName|string|The human readable name of the taxonomy provider|
|taxonId|string|The identifier (name, ID, URI) of a particular taxonomy within the source provider|


 

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
                "accessionNumber": "A0000003",
                "acquisitionDate": "2018-01-01",
                "additionalInfo": {},
                "biologicalStatusOfAccessionCode": "420",
                "biologicalStatusOfAccessionDescription": "Genetic stock",
                "breedingMethodDbId": "ffcce7ef",
                "collection": "Rice Diversity Panel 1 (RDP1)",
                "commonCropName": "Maize",
                "countryOfOriginCode": "BES",
                "defaultDisplayName": "A0000003",
                "documentationURL": "https://wiki.brapi.org",
                "donors": [
                    {
                        "donorAccessionNumber": "A0000123",
                        "donorInstituteCode": "PER001",
                        "germplasmPUI": "http://pui.per/accession/A0000003"
                    }
                ],
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
                "genus": "Aspergillus",
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "germplasmOrigin": [
                    {
                        "coordinateUncertainty": "20",
                        "coordinates": {
                            "geometry": {
                                "coordinates": [
                                    -76.506042,
                                    42.417373,
                                    123
                                ],
                                "type": "Point"
                            },
                            "type": "Feature"
                        }
                    }
                ],
                "germplasmPUI": "http://pui.per/accession/A0000003",
                "germplasmPreprocessing": "EO:0007210; transplanted from study 2351 observation unit ID: pot:894",
                "instituteCode": "PER001",
                "instituteName": "The BrAPI Institute",
                "pedigree": "A0000001/A0000002",
                "seedSource": "A0000001/A0000002",
                "seedSourceDescription": "Branches were collected from a 10-year-old tree growing in a progeny trial established in a loamy brown earth soil.",
                "species": "fructus",
                "speciesAuthority": "Smith, 1822",
                "storageTypes": [
                    {
                        "code": "20",
                        "description": "Field collection"
                    },
                    {
                        "code": "11",
                        "description": "Short term"
                    }
                ],
                "subtaxa": "Aspergillus fructus A",
                "subtaxaAuthority": "Smith, 1822",
                "synonyms": [
                    {
                        "synonym": "variety_1",
                        "type": "Pre-Code"
                    }
                ],
                "taxonIds": [
                    {
                        "sourceName": "NCBI",
                        "taxonId": "2026747"
                    }
                ]
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

# Group Germplasm Attribute Values
Germplasm "attributes" are simply-inherited characteristics (characterization descriptors) that are not environment-dependent but 
inherent in the germplasm line.  They include genes, QTLs, and genetic "traits" like wheat grain 
hardness.  They are often evaluated by genotyping for diagnostic markers.






### Get - /attributevalues [GET /brapi/v2/attributevalues{?attributeValueDbId}{?attributeDbId}{?attributeName}{?germplasmDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Get the Germplasm Attribute Values



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

+ Parameters
    + attributeValueDbId (Optional, ) ... The unique id for an attribute value
    + attributeDbId (Optional, ) ... The unique id for an attribute
    + attributeName (Optional, ) ... The human readable name for an attribute
    + germplasmDbId (Optional, ) ... Get all attributes associated with this germplasm
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
                "additionalInfo": {},
                "attributeCategory": "Morphological",
                "attributeDbId": "2f08b902",
                "attributeDescription": "Height of the plant measured in meters by a tape",
                "attributeName": "Plant Height 1",
                "commonCropName": "Maize",
                "contextOfUse": [
                    "Trial evaluation",
                    "Nursery evaluation"
                ],
                "defaultValue": 2.0,
                "documentationURL": "https://wiki.brapi.org/documentation.html",
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
                "growthStage": "flowering",
                "institution": "The BrAPI Institute",
                "language": "en",
                "method": {
                    "additionalInfo": {},
                    "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
                    "description": "A measuring tape was used",
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
                    "formula": "a^2 + b^2 = c^2",
                    "methodClass": "Measurement",
                    "methodDbId": "0adb2764",
                    "methodName": "Measuring Tape",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    }
                },
                "ontologyReference": {
                    "documentationLinks": [
                        {
                            "URL": "http://purl.obolibrary.org/obo/ro.owl",
                            "type": [
                                "OBO",
                                "RDF",
                                "WEBPAGE"
                            ]
                        }
                    ],
                    "ontologyDbId": "6b071868",
                    "ontologyName": "The Crop Ontology",
                    "version": "7.2.3"
                },
                "scale": {
                    "dataType": [
                        "Code",
                        "Date",
                        "Duration",
                        "Nominal",
                        "Numerical",
                        "Ordinal",
                        "Text"
                    ],
                    "decimalPlaces": 2,
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
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "scaleDbId": "af730171",
                    "scaleName": "Meters",
                    "validValues": {
                        "categories": [
                            {
                                "label": "low",
                                "value": "0"
                            },
                            {
                                "label": "medium",
                                "value": "5"
                            },
                            {
                                "label": "high",
                                "value": "10"
                            }
                        ],
                        "max": 9999,
                        "min": 2
                    }
                },
                "scientist": "Dr. Bob Robertson",
                "status": "recommended",
                "submissionTimestamp": "2018-01-01T14:47:23-0600",
                "synonyms": [
                    "Maize Height",
                    "Stalk Height",
                    "Corn Height"
                ],
                "trait": {
                    "alternativeAbbreviations": [
                        "H",
                        "PH",
                        "H1"
                    ],
                    "attribute": "height",
                    "entity": "Stalk",
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
                    "mainAbbreviation": "PH",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "status": "recommended",
                    "synonyms": [
                        "Height",
                        "Plant Height",
                        "Stalk Height",
                        "Canopy Height"
                    ],
                    "traitClass": "phenological",
                    "traitDbId": "9b2e34f5",
                    "traitDescription": "The height of the plant",
                    "traitName": "Height"
                }
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




### Post - /attributevalues [POST /brapi/v2/attributevalues]

Create new Germplasm Attribute Values

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|attributeValueDbId|string|The ID which uniquely identifies this attribute value within the given database server|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "additionalInfo": {},
        "attributeDbId": "e529dd5a",
        "attributeName": "Weevil Resistance",
        "determinedDate": "2018-01-01T14:47:23-0600",
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
        "germplasmDbId": "d4076594",
        "germplasmName": "A0000003",
        "value": "Present"
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
                "additionalInfo": {},
                "attributeDbId": "e529dd5a",
                "attributeName": "Weevil Resistance",
                "attributeValueDbId": "33edbab7",
                "determinedDate": "2018-01-01T14:47:23-0600",
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
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "value": "Present"
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




### Get - /attributevalues/{attributeValueDbId} [GET /brapi/v2/attributevalues/{attributeValueDbId}]

Get the details for a specific Germplasm Attribute



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|attributeValueDbId|string|The ID which uniquely identifies this attribute value within the given database server|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


 

+ Parameters
    + attributeValueDbId (Required, ) ... The unique id for an attribute value
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
        "additionalInfo": {},
        "attributeDbId": "e529dd5a",
        "attributeName": "Weevil Resistance",
        "attributeValueDbId": "33edbab7",
        "determinedDate": "2018-01-01T14:47:23-0600",
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
        "germplasmDbId": "d4076594",
        "germplasmName": "A0000003",
        "value": "Present"
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




### Post - /attributevalues/{attributeValueDbId} [POST /brapi/v2/attributevalues/{attributeValueDbId}]

Create new Germplasm Attribute Values

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|attributeValueDbId|string|The ID which uniquely identifies this attribute value within the given database server|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


 

+ Parameters
    + attributeValueDbId (Required, ) ... The unique id for an attribute value
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "additionalInfo": {},
    "attributeDbId": "e529dd5a",
    "attributeName": "Weevil Resistance",
    "determinedDate": "2018-01-01T14:47:23-0600",
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
    "germplasmDbId": "d4076594",
    "germplasmName": "A0000003",
    "value": "Present"
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
        "additionalInfo": {},
        "attributeDbId": "e529dd5a",
        "attributeName": "Weevil Resistance",
        "attributeValueDbId": "33edbab7",
        "determinedDate": "2018-01-01T14:47:23-0600",
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
        "germplasmDbId": "d4076594",
        "germplasmName": "A0000003",
        "value": "Present"
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




### Post - /search/attributevalues [POST /brapi/v2/search/attributevalues]

Search for a set of Germplasm Attribute Values based on some criteria
        
See Search Services for additional implementation details.

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|attributeDbIds|array[string]|List of Germplasm Attribute IDs to search for|
|attributeNames|array[string]|List of human readable Germplasm Attribute names to search for|
|attributeValueDbIds|array[string]|List of Germplasm Attribute Value IDs to search for|
|dataTypes|array[string]|List of scale data types to filter search results|
|externalReferenceIDs|array[string]|List of external references for the trait to search for|
|externalReferenceSources|array[string]|List of external references sources for the trait to search for|
|germplasmDbIds|array[string]|List of IDs which uniquely identify germplasm to search for|
|germplasmNames|array[string]|List of human readable names to identify germplasm to search for|
|methodDbIds|array[string]|List of methods to filter search results|
|ontologyDbIds|array[string]|List of ontology IDs to search for|
|page|integer|Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.|
|pageSize|integer|The size of the pages to be returned. Default is `1000`.|
|scaleDbIds|array[string]|List of scales to filter search results|
|traitClasses|array[string]|List of trait classes to filter search results|
|traitDbIds|array[string]|List of trait unique ID to filter search results|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|attributeValueDbId|string|The ID which uniquely identifies this attribute value within the given database server|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "attributeDbIds": [
        "2ef15c9f",
        "318e7f7d"
    ],
    "attributeNames": [
        "Plant Height 1",
        "Root Color"
    ],
    "attributeValueDbIds": [
        "ca4636d0",
        "c8a92409"
    ],
    "dataTypes": [
        "Numerical",
        "Ordinal",
        "Text"
    ],
    "externalReferenceIDs": [
        "http://purl.obolibrary.org/obo/ro.owl",
        "14a19841"
    ],
    "externalReferenceSources": [
        "OBO Library",
        "Field App Name"
    ],
    "germplasmDbIds": [
        "e9c6edd7",
        "1b1df4a6"
    ],
    "germplasmNames": [
        "A0000003",
        "A0000477"
    ],
    "methodDbIds": [
        "07e34f83",
        "d3d5517a"
    ],
    "ontologyDbIds": [
        "f44f7b23",
        "a26b576e"
    ],
    "page": 0,
    "pageSize": 1000,
    "scaleDbIds": [
        "a13ecffa",
        "7e1afe4f"
    ],
    "traitClasses": [
        "morphological",
        "phenological",
        "agronomical"
    ],
    "traitDbIds": [
        "ef81147b",
        "78d82fad"
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
                "additionalInfo": {},
                "attributeDbId": "e529dd5a",
                "attributeName": "Weevil Resistance",
                "attributeValueDbId": "33edbab7",
                "determinedDate": "2018-01-01T14:47:23-0600",
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
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "value": "Present"
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




### Get - /search/attributevalues/{searchResultsDbId} [GET /brapi/v2/search/attributevalues/{searchResultsDbId}{?page}{?pageSize}]

Get the results of a Germplasm Attribute Values search request

See Search Services for additional implementation details.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeName|string|A human readable name for this attribute|
|attributeValueDbId|string|The ID which uniquely identifies this attribute value within the given database server|
|determinedDate|string (date-time)|The date the value of this attribute was determined for a given germplasm|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|The ID which uniquely identifies a germplasm within the given database server|
|germplasmName|string|Name of the germplasm. It can be the preferred name and does not have to be unique.|
|value|string|The value of this attribute for a given germplasm|


 

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
                "additionalInfo": {},
                "attributeDbId": "e529dd5a",
                "attributeName": "Weevil Resistance",
                "attributeValueDbId": "33edbab7",
                "determinedDate": "2018-01-01T14:47:23-0600",
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
                "germplasmDbId": "d4076594",
                "germplasmName": "A0000003",
                "value": "Present"
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

# Group Germplasm Attributes
Germplasm "attributes" are simply-inherited characteristics (characterization descriptors) that are not environment-dependent but 
inherent in the germplasm line.  They include genes, QTLs, and genetic "traits" like wheat grain 
hardness.  They are often evaluated by genotyping for diagnostic markers.






### Get - /attributes [GET /brapi/v2/attributes{?attributeCategory}{?attributeDbId}{?attributeName}{?germplasmDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

List available attributes.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

+ Parameters
    + attributeCategory (Optional, ) ... The general category for the attribute. very similar to Trait class.
    + attributeDbId (Optional, ) ... The unique id for an attribute
    + attributeName (Optional, ) ... The human readable name for an attribute
    + germplasmDbId (Optional, ) ... Get all attributes associated with this germplasm
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
                "additionalInfo": {},
                "attributeCategory": "Morphological",
                "attributeDbId": "2f08b902",
                "attributeDescription": "Height of the plant measured in meters by a tape",
                "attributeName": "Plant Height 1",
                "commonCropName": "Maize",
                "contextOfUse": [
                    "Trial evaluation",
                    "Nursery evaluation"
                ],
                "defaultValue": 2.0,
                "documentationURL": "https://wiki.brapi.org/documentation.html",
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
                "growthStage": "flowering",
                "institution": "The BrAPI Institute",
                "language": "en",
                "method": {
                    "additionalInfo": {},
                    "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
                    "description": "A measuring tape was used",
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
                    "formula": "a^2 + b^2 = c^2",
                    "methodClass": "Measurement",
                    "methodDbId": "0adb2764",
                    "methodName": "Measuring Tape",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    }
                },
                "ontologyReference": {
                    "documentationLinks": [
                        {
                            "URL": "http://purl.obolibrary.org/obo/ro.owl",
                            "type": [
                                "OBO",
                                "RDF",
                                "WEBPAGE"
                            ]
                        }
                    ],
                    "ontologyDbId": "6b071868",
                    "ontologyName": "The Crop Ontology",
                    "version": "7.2.3"
                },
                "scale": {
                    "dataType": [
                        "Code",
                        "Date",
                        "Duration",
                        "Nominal",
                        "Numerical",
                        "Ordinal",
                        "Text"
                    ],
                    "decimalPlaces": 2,
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
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "scaleDbId": "af730171",
                    "scaleName": "Meters",
                    "validValues": {
                        "categories": [
                            {
                                "label": "low",
                                "value": "0"
                            },
                            {
                                "label": "medium",
                                "value": "5"
                            },
                            {
                                "label": "high",
                                "value": "10"
                            }
                        ],
                        "max": 9999,
                        "min": 2
                    }
                },
                "scientist": "Dr. Bob Robertson",
                "status": "recommended",
                "submissionTimestamp": "2018-01-01T14:47:23-0600",
                "synonyms": [
                    "Maize Height",
                    "Stalk Height",
                    "Corn Height"
                ],
                "trait": {
                    "alternativeAbbreviations": [
                        "H",
                        "PH",
                        "H1"
                    ],
                    "attribute": "height",
                    "entity": "Stalk",
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
                    "mainAbbreviation": "PH",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "status": "recommended",
                    "synonyms": [
                        "Height",
                        "Plant Height",
                        "Stalk Height",
                        "Canopy Height"
                    ],
                    "traitClass": "phenological",
                    "traitDbId": "9b2e34f5",
                    "traitDescription": "The height of the plant",
                    "traitName": "Height"
                }
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




### Post - /attributes [POST /brapi/v2/attributes]

Create new Germplasm Attributes

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "additionalInfo": {},
        "attributeCategory": "Morphological",
        "attributeDescription": "Height of the plant measured in meters by a tape",
        "attributeName": "Plant Height 1",
        "commonCropName": "Maize",
        "contextOfUse": [
            "Trial evaluation",
            "Nursery evaluation"
        ],
        "defaultValue": 2.0,
        "documentationURL": "https://wiki.brapi.org/documentation.html",
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
        "growthStage": "flowering",
        "institution": "The BrAPI Institute",
        "language": "en",
        "method": {
            "additionalInfo": {},
            "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
            "description": "A measuring tape was used",
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
            "formula": "a^2 + b^2 = c^2",
            "methodClass": "Measurement",
            "methodDbId": "0adb2764",
            "methodName": "Measuring Tape",
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            }
        },
        "ontologyReference": {
            "documentationLinks": [
                {
                    "URL": "http://purl.obolibrary.org/obo/ro.owl",
                    "type": [
                        "OBO",
                        "RDF",
                        "WEBPAGE"
                    ]
                }
            ],
            "ontologyDbId": "6b071868",
            "ontologyName": "The Crop Ontology",
            "version": "7.2.3"
        },
        "scale": {
            "dataType": [
                "Code",
                "Date",
                "Duration",
                "Nominal",
                "Numerical",
                "Ordinal",
                "Text"
            ],
            "decimalPlaces": 2,
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
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            },
            "scaleDbId": "af730171",
            "scaleName": "Meters",
            "validValues": {
                "categories": [
                    {
                        "label": "low",
                        "value": "0"
                    },
                    {
                        "label": "medium",
                        "value": "5"
                    },
                    {
                        "label": "high",
                        "value": "10"
                    }
                ],
                "max": 9999,
                "min": 2
            }
        },
        "scientist": "Dr. Bob Robertson",
        "status": "recommended",
        "submissionTimestamp": "2018-01-01T14:47:23-0600",
        "synonyms": [
            "Maize Height",
            "Stalk Height",
            "Corn Height"
        ],
        "trait": {
            "alternativeAbbreviations": [
                "H",
                "PH",
                "H1"
            ],
            "attribute": "height",
            "entity": "Stalk",
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
            "mainAbbreviation": "PH",
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            },
            "status": "recommended",
            "synonyms": [
                "Height",
                "Plant Height",
                "Stalk Height",
                "Canopy Height"
            ],
            "traitClass": "phenological",
            "traitDbId": "9b2e34f5",
            "traitDescription": "The height of the plant",
            "traitName": "Height"
        }
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
                "additionalInfo": {},
                "attributeCategory": "Morphological",
                "attributeDbId": "2f08b902",
                "attributeDescription": "Height of the plant measured in meters by a tape",
                "attributeName": "Plant Height 1",
                "commonCropName": "Maize",
                "contextOfUse": [
                    "Trial evaluation",
                    "Nursery evaluation"
                ],
                "defaultValue": 2.0,
                "documentationURL": "https://wiki.brapi.org/documentation.html",
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
                "growthStage": "flowering",
                "institution": "The BrAPI Institute",
                "language": "en",
                "method": {
                    "additionalInfo": {},
                    "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
                    "description": "A measuring tape was used",
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
                    "formula": "a^2 + b^2 = c^2",
                    "methodClass": "Measurement",
                    "methodDbId": "0adb2764",
                    "methodName": "Measuring Tape",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    }
                },
                "ontologyReference": {
                    "documentationLinks": [
                        {
                            "URL": "http://purl.obolibrary.org/obo/ro.owl",
                            "type": [
                                "OBO",
                                "RDF",
                                "WEBPAGE"
                            ]
                        }
                    ],
                    "ontologyDbId": "6b071868",
                    "ontologyName": "The Crop Ontology",
                    "version": "7.2.3"
                },
                "scale": {
                    "dataType": [
                        "Code",
                        "Date",
                        "Duration",
                        "Nominal",
                        "Numerical",
                        "Ordinal",
                        "Text"
                    ],
                    "decimalPlaces": 2,
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
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "scaleDbId": "af730171",
                    "scaleName": "Meters",
                    "validValues": {
                        "categories": [
                            {
                                "label": "low",
                                "value": "0"
                            },
                            {
                                "label": "medium",
                                "value": "5"
                            },
                            {
                                "label": "high",
                                "value": "10"
                            }
                        ],
                        "max": 9999,
                        "min": 2
                    }
                },
                "scientist": "Dr. Bob Robertson",
                "status": "recommended",
                "submissionTimestamp": "2018-01-01T14:47:23-0600",
                "synonyms": [
                    "Maize Height",
                    "Stalk Height",
                    "Corn Height"
                ],
                "trait": {
                    "alternativeAbbreviations": [
                        "H",
                        "PH",
                        "H1"
                    ],
                    "attribute": "height",
                    "entity": "Stalk",
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
                    "mainAbbreviation": "PH",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "status": "recommended",
                    "synonyms": [
                        "Height",
                        "Plant Height",
                        "Stalk Height",
                        "Canopy Height"
                    ],
                    "traitClass": "phenological",
                    "traitDbId": "9b2e34f5",
                    "traitDescription": "The height of the plant",
                    "traitName": "Height"
                }
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




### Get - /attributes/categories [GET /brapi/v2/attributes/categories{?page}{?pageSize}]

List all available attribute categories.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[string]||


 

+ Parameters
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
            "Morphological",
            "Agronomic"
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




### Get - /attributes/{attributeDbId} [GET /brapi/v2/attributes/{attributeDbId}]

Get the details for a specific Germplasm Attribute



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

+ Parameters
    + attributeDbId (Required, ) ... The unique id for an attribute
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
        "additionalInfo": {},
        "attributeCategory": "Morphological",
        "attributeDbId": "2f08b902",
        "attributeDescription": "Height of the plant measured in meters by a tape",
        "attributeName": "Plant Height 1",
        "commonCropName": "Maize",
        "contextOfUse": [
            "Trial evaluation",
            "Nursery evaluation"
        ],
        "defaultValue": 2.0,
        "documentationURL": "https://wiki.brapi.org/documentation.html",
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
        "growthStage": "flowering",
        "institution": "The BrAPI Institute",
        "language": "en",
        "method": {
            "additionalInfo": {},
            "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
            "description": "A measuring tape was used",
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
            "formula": "a^2 + b^2 = c^2",
            "methodClass": "Measurement",
            "methodDbId": "0adb2764",
            "methodName": "Measuring Tape",
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            }
        },
        "ontologyReference": {
            "documentationLinks": [
                {
                    "URL": "http://purl.obolibrary.org/obo/ro.owl",
                    "type": [
                        "OBO",
                        "RDF",
                        "WEBPAGE"
                    ]
                }
            ],
            "ontologyDbId": "6b071868",
            "ontologyName": "The Crop Ontology",
            "version": "7.2.3"
        },
        "scale": {
            "dataType": [
                "Code",
                "Date",
                "Duration",
                "Nominal",
                "Numerical",
                "Ordinal",
                "Text"
            ],
            "decimalPlaces": 2,
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
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            },
            "scaleDbId": "af730171",
            "scaleName": "Meters",
            "validValues": {
                "categories": [
                    {
                        "label": "low",
                        "value": "0"
                    },
                    {
                        "label": "medium",
                        "value": "5"
                    },
                    {
                        "label": "high",
                        "value": "10"
                    }
                ],
                "max": 9999,
                "min": 2
            }
        },
        "scientist": "Dr. Bob Robertson",
        "status": "recommended",
        "submissionTimestamp": "2018-01-01T14:47:23-0600",
        "synonyms": [
            "Maize Height",
            "Stalk Height",
            "Corn Height"
        ],
        "trait": {
            "alternativeAbbreviations": [
                "H",
                "PH",
                "H1"
            ],
            "attribute": "height",
            "entity": "Stalk",
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
            "mainAbbreviation": "PH",
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            },
            "status": "recommended",
            "synonyms": [
                "Height",
                "Plant Height",
                "Stalk Height",
                "Canopy Height"
            ],
            "traitClass": "phenological",
            "traitDbId": "9b2e34f5",
            "traitDescription": "The height of the plant",
            "traitName": "Height"
        }
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




### Post - /attributes/{attributeDbId} [POST /brapi/v2/attributes/{attributeDbId}]

Create new Germplasm Attributes

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

+ Parameters
    + attributeDbId (Required, ) ... The unique id for an attribute
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "additionalInfo": {},
    "attributeCategory": "Morphological",
    "attributeDescription": "Height of the plant measured in meters by a tape",
    "attributeName": "Plant Height 1",
    "commonCropName": "Maize",
    "contextOfUse": [
        "Trial evaluation",
        "Nursery evaluation"
    ],
    "defaultValue": 2.0,
    "documentationURL": "https://wiki.brapi.org/documentation.html",
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
    "growthStage": "flowering",
    "institution": "The BrAPI Institute",
    "language": "en",
    "method": {
        "additionalInfo": {},
        "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
        "description": "A measuring tape was used",
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
        "formula": "a^2 + b^2 = c^2",
        "methodClass": "Measurement",
        "methodDbId": "0adb2764",
        "methodName": "Measuring Tape",
        "ontologyReference": {
            "documentationLinks": [
                {
                    "URL": "http://purl.obolibrary.org/obo/ro.owl",
                    "type": [
                        "OBO",
                        "RDF",
                        "WEBPAGE"
                    ]
                }
            ],
            "ontologyDbId": "6b071868",
            "ontologyName": "The Crop Ontology",
            "version": "7.2.3"
        }
    },
    "ontologyReference": {
        "documentationLinks": [
            {
                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                "type": [
                    "OBO",
                    "RDF",
                    "WEBPAGE"
                ]
            }
        ],
        "ontologyDbId": "6b071868",
        "ontologyName": "The Crop Ontology",
        "version": "7.2.3"
    },
    "scale": {
        "dataType": [
            "Code",
            "Date",
            "Duration",
            "Nominal",
            "Numerical",
            "Ordinal",
            "Text"
        ],
        "decimalPlaces": 2,
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
        "ontologyReference": {
            "documentationLinks": [
                {
                    "URL": "http://purl.obolibrary.org/obo/ro.owl",
                    "type": [
                        "OBO",
                        "RDF",
                        "WEBPAGE"
                    ]
                }
            ],
            "ontologyDbId": "6b071868",
            "ontologyName": "The Crop Ontology",
            "version": "7.2.3"
        },
        "scaleDbId": "af730171",
        "scaleName": "Meters",
        "validValues": {
            "categories": [
                {
                    "label": "low",
                    "value": "0"
                },
                {
                    "label": "medium",
                    "value": "5"
                },
                {
                    "label": "high",
                    "value": "10"
                }
            ],
            "max": 9999,
            "min": 2
        }
    },
    "scientist": "Dr. Bob Robertson",
    "status": "recommended",
    "submissionTimestamp": "2018-01-01T14:47:23-0600",
    "synonyms": [
        "Maize Height",
        "Stalk Height",
        "Corn Height"
    ],
    "trait": {
        "alternativeAbbreviations": [
            "H",
            "PH",
            "H1"
        ],
        "attribute": "height",
        "entity": "Stalk",
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
        "mainAbbreviation": "PH",
        "ontologyReference": {
            "documentationLinks": [
                {
                    "URL": "http://purl.obolibrary.org/obo/ro.owl",
                    "type": [
                        "OBO",
                        "RDF",
                        "WEBPAGE"
                    ]
                }
            ],
            "ontologyDbId": "6b071868",
            "ontologyName": "The Crop Ontology",
            "version": "7.2.3"
        },
        "status": "recommended",
        "synonyms": [
            "Height",
            "Plant Height",
            "Stalk Height",
            "Canopy Height"
        ],
        "traitClass": "phenological",
        "traitDbId": "9b2e34f5",
        "traitDescription": "The height of the plant",
        "traitName": "Height"
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
        "additionalInfo": {},
        "attributeCategory": "Morphological",
        "attributeDbId": "2f08b902",
        "attributeDescription": "Height of the plant measured in meters by a tape",
        "attributeName": "Plant Height 1",
        "commonCropName": "Maize",
        "contextOfUse": [
            "Trial evaluation",
            "Nursery evaluation"
        ],
        "defaultValue": 2.0,
        "documentationURL": "https://wiki.brapi.org/documentation.html",
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
        "growthStage": "flowering",
        "institution": "The BrAPI Institute",
        "language": "en",
        "method": {
            "additionalInfo": {},
            "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
            "description": "A measuring tape was used",
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
            "formula": "a^2 + b^2 = c^2",
            "methodClass": "Measurement",
            "methodDbId": "0adb2764",
            "methodName": "Measuring Tape",
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            }
        },
        "ontologyReference": {
            "documentationLinks": [
                {
                    "URL": "http://purl.obolibrary.org/obo/ro.owl",
                    "type": [
                        "OBO",
                        "RDF",
                        "WEBPAGE"
                    ]
                }
            ],
            "ontologyDbId": "6b071868",
            "ontologyName": "The Crop Ontology",
            "version": "7.2.3"
        },
        "scale": {
            "dataType": [
                "Code",
                "Date",
                "Duration",
                "Nominal",
                "Numerical",
                "Ordinal",
                "Text"
            ],
            "decimalPlaces": 2,
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
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            },
            "scaleDbId": "af730171",
            "scaleName": "Meters",
            "validValues": {
                "categories": [
                    {
                        "label": "low",
                        "value": "0"
                    },
                    {
                        "label": "medium",
                        "value": "5"
                    },
                    {
                        "label": "high",
                        "value": "10"
                    }
                ],
                "max": 9999,
                "min": 2
            }
        },
        "scientist": "Dr. Bob Robertson",
        "status": "recommended",
        "submissionTimestamp": "2018-01-01T14:47:23-0600",
        "synonyms": [
            "Maize Height",
            "Stalk Height",
            "Corn Height"
        ],
        "trait": {
            "alternativeAbbreviations": [
                "H",
                "PH",
                "H1"
            ],
            "attribute": "height",
            "entity": "Stalk",
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
            "mainAbbreviation": "PH",
            "ontologyReference": {
                "documentationLinks": [
                    {
                        "URL": "http://purl.obolibrary.org/obo/ro.owl",
                        "type": [
                            "OBO",
                            "RDF",
                            "WEBPAGE"
                        ]
                    }
                ],
                "ontologyDbId": "6b071868",
                "ontologyName": "The Crop Ontology",
                "version": "7.2.3"
            },
            "status": "recommended",
            "synonyms": [
                "Height",
                "Plant Height",
                "Stalk Height",
                "Canopy Height"
            ],
            "traitClass": "phenological",
            "traitDbId": "9b2e34f5",
            "traitDescription": "The height of the plant",
            "traitName": "Height"
        }
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




### Post - /search/attributes [POST /brapi/v2/search/attributes]

Search for a set of Germplasm Attributes based on some criteria
        
See Search Services for additional implementation details.

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|attributeDbIds|array[string]|List of Germplasm Attribute IDs to search for|
|attributeNames|array[string]|List of human readable Germplasm Attribute names to search for|
|dataTypes|array[string]|List of scale data types to filter search results|
|externalReferenceIDs|array[string]|List of external references for the trait to search for|
|externalReferenceSources|array[string]|List of external references sources for the trait to search for|
|methodDbIds|array[string]|List of methods to filter search results|
|ontologyDbIds|array[string]|List of ontology IDs to search for|
|page|integer|Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.|
|pageSize|integer|The size of the pages to be returned. Default is `1000`.|
|scaleDbIds|array[string]|List of scales to filter search results|
|studyDbId|array[string]|The unique ID of a studies to filter on|
|traitClasses|array[string]|List of trait classes to filter search results|
|traitDbIds|array[string]|List of trait unique ID to filter search results|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "attributeDbIds": [
        "2ef15c9f",
        "318e7f7d"
    ],
    "attributeNames": [
        "Plant Height 1",
        "Root Color"
    ],
    "dataTypes": [
        "Numerical",
        "Ordinal",
        "Text"
    ],
    "externalReferenceIDs": [
        "http://purl.obolibrary.org/obo/ro.owl",
        "14a19841"
    ],
    "externalReferenceSources": [
        "OBO Library",
        "Field App Name"
    ],
    "methodDbIds": [
        "07e34f83",
        "d3d5517a"
    ],
    "ontologyDbIds": [
        "f44f7b23",
        "a26b576e"
    ],
    "page": 0,
    "pageSize": 1000,
    "scaleDbIds": [
        "a13ecffa",
        "7e1afe4f"
    ],
    "studyDbId": [
        "5bcac0ae",
        "7f48e22d"
    ],
    "traitClasses": [
        "morphological",
        "phenological",
        "agronomical"
    ],
    "traitDbIds": [
        "ef81147b",
        "78d82fad"
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
                "additionalInfo": {},
                "attributeCategory": "Morphological",
                "attributeDbId": "2f08b902",
                "attributeDescription": "Height of the plant measured in meters by a tape",
                "attributeName": "Plant Height 1",
                "commonCropName": "Maize",
                "contextOfUse": [
                    "Trial evaluation",
                    "Nursery evaluation"
                ],
                "defaultValue": 2.0,
                "documentationURL": "https://wiki.brapi.org/documentation.html",
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
                "growthStage": "flowering",
                "institution": "The BrAPI Institute",
                "language": "en",
                "method": {
                    "additionalInfo": {},
                    "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
                    "description": "A measuring tape was used",
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
                    "formula": "a^2 + b^2 = c^2",
                    "methodClass": "Measurement",
                    "methodDbId": "0adb2764",
                    "methodName": "Measuring Tape",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    }
                },
                "ontologyReference": {
                    "documentationLinks": [
                        {
                            "URL": "http://purl.obolibrary.org/obo/ro.owl",
                            "type": [
                                "OBO",
                                "RDF",
                                "WEBPAGE"
                            ]
                        }
                    ],
                    "ontologyDbId": "6b071868",
                    "ontologyName": "The Crop Ontology",
                    "version": "7.2.3"
                },
                "scale": {
                    "dataType": [
                        "Code",
                        "Date",
                        "Duration",
                        "Nominal",
                        "Numerical",
                        "Ordinal",
                        "Text"
                    ],
                    "decimalPlaces": 2,
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
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "scaleDbId": "af730171",
                    "scaleName": "Meters",
                    "validValues": {
                        "categories": [
                            {
                                "label": "low",
                                "value": "0"
                            },
                            {
                                "label": "medium",
                                "value": "5"
                            },
                            {
                                "label": "high",
                                "value": "10"
                            }
                        ],
                        "max": 9999,
                        "min": 2
                    }
                },
                "scientist": "Dr. Bob Robertson",
                "status": "recommended",
                "submissionTimestamp": "2018-01-01T14:47:23-0600",
                "synonyms": [
                    "Maize Height",
                    "Stalk Height",
                    "Corn Height"
                ],
                "trait": {
                    "alternativeAbbreviations": [
                        "H",
                        "PH",
                        "H1"
                    ],
                    "attribute": "height",
                    "entity": "Stalk",
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
                    "mainAbbreviation": "PH",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "status": "recommended",
                    "synonyms": [
                        "Height",
                        "Plant Height",
                        "Stalk Height",
                        "Canopy Height"
                    ],
                    "traitClass": "phenological",
                    "traitDbId": "9b2e34f5",
                    "traitDescription": "The height of the plant",
                    "traitName": "Height"
                }
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




### Get - /search/attributes/{searchResultsDbId} [GET /brapi/v2/search/attributes/{searchResultsDbId}{?page}{?pageSize}]

Get the results of a Germplasm Attributes search request

See Search Services for additional implementation details.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|attributeCategory|string|General category for the attribute. very similar to Trait class.|
|attributeDbId|string|The ID which uniquely identifies this attribute within the given database server|
|attributeDescription|string|A human readable description of this attribute|
|attributeName|string|A human readable name for this attribute|
|commonCropName|string|Crop name (examples: "Maize", "Wheat")|
|contextOfUse|array[string]|Indication of how trait is routinely used. (examples: ["Trial evaluation", "Nursery evaluation"])|
|defaultValue|string|Variable default value. (examples: "red", "2.3", etc.)|
|documentationURL|string (uri)|A URL to the human readable documentation of this object|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|growthStage|string|Growth stage at which measurement is made (examples: "flowering")|
|institution|string|Name of institution submitting the variable|
|language|string|2 letter ISO 639-1 code for the language of submission of the variable.|
|method|object||
|additionalInfo|object|Additional arbitrary info|
|bibliographicalReference|string|Bibliographical reference describing the method.  MIAPPE V1.1 (DM-91) Reference associated to the method - URI/DOI of reference describing the method.|
|description|string|Method description  MIAPPE V1.1 (DM-90) Method description - Textual description of the method, which may extend a method defined in an external reference with specific parameters, e.g. growth stage, inoculation precise organ (leaf number)|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|formula|string|For computational methods i.e., when the method consists in assessing the trait by computing measurements, write the generic formula used for the calculation|
|methodClass|string|Method class (examples: "Measurement", "Counting", "Estimation", "Computation", etc.)|
|methodDbId|string|Method unique identifier|
|methodName|string|Human readable name for the method  MIAPPE V1.1 (DM-88) Method  Name of the method of observation|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scale|object|Scale metadata|
|dataType|string|<p>Class of the scale, entries can be</p> <p>"Code" -  This scale class is exceptionally used to express complex traits. Code is a nominal scale that combines the expressions of the different traits composing the complex trait. For example a severity trait might be expressed by a 2 digit and 2 character code. The first 2 digits are the percentage of the plant covered by a fungus and the 2 characters refer to the delay in development, e.g. "75VD" means "75 %" of the plant is infected and the plant is very delayed.</p> <p>"Date" - The date class is for events expressed in a time format, See ISO 8601</p> <p>"Duration" - The Duration class is for time elapsed between two events expressed in a time format, e.g. days, hours, months</p> <p>"Nominal" - Categorical scale that can take one of a limited and fixed number of categories. There is no intrinsic ordering to the categories</p> <p>"Numerical" - Numerical scales express the trait with real numbers. The numerical scale defines the unit e.g. centimeter, ton per hectare, branches</p> <p>"Ordinal" - Ordinal scales are scales composed of ordered categories</p> <p>"Text" - A free text is used to express the trait.</p>|
|decimalPlaces|integer|For numerical, number of decimal places to be reported|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|scaleDbId|string|Unique identifier of the scale. If left blank, the upload system will automatically generate a scale ID.|
|scaleName|string|Name of the scale  MIAPPE V1.1 (DM-92) Scale Name of the scale associated with the variable|
|validValues|object||
|categories|array[object]|List of possible values with optional labels|
|label|string|A text label for a category|
|value|string|The actual value for a category|
|max|integer|Maximum value (used for field data capture control).|
|min|integer|Minimum value (used for data capture control) for numerical and date scales|
|scientist|string|Name of scientist submitting the variable.|
|status|string|Variable status. (examples: "recommended", "obsolete", "legacy", etc.)|
|submissionTimestamp|string (date-time)|Timestamp when the Variable was added (ISO 8601)|
|synonyms|array[string]|Other variable names|
|trait|object||
|alternativeAbbreviations|array[string]|Other frequent abbreviations of the trait, if any. These abbreviations do not have to follow a convention|
|attribute|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the attribute is the observed feature (or characteristic) of the entity e.g., for "grain colour", attribute = "colour"|
|entity|string|A trait can be decomposed as "Trait" = "Entity" + "Attribute", the entity is the part of the plant that the trait refers to e.g., for "grain colour", entity = "grain"|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|mainAbbreviation|string|Main abbreviation for trait name. (examples: "Carotenoid content" => "CC")|
|ontologyReference|object|MIAPPE V1.1  (DM-85) Variable accession number - Accession number of the variable in the Crop Ontology  (DM-87) Trait accession number - Accession number of the trait in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-89) Method accession number - Accession number of the method in a suitable controlled vocabulary (Crop Ontology, Trait Ontology).  (DM-93) Scale accession number - Accession number of the scale in a suitable controlled vocabulary (Crop Ontology).|
|documentationLinks|array[object]|links to various ontology documentation|
|URL|string (uri)||
|type|string||
|ontologyDbId|string|Ontology database unique identifier|
|ontologyName|string|Ontology name|
|version|string|Ontology version (no specific format)|
|status|string|Trait status (examples: "recommended", "obsolete", "legacy", etc.)|
|synonyms|array[string]|Other trait names|
|traitClass|string|Trait class. (examples: "morphological", "phenological", "agronomical", "physiological", "abiotic stress", "biotic stress", "biochemical", "quality traits", "fertility", etc.)|
|traitDbId|string|The ID which uniquely identifies a trait|
|traitDescription|string|The description of a trait|
|traitName|string|The human readable name of a trait  MIAPPE V1.1 (DM-86) Trait - Name of the (plant or environmental) trait under observation|


 

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
                "additionalInfo": {},
                "attributeCategory": "Morphological",
                "attributeDbId": "2f08b902",
                "attributeDescription": "Height of the plant measured in meters by a tape",
                "attributeName": "Plant Height 1",
                "commonCropName": "Maize",
                "contextOfUse": [
                    "Trial evaluation",
                    "Nursery evaluation"
                ],
                "defaultValue": 2.0,
                "documentationURL": "https://wiki.brapi.org/documentation.html",
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
                "growthStage": "flowering",
                "institution": "The BrAPI Institute",
                "language": "en",
                "method": {
                    "additionalInfo": {},
                    "bibliographicalReference": "Smith, 1893, Really Cool Paper, Popular Journal",
                    "description": "A measuring tape was used",
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
                    "formula": "a^2 + b^2 = c^2",
                    "methodClass": "Measurement",
                    "methodDbId": "0adb2764",
                    "methodName": "Measuring Tape",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    }
                },
                "ontologyReference": {
                    "documentationLinks": [
                        {
                            "URL": "http://purl.obolibrary.org/obo/ro.owl",
                            "type": [
                                "OBO",
                                "RDF",
                                "WEBPAGE"
                            ]
                        }
                    ],
                    "ontologyDbId": "6b071868",
                    "ontologyName": "The Crop Ontology",
                    "version": "7.2.3"
                },
                "scale": {
                    "dataType": [
                        "Code",
                        "Date",
                        "Duration",
                        "Nominal",
                        "Numerical",
                        "Ordinal",
                        "Text"
                    ],
                    "decimalPlaces": 2,
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
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "scaleDbId": "af730171",
                    "scaleName": "Meters",
                    "validValues": {
                        "categories": [
                            {
                                "label": "low",
                                "value": "0"
                            },
                            {
                                "label": "medium",
                                "value": "5"
                            },
                            {
                                "label": "high",
                                "value": "10"
                            }
                        ],
                        "max": 9999,
                        "min": 2
                    }
                },
                "scientist": "Dr. Bob Robertson",
                "status": "recommended",
                "submissionTimestamp": "2018-01-01T14:47:23-0600",
                "synonyms": [
                    "Maize Height",
                    "Stalk Height",
                    "Corn Height"
                ],
                "trait": {
                    "alternativeAbbreviations": [
                        "H",
                        "PH",
                        "H1"
                    ],
                    "attribute": "height",
                    "entity": "Stalk",
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
                    "mainAbbreviation": "PH",
                    "ontologyReference": {
                        "documentationLinks": [
                            {
                                "URL": "http://purl.obolibrary.org/obo/ro.owl",
                                "type": [
                                    "OBO",
                                    "RDF",
                                    "WEBPAGE"
                                ]
                            }
                        ],
                        "ontologyDbId": "6b071868",
                        "ontologyName": "The Crop Ontology",
                        "version": "7.2.3"
                    },
                    "status": "recommended",
                    "synonyms": [
                        "Height",
                        "Plant Height",
                        "Stalk Height",
                        "Canopy Height"
                    ],
                    "traitClass": "phenological",
                    "traitDbId": "9b2e34f5",
                    "traitDescription": "The height of the plant",
                    "traitName": "Height"
                }
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

# Group Planned Crosses






### Get - /plannedcrosses [GET /brapi/v2/plannedcrosses{?crossingProjectDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Get a filtered list of Planned Cross entities.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|plannedCrossDbId|string|the unique identifier for a cross|
|plannedCrossName|string|the human readable name for a cross|


 

+ Parameters
    + crossingProjectDbId (Optional, ) ... Search for Crossing Projects with this unique id
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
                "additionalInfo": {},
                "crossType": "BIPARENTAL",
                "crossingProjectDbId": "696d7c92",
                "crossingProjectName": "my_Ibadan_Crosses_2018",
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
                "parent1": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "parent2": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "plannedCrossDbId": "c8905568",
                "plannedCrossName": "my_Ibadan_Crosses_2018_01"
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




### Post - /plannedcrosses [POST /brapi/v2/plannedcrosses]

Create new Planned Cross entities on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|plannedCrossName|string|the human readable name for a cross|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|plannedCrossDbId|string|the unique identifier for a cross|
|plannedCrossName|string|the human readable name for a cross|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "additionalInfo": {},
        "crossType": "BIPARENTAL",
        "crossingProjectDbId": "696d7c92",
        "crossingProjectName": "my_Ibadan_Crosses_2018",
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
        "parent1": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": [
                "MALE",
                "FEMALE",
                "SELF",
                "POPULATION"
            ]
        },
        "parent2": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": [
                "MALE",
                "FEMALE",
                "SELF",
                "POPULATION"
            ]
        },
        "plannedCrossName": "my_Ibadan_Crosses_2018_01"
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
                "additionalInfo": {},
                "crossType": "BIPARENTAL",
                "crossingProjectDbId": "696d7c92",
                "crossingProjectName": "my_Ibadan_Crosses_2018",
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
                "parent1": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "parent2": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "plannedCrossDbId": "c8905568",
                "plannedCrossName": "my_Ibadan_Crosses_2018_01"
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




### Put - /plannedcrosses [PUT /brapi/v2/plannedcrosses]

Update existing Planned Cross entities on this server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|crossType|string|the type of cross|
|crossingProjectDbId|string|the unique identifier for a crossing project|
|crossingProjectName|string|the human readable name for a crossing project|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|parent1|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|parent2|object||
|germplasmDbId|string|the unique identifier for a germplasm|
|germplasmName|string|the human readable name for a germplasm|
|observationUnitDbId|string|the unique identifier for an observation unit|
|observationUnitName|string|the human readable name for an observation unit|
|parentType|string|The type of parent ex. 'MALE', 'FEMALE', 'SELF', 'POPULATION', etc.|
|plannedCrossDbId|string|the unique identifier for a cross|
|plannedCrossName|string|the human readable name for a cross|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "c8905568": {
        "additionalInfo": {},
        "crossAttributes": [
            {
                "crossAttributeName": "string",
                "crossAttributeValue": "string"
            }
        ],
        "crossName": "my_Ibadan_Crosses_2018_01",
        "crossType": "BIPARENTAL",
        "crossingProjectDbId": "696d7c92",
        "crossingProjectName": "my_Ibadan_Crosses_2018",
        "parent1": {
            "germplasmDbId": "d34b10c3",
            "germplasmName": "TME_419",
            "observationUnitDbId": "2e1926a7",
            "observationUnitName": "my_Ibadan_Plot_9001",
            "parentType": "MALE"
        },
        "parent2": {
            "germplasmDbId": "843fb211",
            "germplasmName": "TME_419",
            "observationUnitDbId": "f05e955f",
            "observationUnitName": "my_Ibadan_Plot_9002",
            "parentType": "FEMALE"
        }
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
                "additionalInfo": {},
                "crossType": "BIPARENTAL",
                "crossingProjectDbId": "696d7c92",
                "crossingProjectName": "my_Ibadan_Crosses_2018",
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
                "parent1": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "parent2": {
                    "germplasmDbId": "d34b10c3",
                    "germplasmName": "TME_419",
                    "observationUnitDbId": "2e1926a7",
                    "observationUnitName": "my_Ibadan_Plot_9001",
                    "parentType": [
                        "MALE",
                        "FEMALE",
                        "SELF",
                        "POPULATION"
                    ]
                },
                "plannedCrossDbId": "c8905568",
                "plannedCrossName": "my_Ibadan_Crosses_2018_01"
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

# Group SeedLots






### Get - /seedlots [GET /brapi/v2/seedlots{?seedLotDbId}{?germplasmDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Get a filtered list of Seed Lot descriptions available in a system.



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|amount|number|Current balance of seeds in this lot. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|createdDate|string (date-time)|The time stamp for when this seed lot was created|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|Unique DbId of the Germplasm held in this Seed Lot|
|lastUpdated|string (date-time)|The timestamp for the last update to this Seed Lot (including transactions)|
|locationDbId|string|DbId of the storage location|
|programDbId|string|Unique DbId of the breeding Program this Seed Lot belongs to|
|seedLotDbId|string|Unique DbId for the Seed Lot|
|seedLotDescription|string|A general description of this Seed Lot|
|seedLotName|string|A human readable name for this Seed Lot|
|sourceCollection|string|The description of the source where this material was originally collected (wild, nursery, etc)|
|storageLocation|string|Description the storage location|
|units|string|Description of the things being counted in this Seed Lot (seeds, bulbs, kg, tree, etc)|


 

+ Parameters
    + seedLotDbId (Optional, ) ... Unique id for a seed lot on this server
    + germplasmDbId (Optional, ) ... The internal id of the germplasm
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
                "additionalInfo": {},
                "amount": 561,
                "createdDate": "2018-01-01T14:47:23-0600",
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
                "germplasmDbId": "029d705d",
                "lastUpdated": "2018-01-01T14:47:23-0600",
                "locationDbId": "7989c44c",
                "programDbId": "e972d569",
                "seedLotDbId": "261ecb09",
                "seedLotDescription": "This is a description of a seed lot",
                "seedLotName": "Seed Lot Alpha",
                "sourceCollection": "nursery",
                "storageLocation": "The storage location is an massive, underground, bunker.",
                "units": "seeds"
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




### Post - /seedlots [POST /brapi/v2/seedlots]

Add new Seed Lot descriptions to a server

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|amount|number|Current balance of seeds in this lot. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|createdDate|string (date-time)|The time stamp for when this seed lot was created|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|Unique DbId of the Germplasm held in this Seed Lot|
|lastUpdated|string (date-time)|The timestamp for the last update to this Seed Lot (including transactions)|
|locationDbId|string|DbId of the storage location|
|programDbId|string|Unique DbId of the breeding Program this Seed Lot belongs to|
|seedLotDescription|string|A general description of this Seed Lot|
|seedLotName|string|A human readable name for this Seed Lot|
|sourceCollection|string|The description of the source where this material was originally collected (wild, nursery, etc)|
|storageLocation|string|Description the storage location|
|units|string|Description of the things being counted in this Seed Lot (seeds, bulbs, kg, tree, etc)|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|amount|number|Current balance of seeds in this lot. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|createdDate|string (date-time)|The time stamp for when this seed lot was created|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|Unique DbId of the Germplasm held in this Seed Lot|
|lastUpdated|string (date-time)|The timestamp for the last update to this Seed Lot (including transactions)|
|locationDbId|string|DbId of the storage location|
|programDbId|string|Unique DbId of the breeding Program this Seed Lot belongs to|
|seedLotDbId|string|Unique DbId for the Seed Lot|
|seedLotDescription|string|A general description of this Seed Lot|
|seedLotName|string|A human readable name for this Seed Lot|
|sourceCollection|string|The description of the source where this material was originally collected (wild, nursery, etc)|
|storageLocation|string|Description the storage location|
|units|string|Description of the things being counted in this Seed Lot (seeds, bulbs, kg, tree, etc)|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
[
    {
        "additionalInfo": {},
        "amount": 561,
        "createdDate": "2018-01-01T14:47:23-0600",
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
        "germplasmDbId": "029d705d",
        "lastUpdated": "2018-01-01T14:47:23-0600",
        "locationDbId": "7989c44c",
        "programDbId": "e972d569",
        "seedLotDescription": "This is a description of a seed lot",
        "seedLotName": "Seed Lot Alpha",
        "sourceCollection": "nursery",
        "storageLocation": "The storage location is an massive, underground, bunker.",
        "units": "seeds"
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
                "additionalInfo": {},
                "amount": 561,
                "createdDate": "2018-01-01T14:47:23-0600",
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
                "germplasmDbId": "029d705d",
                "lastUpdated": "2018-01-01T14:47:23-0600",
                "locationDbId": "7989c44c",
                "programDbId": "e972d569",
                "seedLotDbId": "261ecb09",
                "seedLotDescription": "This is a description of a seed lot",
                "seedLotName": "Seed Lot Alpha",
                "sourceCollection": "nursery",
                "storageLocation": "The storage location is an massive, underground, bunker.",
                "units": "seeds"
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




### Get - /seedlots/transactions [GET /brapi/v2/seedlots/transactions{?transactionDbId}{?seedLotDbId}{?germplasmDbId}{?externalReferenceID}{?externalReferenceSource}{?page}{?pageSize}]

Get a filtered list of Seed Lot Transactions



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|amount|number|The amount of units being transfered. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|fromSeedLotDbId|string|The identifier for the Seed Lot being transfered out of|
|toSeedLotDbId|string|The identifier for the Seed Lot being transfered into|
|transactionDbId|string|Unique DbId for the Seed Lot Transaction|
|transactionDescription|string|A general description of this Seed Lot Transaction|
|transactionTimestamp|string (date-time)|The time stamp for when the transaction occured|
|units|string|Description of the things being transfered in this transaction (seeds, bulbs, kg, etc)|


 

+ Parameters
    + transactionDbId (Optional, ) ... Unique id for a transaction on this server
    + seedLotDbId (Optional, ) ... Unique id for a seed lot on this server
    + germplasmDbId (Optional, ) ... The internal id of the germplasm
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
                "additionalInfo": {},
                "amount": 45,
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
                "fromSeedLotDbId": "11eef13b",
                "toSeedLotDbId": "59339b90",
                "transactionDbId": "28e46db9",
                "transactionDescription": "f9cd88d2",
                "transactionTimestamp": "2018-01-01T14:47:23-0600",
                "units": "seeds"
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




### Post - /seedlots/transactions [POST /brapi/v2/seedlots/transactions]

Add new Seed Lot Transaction to be recorded

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|seedLots|array[object]||
|additionalInfo|object|Additional arbitrary info|
|amount|number|The amount of units being transfered. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|fromSeedLotDbId|string|The identifier for the Seed Lot being transfered out of|
|toSeedLotDbId|string|The identifier for the Seed Lot being transfered into|
|transactionDescription|string|A general description of this Seed Lot Transaction|
|transactionTimestamp|string (date-time)|The time stamp for when the transaction occured|
|units|string|Description of the things being transfered in this transaction (seeds, bulbs, kg, etc)|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|amount|number|The amount of units being transfered. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|fromSeedLotDbId|string|The identifier for the Seed Lot being transfered out of|
|toSeedLotDbId|string|The identifier for the Seed Lot being transfered into|
|transactionDbId|string|Unique DbId for the Seed Lot Transaction|
|transactionDescription|string|A general description of this Seed Lot Transaction|
|transactionTimestamp|string (date-time)|The time stamp for when the transaction occured|
|units|string|Description of the things being transfered in this transaction (seeds, bulbs, kg, etc)|


 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "seedLots": [
        {
            "additionalInfo": {},
            "amount": 45,
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
            "fromSeedLotDbId": "11eef13b",
            "toSeedLotDbId": "59339b90",
            "transactionDescription": "f9cd88d2",
            "transactionTimestamp": "2018-01-01T14:47:23-0600",
            "units": "seeds"
        }
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
                "additionalInfo": {},
                "amount": 45,
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
                "fromSeedLotDbId": "11eef13b",
                "toSeedLotDbId": "59339b90",
                "transactionDbId": "28e46db9",
                "transactionDescription": "f9cd88d2",
                "transactionTimestamp": "2018-01-01T14:47:23-0600",
                "units": "seeds"
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




### Get - /seedlots/{seedLotDbId} [GET /brapi/v2/seedlots/{seedLotDbId}]

Get a specific Seed Lot by seedLotDbId



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|amount|number|Current balance of seeds in this lot. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|createdDate|string (date-time)|The time stamp for when this seed lot was created|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|Unique DbId of the Germplasm held in this Seed Lot|
|lastUpdated|string (date-time)|The timestamp for the last update to this Seed Lot (including transactions)|
|locationDbId|string|DbId of the storage location|
|programDbId|string|Unique DbId of the breeding Program this Seed Lot belongs to|
|seedLotDbId|string|Unique DbId for the Seed Lot|
|seedLotDescription|string|A general description of this Seed Lot|
|seedLotName|string|A human readable name for this Seed Lot|
|sourceCollection|string|The description of the source where this material was originally collected (wild, nursery, etc)|
|storageLocation|string|Description the storage location|
|units|string|Description of the things being counted in this Seed Lot (seeds, bulbs, kg, tree, etc)|


 

+ Parameters
    + seedLotDbId (Required, ) ... Unique id for a seed lot on this server
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
        "additionalInfo": {},
        "amount": 561,
        "createdDate": "2018-01-01T14:47:23-0600",
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
        "germplasmDbId": "029d705d",
        "lastUpdated": "2018-01-01T14:47:23-0600",
        "locationDbId": "7989c44c",
        "programDbId": "e972d569",
        "seedLotDbId": "261ecb09",
        "seedLotDescription": "This is a description of a seed lot",
        "seedLotName": "Seed Lot Alpha",
        "sourceCollection": "nursery",
        "storageLocation": "The storage location is an massive, underground, bunker.",
        "units": "seeds"
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




### Put - /seedlots/{seedLotDbId} [PUT /brapi/v2/seedlots/{seedLotDbId}]

Update an existing Seed Lot

**Request Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|amount|number|Current balance of seeds in this lot. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|createdDate|string (date-time)|The time stamp for when this seed lot was created|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|Unique DbId of the Germplasm held in this Seed Lot|
|lastUpdated|string (date-time)|The timestamp for the last update to this Seed Lot (including transactions)|
|locationDbId|string|DbId of the storage location|
|programDbId|string|Unique DbId of the breeding Program this Seed Lot belongs to|
|seedLotDescription|string|A general description of this Seed Lot|
|seedLotName|string|A human readable name for this Seed Lot|
|sourceCollection|string|The description of the source where this material was originally collected (wild, nursery, etc)|
|storageLocation|string|Description the storage location|
|units|string|Description of the things being counted in this Seed Lot (seeds, bulbs, kg, tree, etc)|


**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|additionalInfo|object|Additional arbitrary info|
|amount|number|Current balance of seeds in this lot. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|createdDate|string (date-time)|The time stamp for when this seed lot was created|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|germplasmDbId|string|Unique DbId of the Germplasm held in this Seed Lot|
|lastUpdated|string (date-time)|The timestamp for the last update to this Seed Lot (including transactions)|
|locationDbId|string|DbId of the storage location|
|programDbId|string|Unique DbId of the breeding Program this Seed Lot belongs to|
|seedLotDbId|string|Unique DbId for the Seed Lot|
|seedLotDescription|string|A general description of this Seed Lot|
|seedLotName|string|A human readable name for this Seed Lot|
|sourceCollection|string|The description of the source where this material was originally collected (wild, nursery, etc)|
|storageLocation|string|Description the storage location|
|units|string|Description of the things being counted in this Seed Lot (seeds, bulbs, kg, tree, etc)|


 

+ Parameters
    + seedLotDbId (Required, ) ... Unique id for a seed lot on this server
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization <strong> Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "additionalInfo": {},
    "amount": 561,
    "createdDate": "2018-01-01T14:47:23-0600",
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
    "germplasmDbId": "029d705d",
    "lastUpdated": "2018-01-01T14:47:23-0600",
    "locationDbId": "7989c44c",
    "programDbId": "e972d569",
    "seedLotDescription": "This is a description of a seed lot",
    "seedLotName": "Seed Lot Alpha",
    "sourceCollection": "nursery",
    "storageLocation": "The storage location is an massive, underground, bunker.",
    "units": "seeds"
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
        "additionalInfo": {},
        "amount": 561,
        "createdDate": "2018-01-01T14:47:23-0600",
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
        "germplasmDbId": "029d705d",
        "lastUpdated": "2018-01-01T14:47:23-0600",
        "locationDbId": "7989c44c",
        "programDbId": "e972d569",
        "seedLotDbId": "261ecb09",
        "seedLotDescription": "This is a description of a seed lot",
        "seedLotName": "Seed Lot Alpha",
        "sourceCollection": "nursery",
        "storageLocation": "The storage location is an massive, underground, bunker.",
        "units": "seeds"
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




### Get - /seedlots/{seedLotDbId}/transactions [GET /brapi/v2/seedlots/{seedLotDbId}/transactions{?transactionDbId}{?transactionDirection}{?page}{?pageSize}]

Get all Transactions related to a specific Seed Lot



**Response Fields** 

|Field|Type|Description|
|---|---|---| 
|data|array[object]||
|additionalInfo|object|Additional arbitrary info|
|amount|number|The amount of units being transfered. Could be a count (seeds, bulbs, etc) or a weight (kg of seed).|
|externalReferences|array[object]|An array of external reference ids. These are references to this piece of data in an external system. Could be a simple string or a URI.|
|referenceID||The external reference ID. Could be a simple string or a URI.|
|referenceSource|string|An identifier for the source system or database of this reference|
|fromSeedLotDbId|string|The identifier for the Seed Lot being transfered out of|
|toSeedLotDbId|string|The identifier for the Seed Lot being transfered into|
|transactionDbId|string|Unique DbId for the Seed Lot Transaction|
|transactionDescription|string|A general description of this Seed Lot Transaction|
|transactionTimestamp|string (date-time)|The time stamp for when the transaction occured|
|units|string|Description of the things being transfered in this transaction (seeds, bulbs, kg, etc)|


 

+ Parameters
    + seedLotDbId (Required, ) ... Unique id for a seed lot on this server
    + transactionDbId (Optional, ) ... Unique id for a Transaction that has occured
    + transactionDirection (Optional, ) ... Filter results to only include transactions directed to the specific Seed Lot (TO), away from the specific Seed Lot (FROM), or both (BOTH). The default value for this parameter is BOTH
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
                "additionalInfo": {},
                "amount": 45,
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
                "fromSeedLotDbId": "11eef13b",
                "toSeedLotDbId": "59339b90",
                "transactionDbId": "28e46db9",
                "transactionDescription": "f9cd88d2",
                "transactionTimestamp": "2018-01-01T14:47:23-0600",
                "units": "seeds"
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
