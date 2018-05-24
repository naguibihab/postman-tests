# postman-tests
Some test methods using postman

## Comparing a json value against a static string

```
var jsonData = JSON.parse(responseBody);
tests["Do we have a PDF?"] = jsonData.status.value === 'pdf';
```

## Comparing a json value against regex

```
var jsonData = JSON.parse(responseBody);
tests["Do we have chart ids?"] = true === /\d*/.test(jsonData[0].chart_id);
```

```
var jsonData = JSON.parse(responseBody);
tests["Do we have chart titles?"] = true === /\w*d*/.test(jsonData[0].chart_title);
```
## Searching for a string in the body

```
tests["Is the report uploaded to s3?"] = responseBody.has("https://s3-ap-southeast-2.amazonaws.com/reports.mywebsite.com");
```

## Generating a random UUID

```
pm.setGlobalVariable("v4uuid", 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function(c) { var r = Math.random()*16|0, v = c == 'x' ? r : (r&0x3|0x8); return v.toString(16); }));
```
