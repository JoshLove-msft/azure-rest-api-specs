# Cognitive Services Translator Text SDK

> see https://aka.ms/autorest

Configuration for generating Translator Text SDK.

The current release is `release_3_0`.

The current document batch release is `release_1_1'`.

``` yaml

tag: release_3_0
add-credentials: true
openapi-type: data-plane
```

``` yaml

tag: release_1_1
add-credentials: true
openapi-type: data-plane
```
# Releases

### Preview 1.0
This setting is for batch document translator and only applied when `--tag=release_1_0_preview.1` is specified on the command line.
``` yaml $(tag) == 'release_1_0_preview.1'
input-file: preview/v1.0-preview.1/TranslatorBatch.json
```

### 1.0 Batch API
This setting is for batch document translator and only applied when `--tag=release_1_0` is specified on the command line.
``` yaml $(tag) == 'release_1_0'
input-file: stable/v1.0/TranslatorBatch.json
```

### 1.1 Batch API
This setting is for batch document translator and only applied when `--tag=release_1_1` is specified on the command line.
``` yaml $(tag) == 'release_1_1'
input-file: stable/v1.1/TranslatorBatch.json
```

### Release 3.0
These settings apply only when `--tag=release_3_0` is specified on the command line.

``` yaml $(tag) == 'release_3_0'
input-file: stable/v3.0/TranslatorText.json
```

## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-net
```

## CSharp Settings
These settings apply only when `--csharp` is specified on the command line.
``` yaml $(csharp)
csharp:
  sync-methods: None
  license-header: MICROSOFT_MIT_NO_VERSION
  azure-arm: false
  namespace: Microsoft.Azure.CognitiveServices.TranslatorText
  output-folder: $(csharp-sdks-folder)/CognitiveServices/dataPlane/TranslatorText/TranslatorText/Generated
  clear-output-folder: true
```

## Python

See configuration in [readme.python.md](./readme.python.md)

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

These settings apply only when `--java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-libraries-for-java clone>`.

``` yaml $(java)
java:
  azure-arm: true
  namespace: com.microsoft.azure.cognitiveservices.translatortext
  license-header: MICROSOFT_MIT_NO_CODEGEN
  payload-flattening-threshold: 1
  output-folder: $(azure-libraries-for-java-folder)/cognitiveservices/data-plane/translatortext
  with-optional-parameters: true
  with-single-async-method: true
```

## Node.js

``` yaml $(nodejs)
nodejs:
  package-name: azure-cognitiveservices-translatortext
  output-folder: $(node-sdks-folder)/lib/services/translatorText
  azure-arm: false
  generate-license-txt: true
  generate-package-json: true
  generate-readme-md: false
```

### Tag: release_1_0_preview.1 and nodejs

These settings apply only when `--tag=release_1_0_preview.1 --nodejs` is specified on the command line.

``` yaml $(tag) == 'release_1_0_preview.1' && $(nodejs)
  package-version: 1.0.1
```

### Tag: release_1_0 and nodejs

These settings apply only when `--tag=release_1_0 --nodejs` is specified on the command line.

``` yaml $(tag) == 'release_1_0' && $(nodejs)
  package-version: 1.0
```

### Tag: release_3_0 and go

These settings apply only when `--tag=release_3_0 --nodejs` is specified on the command line.

``` yaml $(tag) == 'release_3_0' && $(nodejs)
  package-version: 3.0.0
```

## Multi-API/Profile support for AutoRest v3 generators 

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/preview/v1.0-preview.1/TranslatorBatch.json
  - $(this-folder)/stable/v3.0/TranslatorText.json

```

If there are files that should not be in the `all-api-versions` set, 
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```

