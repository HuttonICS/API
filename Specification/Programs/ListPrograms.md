## Program list [/brapi/v1/programs]
Call to retrieve a list of programs.

Status: ACCEPTED
Implemented By:

### List programs [GET /brapi/v1/programs{?programName}{?abbreviation}{?commonCropName}{?pageSize}{?page}]

+ Parameters
    + programName (optional, string, `Internation Yield Trial`) ... Filter by program name. Exact match.
    + abbreviation (optional, string, `IYT`) ... Filter by program abbreviation. Exact match.
    + commonCropName (optional, string, `wheat`) ... The common crop name. Important for multi-crop systems.
    + pageSize (optional, integer, `1000`) ... The size of the pages to be returned. Default is `1000`.
    + page (optional, integer, `0`) ... Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.

+ Response 200 (application/json)
        
        {
            "metadata" : {
                "pagination": {
                    "pageSize": 1000,
                    "currentPage": 0,
                    "totalCount": 2,
                    "totalPages": 1
                },
                "status": [],
                "datafiles": []
            },
            "result" : {
                "data" : [
                    {
                        "programDbId": "123",
                        "name": "Wheat Resistance Program",
                        "abbreviation" : "DRP1",
                        "objective" : "Disease resistance",
                        "leadPerson" : "Dr. Henry Beachell",
                        "commonCropName": "wheat"
                    },
                    {
                        "programDbId": "456",
                        "name": "Wheat Improvement Program",
                        "abbreviation" : "DRP2",
                        "objective" : "Yield improvement",
                        "leadPerson" : "Dr. Norman Borlaug",
                        "commonCropName": "wheat"
                    }
                ]
            }
        }
    
