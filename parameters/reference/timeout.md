---
title: Dynamsoft Document Normalizer Parameter Reference - Timeout
keywords: timeout, parameters, reference, ddn, documentation
description: Dynamsoft Document Normalizer Parameter Reference - Timeout
needGenerateH3Content: true
---

# Timeout
Sets the maximum amount of time (in milliseconds) should be spent on normalizing the content per page. 

**Remarks**   
It does not include the time taken to load/decode an image (Tiff, PNG, etc.) from disk into memory.   

## Setting Methods
### As Json Parameter

| Parent Json Object | Json Parameter Name | Value Type | 
| ------------------ | ------------------- | ---------- |
| DocumentNormalizerParameter | Timeout | *int* |

**Value Range**  
    [0, 0x7fffffff]

**Default Value**  
    10000

**Example**  
```json
{
    "Timeout": 20000,
}
```

### As Struct Member

| Struct | Struct Member Name | Value Type | 
| ------ | ------------------ | ---------- |
| DDN_RuntimeSettings | timeout | *int* |

**Value Range**  
    [0, 0x7fffffff]

**Default Value**  
    10000

**Code Snippet**  
```cpp
// This is a c++ sample code.
DocumentNormalizer::InitLicense("t0260NwAAAHV***************");
DocumentNormalizer* normalizer = new DocumentNormalizer();
DDN_RuntimeSettings settings;
int errorCode = normalizer->GetRuntimeSettings(&settings);
settings->timeout = 20000;
char errorMessage[256];
errorCode = normalizer->UpdateRuntimeSettings(&settings, errorMessage, 256);
delete normalizer;
```