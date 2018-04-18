## Program Search [/brapi/v1/programs-search]
Advanced searching for the programs resource.

Status: ACCEPTED.

See <a href="#introduction/search-services">Search Services</a> for additional implementation details.

### Search Programs [POST /brapi/v1/programs-search]

+ Request (application/json)
        
        {
            "programDbId": "123",
            "name": "Wheat Resistance Program",
            "abbreviation" : "DRP1",
            "objective" : "Disease resistance",
            "leadPerson" : "Dr. Henry Beachell",
            "commonCropName": "wheat",
            "pageSize": 1000,
            "page": 0
        }

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
