# farmsmart-model

## JSON Schema to use is Draft 7

https://json-schema.org/draft-07/json-schema-release-notes.html

## CMS Models stored in FireStore

[Crop](./schemas/crop.schema.json) - Contains crops

[Crop Stage](./schemas/crop_stage.schema.json) - Stages in a crop. Referenced by Crop

[Article](./schemas/article.schema.json) - Articles referenced by Crop Stage or other Articles

## References to other CMS entities

Use the path segments to build the path to the document in FireStore

## References to Images

Use the path segments to build the path to the image. Additionally, supply the image sizes in the request for the image.

Sample Path segments:
```
"image": [
        {
            "_path": {
                "segments": [
                    "fl_files",
                    "fFchw9hkJ8m5u5j2xAuX"
                ]
            }
        }
    ],
```
In firestore lookup **fl_files** for the **fFchw9hkJ8m5u5j2xAuX** to get the available size and the name of the image. [Sample JSON of fl_files](./json/fl_files_sample.json)

``
/flamelink/media/sized/1080_9999_100/name.JPG
``