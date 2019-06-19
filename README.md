# farmsmart-model

## JSON Schema to use is Draft 7

https://json-schema.org/draft-07/json-schema-release-notes.html

## JSON Schemas for the CMS entities stored in FireStore

Note that schemas should match the schema name from Flamelink, typically this is camelCase e.g. `cropStage`

[Crop](./schemas/crop.schema.json) - Contains crops

[Crop Stage Schema](./schemas/cropStage.schema.json) - Stages in a crop. Referenced by Crop

[Article](./schemas/article.schema.json) - Articles referenced by Crop Stage or other Articles

## References to other CMS entities

Use the path segments to build the path to the document in FireStore

## References to Images

Use the path segments to build the path to the image.

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

```
{
    "sizes": [
        {
            "width": 1080,
            "path": "1080_9999_100",
            "quality": 1,
            "height": 9999
        }
    ],
    "type": "images",
    "id": "fFchw9hkJ8m5u5j2xAuX",
    "file": "fFchw9hkJ8m5u5j2xAuX_Tomato.JPG",
    "contentType": "image/jpeg"
}
```

From the document build the path to the Firebase Cloud Store

```
/flamelink/media/sized/1080_9999_100/fFchw9hkJ8m5u5j2xAuX_Tomato.JPG
```
