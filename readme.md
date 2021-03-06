# ago-tools

A Python package to assist with administering ArcGIS Online Organizations.

## Features
* Create a spreadsheet of all users in the org
* Update map service urls in webmaps

## Instructions

1. Fork and then clone the repo. 
2. Run and try the samples.

## Installation
Unzip into a folder such as C:/myscripts, then either:

* add that directory to your system path in advanced system settings
* append it at runtime using the sys module in python
    
        import sys
        sys.path.append('c:/myscripts')

## Samples

#### Admin Class
 
#### Create a spreadsheet of all users in the org
	import csv
    from ago-tools.admin import Admin
    agoAdmin = Admin(<username>)
    users = agoAdmin.getUsers()

    outputFile = 'c:/temp/users.csv'

    with open(outputFile, 'wb') as output:
        dataWriter = csv.writer(output, delimiter=',',
                                quotechar='|', quoting=csv.QUOTE_MINIMAL)
        # Write header row.
        dataWriter.writerow(['Full Name', 'Username', 'Role'])
        # Write user data.
        for user in users:
            dataWriter.writerow([user['fullName'], user['username'], user['role']])

            
#### Utilities Class
            
#### Update map service urls in webmaps
    from ago-tools.utilities import Utilities
    agoUtilities = Utilities(<username>)

    webmapId = 'e1d78110b0eg447aab46d373c7360046'
    oldUrl = 'http://myserver.com/arcgis/rest/services/old/MapServer'
    newUrl = 'http://myserver.com/arcgis/rest/services/new/MapServer'

    agoUtilities.updateWebmapService(webmapId, oldUrl, newUrl)
        
## Requirements

* Python
* Notepad or your favorite Python editor

## Resources

* [Python for ArcGIS Resource Center](http://resources.arcgis.com/en/communities/python/)
* [ArcGIS Blog](http://blogs.esri.com/esri/arcgis/)
* [twitter@esri](http://twitter.com/esri)

## Issues

Find a bug or want to request a new feature?  Please let us know by submitting an issue.

## Contributing

Anyone and everyone is welcome to contribute. 

## Licensing
Copyright 2013 Esri

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

A copy of the license is available in the repository's [license.txt](https://raw.github.com/Esri/ago-tools/master/license.txt) file.

[](Esri Tags: ago-tools)
[](Esri Language: Python)