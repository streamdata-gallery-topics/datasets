swagger: "2.0"
x-collection-name: Xibo
x-complete: 1
info:
  title: Xibo API
  description: xibo-cms-api
  termsOfService: http://xibo.org.uk/legal
  version: 1.0.0
basePath: /api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /dataset:
    get:
      summary: DataSet Search
      description: Search this users DataSets
      operationId: dataSetSearch
      x-api-path-slug: dataset-get
      parameters:
      - in: formData
        name: code
        description: Filter by DataSet Code
      - in: formData
        name: dataSet
        description: Filter by DataSet Name
      - in: formData
        name: dataSetId
        description: Filter by DataSet Id
      - in: formData
        name: embed
        description: Embed related data such as columns
      responses:
        200:
          description: OK
      tags:
      - DataSet
      - Search
    post:
      summary: Add DataSet
      description: Add a DataSet
      operationId: dataSetAdd
      x-api-path-slug: dataset-post
      parameters:
      - in: formData
        name: authentication
        description: HTTP Authentication method None|Basic|Digest
      - in: formData
        name: clearRate
        description: How often in seconds should this remote DataSet be truncated
      - in: formData
        name: code
        description: A code for this DataSet
      - in: formData
        name: dataRoot
        description: The root of the data in the Remote source which is used as the
          base for all remote columns
      - in: formData
        name: dataSet
        description: The DataSet Name
      - in: formData
        name: description
        description: A description of this DataSet
      - in: formData
        name: isRemote
        description: Is this a remote DataSet?
      - in: formData
        name: method
        description: The Request Method GET or POST
      - in: formData
        name: password
        description: HTTP Authentication Password
      - in: formData
        name: postData
        description: query parameter encoded data to add to the request
      - in: formData
        name: refreshRate
        description: How often in seconds should this remote DataSet be refreshed
      - in: formData
        name: runsAfter
        description: An optional dataSetId which should be run before this Remote
          DataSet
      - in: formData
        name: summarize
        description: Should the data be aggregated? None|Summarize|Count
      - in: formData
        name: summarizeField
        description: Which field should be used to summarize
      - in: formData
        name: uri
        description: The URI, without query parameters
      - in: formData
        name: username
        description: HTTP Authentication User Name
      responses:
        200:
          description: OK
      tags:
      - DataSet
  /dataset/{dataSetId}:
    put:
      summary: Edit DataSet
      description: Edit a DataSet
      operationId: dataSetEdit
      x-api-path-slug: datasetdatasetid-put
      parameters:
      - in: formData
        name: authentication
        description: HTTP Authentication method None|Basic|Digest
      - in: formData
        name: clearRate
        description: How often in seconds should this remote DataSet be truncated
      - in: formData
        name: code
        description: A code for this DataSet
      - in: formData
        name: dataRoot
        description: The root of the data in the Remote source which is used as the
          base for all remote columns
      - in: formData
        name: dataSet
        description: The DataSet Name
      - in: path
        name: dataSetId
        description: The DataSet ID
      - in: formData
        name: description
        description: A description of this DataSet
      - in: formData
        name: isRemote
        description: Is this a remote DataSet?
      - in: formData
        name: method
        description: The Request Method GET or POST
      - in: formData
        name: password
        description: HTTP Authentication Password
      - in: formData
        name: postData
        description: query parameter encoded data to add to the request
      - in: formData
        name: refreshRate
        description: How often in seconds should this remote DataSet be refreshed
      - in: formData
        name: runsAfter
        description: An optional dataSetId which should be run before this Remote
          DataSet
      - in: formData
        name: summarize
        description: Should the data be aggregated? None|Summarize|Count
      - in: formData
        name: summarizeField
        description: Which field should be used to summarize
      - in: formData
        name: uri
        description: The URI, without query parameters
      - in: formData
        name: username
        description: HTTP Authentication User Name
      responses:
        200:
          description: OK
      tags:
      - Edit
      - DataSet
    delete:
      summary: Delete DataSet
      description: Delete a DataSet
      operationId: dataSetDelete
      x-api-path-slug: datasetdatasetid-delete
      parameters:
      - in: path
        name: dataSetId
        description: The DataSet ID
      responses:
        200:
          description: OK
      tags:
      - DataSet
  /dataset/copy/{dataSetId}:
    post:
      summary: Copy DataSet
      description: Copy a DataSet
      operationId: dataSetCopy
      x-api-path-slug: datasetcopydatasetid-post
      parameters:
      - in: formData
        name: code
        description: A code for this DataSet
      - in: formData
        name: dataSet
        description: The DataSet Name
      - in: path
        name: dataSetId
        description: The DataSet ID
      - in: formData
        name: description
        description: A description of this DataSet
      responses:
        200:
          description: OK
      tags:
      - Copy
      - DataSet
  /dataset/data/{dataSetId}:
    get:
      summary: DataSet Data
      description: Get Data for DataSet
      operationId: dataSetData
      x-api-path-slug: datasetdatadatasetid-get
      parameters:
      - in: path
        name: dataSetId
        description: The DataSet ID
      responses:
        200:
          description: OK
      tags:
      - DataSet
      - Data