+++
title = "Using Kendra with a non-english index"
date = "`r Sys.Date()`"
weight = 5
chapter = false
pre = "<b>5. </b>"
+++
### Using Kendra with a non-english index


If you're using Kendra with an index in a language other than English, you will need to make some code modifications.

You'll need to modify the filters in the file `lib/shared/layers/python-sdk/python/genai_core/kendra/query.py.`


Example for vietnamese:
```
if kendra_index_external or kendra_use_all_data:
    result = kendra.retrieve(
        IndexId=kendra_index_id,
        QueryText=query,
        PageSize=limit,
        PageNumber=1,
        AttributeFilter={'AndAllFilters': [{"EqualsTo": {"Key": "_language_code","Value": {"StringValue": "vi"}}}]}
    )
else:
    result = kendra.retrieve(
        IndexId=kendra_index_id,
        QueryText=query,
        PageSize=limit,
        PageNumber=1,
        AttributeFilter={'AndAllFilters':
            [
                {"EqualsTo": {"Key": "_language_code","Value": {"StringValue": "vi"}}},
                {"EqualsTo": {"Key": "workspace_id","Value": {"StringValue": workspace_id}}}
            ]
        }
    )


```


**Important**: After you have done these changes it's essential to redeploy the solution:
```
npx cdk deploy
```