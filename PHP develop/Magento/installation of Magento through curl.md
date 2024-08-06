### Downloads Usage:

  `[wget|curl -O] https://MAG_ID:TOKEN@www.magentocommerce.com/products/downloads/file/[FILENAME]`

### Info Usage:

  `curl https://MAG_ID:TOKEN@www.magentocommerce.com/products/downloads/info/[OPTION]/[PARAMS]`

### Options:

|          |                                                                                    |
| -------- | ---------------------------------------------------------------------------------- |
| help     | This help                                                                          |
| files    | List of all available files for download                                           |
| versions | Versions list                                                                      |
| filter   | Filtered list of all available files for download (see "Filter Options" for usage) |
| json     | The JSON feed of all available files                                               |



### Filter Params:

  version       Shows files by version number. You can use wildcard.
                Example: /downloads/info/filter/version/1.9.2.1
                Example: /downloads/info/filter/version/1.9.*

  type          Shows files by file type:



|          |
| -------- |
| ce-full  |
| ee-full  |
| ce-patch |
| ee-patch |
| other    |



 Example: `/downloads/info/filter/type/ce-full`
