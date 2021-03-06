# Learn-ReadMe
Try different types of ReadMe's

**Reference to the Component ("compRef" in below example)**

API's exposed on the component ref are accessible via `compRef.current.<API_NAME>` (like compRef.current.refreshView)
| API_NAME | Default values | Notes | Example |
| -------- | -------------- | ----- | ------- |
| refreshView | | refreshView api is used to re-render the already loaded table to re-fetch the data and you can provide two arguments to refreshView; 1. stateToReset (`<object>`) - (ex: you want to remove grouping before triggering re-render). Currently, supported state flushing of only `['filterExpression', 'search', 'selectedRows']`, 2. featuresToAvoid (`Array<string>`) - to avoid re-running of the following fetures - ['rowAnimation', 'columnAnimation'] | `compRef.current.refreshView({ filterExpression: true, search: true }, ['rowAnimation']);`|
| moveListRecords | | `apiContext.moveListRecords` api is used to consume a dxapi which invokes a OOTB data transform. api flow: 1. invokes dxapi with neccessarry payload, 2. dxapi is configured with activity which invokes a data transform based on the payload & path param received 3. returns success response object with `{refresh: true}` 4. based on this falg it triggers refresh strategy which fetch new set of data | `compRef.current.apiContext.moveListRecords({sourceID, destinationID})`|
|dispatchAction| | `dispatchAction(action,payload)` is used to trigger specific actions to the table with a specific payload. Below actions are available: <br>'toggleDisableSelection' - it supports enable/disable of selection of rows. Payload should be a boolean in order to enable disable the selection.<br>'updateDebugInfo' - Show the stats of API call for debugging purposes. The payload must be an object.<br>'toggleRequired' - It supports show/hide of astereix(\*) sign in case of embedded/data reference tables, To show/hide of warning sign in case required condition is not met. The payload must be an object.<br>| Disable the selection - `compRef.current.dispatchAction('toggleDisableSelection',true)` <br> Pass API stats - `compRef.current.dispatchAction('updateDebugInfo', {className: "ABC", dataPage: "D_Page", dataSource: "RDBMS", timeTaken: "1.2 s", insightId: "someId"})`<br>Show/Hide Required UX(astereix(\*) & warning sign) - `cosmosTableRef.current?.dispatchAction('toggleRequired',{required, validatemessage`<br> |



## colors in markdown
###  ![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `#f03c15`
