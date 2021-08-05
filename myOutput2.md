---
title: Swagger OMP application v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="swagger-omp-application">Swagger OMP application v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Automatically generated applications service

Base URLs:

* <a href="//emm.omprussia.ru/v1">//emm.omprussia.ru/v1</a>

<a href="http://swagger.io/terms/">Terms of service</a>

 License: undefined

<h1 id="swagger-omp-application-default">Default</h1>

## get__admin_version

`GET /admin/version`

shows the binary's version

> Example responses

> 200 Response

```json
{
  "version": "string"
}
```

<h3 id="get__admin_version-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[container.version](#schemacontainer.version)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="swagger-omp-application-applications">Applications</h1>

working with application entity

## post__applications

`POST /applications`

*add application*

create new application

> Body parameter

```json
{
  "code": "string",
  "osCode": "string",
  "ownerId": "string"
}
```

<h3 id="post__applications-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[schemas+test#application.createrequest])|true|New model fields|

> Example responses

> 201 Response

```json
{
  "id": "string"
}
```

<h3 id="post__applications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[application.CreateResponse](#schemaapplication.createresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[liberrors.Error](#schemaliberrors.error)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[liberrors.Error](#schemaliberrors.error)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_application.BuildResponseDTO">application.BuildResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.buildresponsedto"></a>
<a id="schema_application.BuildResponseDTO"></a>
<a id="tocSapplication.buildresponsedto"></a>
<a id="tocsapplication.buildresponsedto"></a>

```json
{
  "appCode": "string",
  "hasDeveloperSignature": true,
  "id": "string",
  "url": "string",
  "version": [
    null
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|appCode|string|false|none|none|
|hasDeveloperSignature|boolean|false|none|none|
|id|string|false|none|none|
|url|string|false|none|none|
|version|[version.Version](#schemaversion.version)|false|none|none|

<h2 id="tocS_application.CreateRequest">application.CreateRequest</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.createrequest"></a>
<a id="schema_application.CreateRequest"></a>
<a id="tocSapplication.createrequest"></a>
<a id="tocsapplication.createrequest"></a>

```json
{
  "code": "string",
  "osCode": "string",
  "ownerId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|osCode|string|false|none|none|
|ownerId|string|false|none|none|

<h2 id="tocS_application.CreateResponse">application.CreateResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.createresponse"></a>
<a id="schema_application.CreateResponse"></a>
<a id="tocSapplication.createresponse"></a>
<a id="tocsapplication.createresponse"></a>

```json
{
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|

<h2 id="tocS_application.Dependency">application.Dependency</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.dependency"></a>
<a id="schema_application.Dependency"></a>
<a id="tocSapplication.dependency"></a>
<a id="tocsapplication.dependency"></a>

```json
{
  "applicationId": "string",
  "createdAt": "string",
  "customerKeyPairId": "string",
  "id": "string",
  "name": "string",
  "originalDependencyId": "string",
  "updatedAt": "string",
  "url": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|applicationId|string|false|none|none|
|createdAt|string|false|none|none|
|customerKeyPairId|string|false|none|none|
|id|string|false|none|none|
|name|string|false|none|// Name is a RPM package name extracted from it's headers.|
|originalDependencyId|string|false|none|none|
|updatedAt|string|false|none|none|
|url|string|false|none|// URL is a generated path to dependency content.|
|version|string|false|none|// Version is a RPM package version extracted from it's headers.|

<h2 id="tocS_application.ListResponse">application.ListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.listresponse"></a>
<a id="schema_application.ListResponse"></a>
<a id="tocSapplication.listresponse"></a>
<a id="tocsapplication.listresponse"></a>

```json
{
  "data": [
    {
      "changes": {
        "application": {
          "primaryCategoryCode": "string",
          "secondaryCategoryCode": "string"
        },
        "status": "DRAFT"
      },
      "code": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "id": "string",
      "osCode": "string",
      "ownerId": "string",
      "primaryCategoryCode": "string",
      "releases": [
        {
          "build": {
            "appCode": "string",
            "hasDeveloperSignature": true,
            "id": "string",
            "url": "string",
            "version": [
              null
            ]
          },
          "icon": {
            "id": "string",
            "url": "string"
          },
          "id": "string",
          "name": "string",
          "status": "DRAFT",
          "version": "string"
        }
      ],
      "secondaryCategoryCode": "string",
      "updatedAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[application.ResponseApplicationDTO](#schemaapplication.responseapplicationdto)]|false|none|none|

<h2 id="tocS_application.ReadResponse">application.ReadResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.readresponse"></a>
<a id="schema_application.ReadResponse"></a>
<a id="tocSapplication.readresponse"></a>
<a id="tocsapplication.readresponse"></a>

```json
{
  "changes": {
    "application": {
      "primaryCategoryCode": "string",
      "secondaryCategoryCode": "string"
    },
    "status": "DRAFT"
  },
  "code": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "id": "string",
  "osCode": "string",
  "ownerId": "string",
  "primaryCategoryCode": "string",
  "secondaryCategoryCode": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|changes|[application.ResponseApplicationChangesDTO](#schemaapplication.responseapplicationchangesdto)|false|none|none|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|id|string|false|none|none|
|osCode|string|false|none|none|
|ownerId|string|false|none|none|
|primaryCategoryCode|string|false|none|none|
|secondaryCategoryCode|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_application.ReleaseShortInfoDTO">application.ReleaseShortInfoDTO</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.releaseshortinfodto"></a>
<a id="schema_application.ReleaseShortInfoDTO"></a>
<a id="tocSapplication.releaseshortinfodto"></a>
<a id="tocsapplication.releaseshortinfodto"></a>

```json
{
  "build": {
    "appCode": "string",
    "hasDeveloperSignature": true,
    "id": "string",
    "url": "string",
    "version": [
      null
    ]
  },
  "icon": {
    "id": "string",
    "url": "string"
  },
  "id": "string",
  "name": "string",
  "status": "DRAFT",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|build|[application.BuildResponseDTO](#schemaapplication.buildresponsedto)|false|none|none|
|icon|[application.ResourceResponseDTO](#schemaapplication.resourceresponsedto)|false|none|none|
|id|string|false|none|none|
|name|string|false|none|none|
|status|string|false|none|none|
|version|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|DRAFT|
|status|REWORK|
|status|REVIEW_PENDING|
|status|APPROVED|
|status|DECLINED|

<h2 id="tocS_application.ResourceResponseDTO">application.ResourceResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.resourceresponsedto"></a>
<a id="schema_application.ResourceResponseDTO"></a>
<a id="tocSapplication.resourceresponsedto"></a>
<a id="tocsapplication.resourceresponsedto"></a>

```json
{
  "id": "string",
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|url|string|false|none|none|

<h2 id="tocS_application.ResponseApplicationChangesDTO">application.ResponseApplicationChangesDTO</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.responseapplicationchangesdto"></a>
<a id="schema_application.ResponseApplicationChangesDTO"></a>
<a id="tocSapplication.responseapplicationchangesdto"></a>
<a id="tocsapplication.responseapplicationchangesdto"></a>

```json
{
  "application": {
    "primaryCategoryCode": "string",
    "secondaryCategoryCode": "string"
  },
  "status": "DRAFT"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|application|[application.ResponseApplicationChangesFieldsDTO](#schemaapplication.responseapplicationchangesfieldsdto)|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|DRAFT|
|status|REWORK|
|status|REVIEW_PENDING|
|status|APPROVED|

<h2 id="tocS_application.ResponseApplicationChangesFieldsDTO">application.ResponseApplicationChangesFieldsDTO</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.responseapplicationchangesfieldsdto"></a>
<a id="schema_application.ResponseApplicationChangesFieldsDTO"></a>
<a id="tocSapplication.responseapplicationchangesfieldsdto"></a>
<a id="tocsapplication.responseapplicationchangesfieldsdto"></a>

```json
{
  "primaryCategoryCode": "string",
  "secondaryCategoryCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|primaryCategoryCode|string|false|none|none|
|secondaryCategoryCode|string|false|none|none|

<h2 id="tocS_application.ResponseApplicationDTO">application.ResponseApplicationDTO</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.responseapplicationdto"></a>
<a id="schema_application.ResponseApplicationDTO"></a>
<a id="tocSapplication.responseapplicationdto"></a>
<a id="tocsapplication.responseapplicationdto"></a>

```json
{
  "changes": {
    "application": {
      "primaryCategoryCode": "string",
      "secondaryCategoryCode": "string"
    },
    "status": "DRAFT"
  },
  "code": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "id": "string",
  "osCode": "string",
  "ownerId": "string",
  "primaryCategoryCode": "string",
  "releases": [
    {
      "build": {
        "appCode": "string",
        "hasDeveloperSignature": true,
        "id": "string",
        "url": "string",
        "version": [
          null
        ]
      },
      "icon": {
        "id": "string",
        "url": "string"
      },
      "id": "string",
      "name": "string",
      "status": "DRAFT",
      "version": "string"
    }
  ],
  "secondaryCategoryCode": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|changes|[application.ResponseApplicationChangesDTO](#schemaapplication.responseapplicationchangesdto)|false|none|none|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|id|string|false|none|none|
|osCode|string|false|none|none|
|ownerId|string|false|none|none|
|primaryCategoryCode|string|false|none|none|
|releases|[[application.ReleaseShortInfoDTO](#schemaapplication.releaseshortinfodto)]|false|none|none|
|secondaryCategoryCode|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_application.UpdateRequestBody">application.UpdateRequestBody</h2>
<!-- backwards compatibility -->
<a id="schemaapplication.updaterequestbody"></a>
<a id="schema_application.UpdateRequestBody"></a>
<a id="tocSapplication.updaterequestbody"></a>
<a id="tocsapplication.updaterequestbody"></a>

```json
{
  "code": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|

<h2 id="tocS_build.CompatibilityResponseDTO">build.CompatibilityResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemabuild.compatibilityresponsedto"></a>
<a id="schema_build.CompatibilityResponseDTO"></a>
<a id="tocSbuild.compatibilityresponsedto"></a>
<a id="tocsbuild.compatibilityresponsedto"></a>

```json
{
  "osReleaseCodeFrom": "string",
  "osReleaseCodeTo": "string",
  "osReleaseLatestCompatible": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|osReleaseCodeFrom|string|false|none|none|
|osReleaseCodeTo|string|false|none|none|
|osReleaseLatestCompatible|boolean|false|none|none|

<h2 id="tocS_build.OSCompatibilityDTO">build.OSCompatibilityDTO</h2>
<!-- backwards compatibility -->
<a id="schemabuild.oscompatibilitydto"></a>
<a id="schema_build.OSCompatibilityDTO"></a>
<a id="tocSbuild.oscompatibilitydto"></a>
<a id="tocsbuild.oscompatibilitydto"></a>

```json
{
  "osReleaseCodeFrom": "string",
  "osReleaseCodeTo": "string",
  "osReleaseLatestCompatible": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|osReleaseCodeFrom|string|false|none|none|
|osReleaseCodeTo|string|false|none|none|
|osReleaseLatestCompatible|boolean|false|none|none|

<h2 id="tocS_build.ResourceResponseDTO">build.ResourceResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemabuild.resourceresponsedto"></a>
<a id="schema_build.ResourceResponseDTO"></a>
<a id="tocSbuild.resourceresponsedto"></a>
<a id="tocsbuild.resourceresponsedto"></a>

```json
{
  "id": "string",
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|url|string|false|none|none|

<h2 id="tocS_build.ResponseBuildInfoDTO">build.ResponseBuildInfoDTO</h2>
<!-- backwards compatibility -->
<a id="schemabuild.responsebuildinfodto"></a>
<a id="schema_build.ResponseBuildInfoDTO"></a>
<a id="tocSbuild.responsebuildinfodto"></a>
<a id="tocsbuild.responsebuildinfodto"></a>

```json
{
  "appCode": "string",
  "applicationId": "string",
  "createdAt": "string",
  "description": "string",
  "hasDeveloperSignature": true,
  "icon": {
    "id": "string",
    "url": "string"
  },
  "id": "string",
  "osCompatibility": {
    "osReleaseCodeFrom": "string",
    "osReleaseCodeTo": "string",
    "osReleaseLatestCompatible": true
  },
  "updatedAt": "string",
  "version": "string",
  "websiteUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|appCode|string|false|none|// AppCode is a RPM package name extracted from it's headers. We expect it matches to Application.Code.|
|applicationId|string|false|none|none|
|createdAt|string|false|none|none|
|description|string|false|none|// Description is a RPM package description extracted from it's headers. We expect it have some relation to Release.Description.|
|hasDeveloperSignature|boolean|false|none|// HasDeveloperSignature is a marker showing that the build has been signed by the developer.|
|icon|[build.ResourceResponseDTO](#schemabuild.resourceresponsedto)|false|none|none|
|id|string|false|none|none|
|osCompatibility|[build.CompatibilityResponseDTO](#schemabuild.compatibilityresponsedto)|false|none|none|
|updatedAt|string|false|none|none|
|version|string|false|none|// Version is a RPM package version extracted from it's headers. We expect it have some relation to Release.Version.|
|websiteUrl|string|false|none|// WebSiteURL is a RPM package URL extracted from it's headers. We expect it have some relation to Release.WebSiteURL.|

<h2 id="tocS_build.UpdateBuildDTO">build.UpdateBuildDTO</h2>
<!-- backwards compatibility -->
<a id="schemabuild.updatebuilddto"></a>
<a id="schema_build.UpdateBuildDTO"></a>
<a id="tocSbuild.updatebuilddto"></a>
<a id="tocsbuild.updatebuilddto"></a>

```json
{
  "osCompatibility": {
    "osReleaseCodeFrom": "string",
    "osReleaseCodeTo": "string",
    "osReleaseLatestCompatible": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|osCompatibility|[build.OSCompatibilityDTO](#schemabuild.oscompatibilitydto)|false|none|none|

<h2 id="tocS_category.ResponseCategoryDTO">category.ResponseCategoryDTO</h2>
<!-- backwards compatibility -->
<a id="schemacategory.responsecategorydto"></a>
<a id="schema_category.ResponseCategoryDTO"></a>
<a id="tocScategory.responsecategorydto"></a>
<a id="tocscategory.responsecategorydto"></a>

```json
{
  "code": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|name|string|false|none|none|

<h2 id="tocS_container.version">container.version</h2>
<!-- backwards compatibility -->
<a id="schemacontainer.version"></a>
<a id="schema_container.version"></a>
<a id="tocScontainer.version"></a>
<a id="tocscontainer.version"></a>

```json
{
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|version|string|false|none|none|

<h2 id="tocS_customerkeypair.CustomerKeyPair">customerkeypair.CustomerKeyPair</h2>
<!-- backwards compatibility -->
<a id="schemacustomerkeypair.customerkeypair"></a>
<a id="schema_customerkeypair.CustomerKeyPair"></a>
<a id="tocScustomerkeypair.customerkeypair"></a>
<a id="tocscustomerkeypair.customerkeypair"></a>

```json
{
  "certificate": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "description": "string",
  "id": "string",
  "name": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|certificate|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|description|string|false|none|none|
|id|string|false|none|none|
|name|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_dashboard.ApplicationDTO">dashboard.ApplicationDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.applicationdto"></a>
<a id="schema_dashboard.ApplicationDTO"></a>
<a id="tocSdashboard.applicationdto"></a>
<a id="tocsdashboard.applicationdto"></a>

```json
{
  "code": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "id": "string",
  "ownerId": "string",
  "primaryCategoryCode": "string",
  "releases": {},
  "secondaryCategoryCode": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|id|string|false|none|none|
|ownerId|string|false|none|none|
|primaryCategoryCode|string|false|none|none|
|releases|object|false|none|// TODO(s.tyapkin): remove this field from dto. It is useless and always nil.|
|secondaryCategoryCode|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_dashboard.BuildResponseDTO">dashboard.BuildResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.buildresponsedto"></a>
<a id="schema_dashboard.BuildResponseDTO"></a>
<a id="tocSdashboard.buildresponsedto"></a>
<a id="tocsdashboard.buildresponsedto"></a>

```json
{
  "appCode": "string",
  "hasDeveloperSignature": true,
  "id": "string",
  "url": "string",
  "version": [
    null
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|appCode|string|false|none|none|
|hasDeveloperSignature|boolean|false|none|none|
|id|string|false|none|none|
|url|string|false|none|none|
|version|[version.Version](#schemaversion.version)|false|none|none|

<h2 id="tocS_dashboard.CategoryResponseDTO">dashboard.CategoryResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.categoryresponsedto"></a>
<a id="schema_dashboard.CategoryResponseDTO"></a>
<a id="tocSdashboard.categoryresponsedto"></a>
<a id="tocsdashboard.categoryresponsedto"></a>

```json
{
  "applications": [
    {
      "code": "string",
      "createdAt": "string",
      "id": "string",
      "releases": [
        {
          "icon": {
            "url": "string"
          },
          "id": "string",
          "name": "string",
          "version": "string"
        }
      ],
      "updatedAt": "string"
    }
  ],
  "code": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|applications|[[dashboard.CategoryResponseDTOApp](#schemadashboard.categoryresponsedtoapp)]|false|none|none|
|code|string|false|none|none|

<h2 id="tocS_dashboard.CategoryResponseDTOApp">dashboard.CategoryResponseDTOApp</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.categoryresponsedtoapp"></a>
<a id="schema_dashboard.CategoryResponseDTOApp"></a>
<a id="tocSdashboard.categoryresponsedtoapp"></a>
<a id="tocsdashboard.categoryresponsedtoapp"></a>

```json
{
  "code": "string",
  "createdAt": "string",
  "id": "string",
  "releases": [
    {
      "icon": {
        "url": "string"
      },
      "id": "string",
      "name": "string",
      "version": "string"
    }
  ],
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|id|string|false|none|none|
|releases|[[dashboard.CategoryResponseDTORelease](#schemadashboard.categoryresponsedtorelease)]|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_dashboard.CategoryResponseDTOIcon">dashboard.CategoryResponseDTOIcon</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.categoryresponsedtoicon"></a>
<a id="schema_dashboard.CategoryResponseDTOIcon"></a>
<a id="tocSdashboard.categoryresponsedtoicon"></a>
<a id="tocsdashboard.categoryresponsedtoicon"></a>

```json
{
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|false|none|none|

<h2 id="tocS_dashboard.CategoryResponseDTORelease">dashboard.CategoryResponseDTORelease</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.categoryresponsedtorelease"></a>
<a id="schema_dashboard.CategoryResponseDTORelease"></a>
<a id="tocSdashboard.categoryresponsedtorelease"></a>
<a id="tocsdashboard.categoryresponsedtorelease"></a>

```json
{
  "icon": {
    "url": "string"
  },
  "id": "string",
  "name": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|icon|[dashboard.CategoryResponseDTOIcon](#schemadashboard.categoryresponsedtoicon)|false|none|none|
|id|string|false|none|none|
|name|string|false|none|none|
|version|string|false|none|none|

<h2 id="tocS_dashboard.CreateRequest">dashboard.CreateRequest</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.createrequest"></a>
<a id="schema_dashboard.CreateRequest"></a>
<a id="tocSdashboard.createrequest"></a>
<a id="tocsdashboard.createrequest"></a>

```json
{
  "allowAnonymousAccess": true,
  "name": "string",
  "osCode": "string",
  "purpose": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|allowAnonymousAccess|boolean|false|none|none|
|name|string|false|none|none|
|osCode|string|false|none|none|
|purpose|string|false|none|none|

<h2 id="tocS_dashboard.DeleteCustomerKeyPairResponse">dashboard.DeleteCustomerKeyPairResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.deletecustomerkeypairresponse"></a>
<a id="schema_dashboard.DeleteCustomerKeyPairResponse"></a>
<a id="tocSdashboard.deletecustomerkeypairresponse"></a>
<a id="tocsdashboard.deletecustomerkeypairresponse"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_dashboard.DeleteCustomerKeyPairsResponse">dashboard.DeleteCustomerKeyPairsResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.deletecustomerkeypairsresponse"></a>
<a id="schema_dashboard.DeleteCustomerKeyPairsResponse"></a>
<a id="tocSdashboard.deletecustomerkeypairsresponse"></a>
<a id="tocsdashboard.deletecustomerkeypairsresponse"></a>

```json
{
  "data": [
    {
      "certificate": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "description": "string",
      "id": "string",
      "name": "string",
      "updatedAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[customerkeypair.CustomerKeyPair](#schemacustomerkeypair.customerkeypair)]|false|none|none|

<h2 id="tocS_dashboard.DependencyResponseDTO">dashboard.DependencyResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.dependencyresponsedto"></a>
<a id="schema_dashboard.DependencyResponseDTO"></a>
<a id="tocSdashboard.dependencyresponsedto"></a>
<a id="tocsdashboard.dependencyresponsedto"></a>

```json
{
  "id": "string",
  "name": "string",
  "url": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|name|string|false|none|none|
|url|string|false|none|none|
|version|string|false|none|none|

<h2 id="tocS_dashboard.FilterCondition">dashboard.FilterCondition</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.filtercondition"></a>
<a id="schema_dashboard.FilterCondition"></a>
<a id="tocSdashboard.filtercondition"></a>
<a id="tocsdashboard.filtercondition"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_dashboard.FilterConditions">dashboard.FilterConditions</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.filterconditions"></a>
<a id="schema_dashboard.FilterConditions"></a>
<a id="tocSdashboard.filterconditions"></a>
<a id="tocsdashboard.filterconditions"></a>

```json
{
  "conditions": [
    {}
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|conditions|[[dashboard.FilterCondition](#schemadashboard.filtercondition)]|false|none|none|

<h2 id="tocS_dashboard.FilterRules">dashboard.FilterRules</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.filterrules"></a>
<a id="schema_dashboard.FilterRules"></a>
<a id="tocSdashboard.filterrules"></a>
<a id="tocsdashboard.filterrules"></a>

```json
{
  "createdAt": "string",
  "dashboardId": {},
  "id": "string",
  "rules": [
    "string"
  ],
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdAt|string|false|none|none|
|dashboardId|[dashboard.ID](#schemadashboard.id)|false|none|none|
|id|string|false|none|none|
|rules|[string]|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_dashboard.ID">dashboard.ID</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.id"></a>
<a id="schema_dashboard.ID"></a>
<a id="tocSdashboard.id"></a>
<a id="tocsdashboard.id"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_dashboard.ListApplicationReleasesResponse">dashboard.ListApplicationReleasesResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.listapplicationreleasesresponse"></a>
<a id="schema_dashboard.ListApplicationReleasesResponse"></a>
<a id="tocSdashboard.listapplicationreleasesresponse"></a>
<a id="tocsdashboard.listapplicationreleasesresponse"></a>

```json
{
  "data": [
    {
      "build": {
        "appCode": "string",
        "hasDeveloperSignature": true,
        "id": "string",
        "url": "string",
        "version": [
          null
        ]
      },
      "changelog": "string",
      "comment": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "dependencies": [
        {
          "id": "string",
          "name": "string",
          "url": "string",
          "version": "string"
        }
      ],
      "description": "string",
      "icon": {
        "id": "string",
        "url": "string"
      },
      "id": "string",
      "keywords": "string",
      "name": "string",
      "policyUrl": "string",
      "screenshots": [
        {
          "id": "string",
          "url": "string"
        }
      ],
      "status": "DRAFT",
      "supportEmail": "string",
      "updatedAt": "string",
      "version": "string",
      "websiteUrl": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[dashboard.ReleaseListResponseReleaseDTO](#schemadashboard.releaselistresponsereleasedto)]|false|none|none|

<h2 id="tocS_dashboard.ListApplicationsResponse">dashboard.ListApplicationsResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.listapplicationsresponse"></a>
<a id="schema_dashboard.ListApplicationsResponse"></a>
<a id="tocSdashboard.listapplicationsresponse"></a>
<a id="tocsdashboard.listapplicationsresponse"></a>

```json
{
  "data": [
    {
      "code": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "id": "string",
      "osCode": "string",
      "ownerId": "string",
      "primaryCategoryCode": "string",
      "releases": [
        {
          "build": {
            "appCode": "string",
            "hasDeveloperSignature": true,
            "id": "string",
            "url": "string",
            "version": [
              null
            ]
          },
          "categoryCodes": [
            "string"
          ],
          "icon": {
            "id": "string",
            "url": "string"
          },
          "id": "string",
          "name": "string",
          "version": "string"
        }
      ],
      "secondaryCategoryCode": "string",
      "updatedAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[dashboard.ResponseApplicationDTO](#schemadashboard.responseapplicationdto)]|false|none|none|

<h2 id="tocS_dashboard.ListCategoriesResponse">dashboard.ListCategoriesResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.listcategoriesresponse"></a>
<a id="schema_dashboard.ListCategoriesResponse"></a>
<a id="tocSdashboard.listcategoriesresponse"></a>
<a id="tocsdashboard.listcategoriesresponse"></a>

```json
{
  "data": [
    {
      "applications": [
        {
          "code": "string",
          "createdAt": "string",
          "id": "string",
          "releases": [
            {
              "icon": {
                "url": "string"
              },
              "id": "string",
              "name": "string",
              "version": "string"
            }
          ],
          "updatedAt": "string"
        }
      ],
      "code": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[dashboard.CategoryResponseDTO](#schemadashboard.categoryresponsedto)]|false|none|none|

<h2 id="tocS_dashboard.ListCustomerKeyPairsResponse">dashboard.ListCustomerKeyPairsResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.listcustomerkeypairsresponse"></a>
<a id="schema_dashboard.ListCustomerKeyPairsResponse"></a>
<a id="tocSdashboard.listcustomerkeypairsresponse"></a>
<a id="tocsdashboard.listcustomerkeypairsresponse"></a>

```json
{
  "data": [
    {
      "certificate": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "description": "string",
      "id": "string",
      "name": "string",
      "updatedAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[customerkeypair.CustomerKeyPair](#schemacustomerkeypair.customerkeypair)]|false|none|none|

<h2 id="tocS_dashboard.ListResponse">dashboard.ListResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.listresponse"></a>
<a id="schema_dashboard.ListResponse"></a>
<a id="tocSdashboard.listresponse"></a>
<a id="tocsdashboard.listresponse"></a>

```json
{
  "data": [
    {
      "allowAnonymousAccess": true,
      "createdAt": "string",
      "id": "string",
      "isPublic": true,
      "name": "string",
      "os": {
        "code": "string"
      },
      "purpose": "string",
      "updatedAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[dashboard.ResponseDTO](#schemadashboard.responsedto)]|false|none|none|

<h2 id="tocS_dashboard.ListUnsignedApplicationsResponse">dashboard.ListUnsignedApplicationsResponse</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.listunsignedapplicationsresponse"></a>
<a id="schema_dashboard.ListUnsignedApplicationsResponse"></a>
<a id="tocSdashboard.listunsignedapplicationsresponse"></a>
<a id="tocsdashboard.listunsignedapplicationsresponse"></a>

```json
{
  "data": [
    {
      "code": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "id": "string",
      "osCode": "string",
      "ownerId": "string",
      "primaryCategoryCode": "string",
      "releases": [
        {
          "build": {
            "appCode": "string",
            "hasDeveloperSignature": true,
            "id": "string",
            "url": "string",
            "version": [
              null
            ]
          },
          "categoryCodes": [
            "string"
          ],
          "icon": {
            "id": "string",
            "url": "string"
          },
          "id": "string",
          "name": "string",
          "version": "string"
        }
      ],
      "secondaryCategoryCode": "string",
      "updatedAt": "string"
    }
  ],
  "totalApplications": 0,
  "totalReleases": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[dashboard.ResponseApplicationDTO](#schemadashboard.responseapplicationdto)]|false|none|none|
|totalApplications|integer|false|none|none|
|totalReleases|integer|false|none|none|

<h2 id="tocS_dashboard.OSResponseDTO">dashboard.OSResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.osresponsedto"></a>
<a id="schema_dashboard.OSResponseDTO"></a>
<a id="tocSdashboard.osresponsedto"></a>
<a id="tocsdashboard.osresponsedto"></a>

```json
{
  "code": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|

<h2 id="tocS_dashboard.ReleaseListResponseReleaseDTO">dashboard.ReleaseListResponseReleaseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.releaselistresponsereleasedto"></a>
<a id="schema_dashboard.ReleaseListResponseReleaseDTO"></a>
<a id="tocSdashboard.releaselistresponsereleasedto"></a>
<a id="tocsdashboard.releaselistresponsereleasedto"></a>

```json
{
  "build": {
    "appCode": "string",
    "hasDeveloperSignature": true,
    "id": "string",
    "url": "string",
    "version": [
      null
    ]
  },
  "changelog": "string",
  "comment": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "dependencies": [
    {
      "id": "string",
      "name": "string",
      "url": "string",
      "version": "string"
    }
  ],
  "description": "string",
  "icon": {
    "id": "string",
    "url": "string"
  },
  "id": "string",
  "keywords": "string",
  "name": "string",
  "policyUrl": "string",
  "screenshots": [
    {
      "id": "string",
      "url": "string"
    }
  ],
  "status": "DRAFT",
  "supportEmail": "string",
  "updatedAt": "string",
  "version": "string",
  "websiteUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|build|[dashboard.BuildResponseDTO](#schemadashboard.buildresponsedto)|false|none|none|
|changelog|string|false|none|none|
|comment|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|dependencies|[[dashboard.DependencyResponseDTO](#schemadashboard.dependencyresponsedto)]|false|none|none|
|description|string|false|none|none|
|icon|[dashboard.ResourceResponseDTO](#schemadashboard.resourceresponsedto)|false|none|none|
|id|string|false|none|none|
|keywords|string|false|none|none|
|name|string|false|none|none|
|policyUrl|string|false|none|none|
|screenshots|[[dashboard.ResourceResponseDTO](#schemadashboard.resourceresponsedto)]|false|none|none|
|status|string|false|none|none|
|supportEmail|string|false|none|none|
|updatedAt|string|false|none|none|
|version|string|false|none|none|
|websiteUrl|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|DRAFT|
|status|REVIEW_PENDING|
|status|APPROVED|
|status|REWORK|
|status|DECLINED|

<h2 id="tocS_dashboard.ReleaseResponseDTO">dashboard.ReleaseResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.releaseresponsedto"></a>
<a id="schema_dashboard.ReleaseResponseDTO"></a>
<a id="tocSdashboard.releaseresponsedto"></a>
<a id="tocsdashboard.releaseresponsedto"></a>

```json
{
  "application": {
    "code": "string",
    "createdAt": "string",
    "deletedAt": "string",
    "id": "string",
    "ownerId": "string",
    "primaryCategoryCode": "string",
    "releases": {},
    "secondaryCategoryCode": "string",
    "updatedAt": "string"
  },
  "build": {
    "appCode": "string",
    "hasDeveloperSignature": true,
    "id": "string",
    "url": "string",
    "version": [
      null
    ]
  },
  "categoryCodes": [
    "string"
  ],
  "changelog": "string",
  "comment": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "dependencies": [
    {
      "id": "string",
      "name": "string",
      "url": "string",
      "version": "string"
    }
  ],
  "description": "string",
  "icon": {
    "id": "string",
    "url": "string"
  },
  "id": "string",
  "keywords": "string",
  "name": "string",
  "policyUrl": "string",
  "screenshots": [
    {
      "id": "string",
      "url": "string"
    }
  ],
  "status": "DRAFT",
  "supportEmail": "string",
  "updatedAt": "string",
  "version": "string",
  "websiteUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|application|[dashboard.ApplicationDTO](#schemadashboard.applicationdto)|false|none|none|
|build|[dashboard.BuildResponseDTO](#schemadashboard.buildresponsedto)|false|none|none|
|categoryCodes|[string]|false|none|// Deprecated: use PrimaryCategoryCode and SecondaryCategoryCode in application.|
|changelog|string|false|none|none|
|comment|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|dependencies|[[dashboard.DependencyResponseDTO](#schemadashboard.dependencyresponsedto)]|false|none|none|
|description|string|false|none|none|
|icon|[dashboard.ResourceResponseDTO](#schemadashboard.resourceresponsedto)|false|none|none|
|id|string|false|none|none|
|keywords|string|false|none|none|
|name|string|false|none|none|
|policyUrl|string|false|none|none|
|screenshots|[[dashboard.ResourceResponseDTO](#schemadashboard.resourceresponsedto)]|false|none|none|
|status|string|false|none|none|
|supportEmail|string|false|none|none|
|updatedAt|string|false|none|none|
|version|string|false|none|none|
|websiteUrl|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|DRAFT|
|status|REVIEW_PENDING|
|status|APPROVED|
|status|REWORK|
|status|DECLINED|

<h2 id="tocS_dashboard.ResourceResponseDTO">dashboard.ResourceResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.resourceresponsedto"></a>
<a id="schema_dashboard.ResourceResponseDTO"></a>
<a id="tocSdashboard.resourceresponsedto"></a>
<a id="tocsdashboard.resourceresponsedto"></a>

```json
{
  "id": "string",
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|url|string|false|none|none|

<h2 id="tocS_dashboard.ResponseApplicationDTO">dashboard.ResponseApplicationDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.responseapplicationdto"></a>
<a id="schema_dashboard.ResponseApplicationDTO"></a>
<a id="tocSdashboard.responseapplicationdto"></a>
<a id="tocsdashboard.responseapplicationdto"></a>

```json
{
  "code": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "id": "string",
  "osCode": "string",
  "ownerId": "string",
  "primaryCategoryCode": "string",
  "releases": [
    {
      "build": {
        "appCode": "string",
        "hasDeveloperSignature": true,
        "id": "string",
        "url": "string",
        "version": [
          null
        ]
      },
      "categoryCodes": [
        "string"
      ],
      "icon": {
        "id": "string",
        "url": "string"
      },
      "id": "string",
      "name": "string",
      "version": "string"
    }
  ],
  "secondaryCategoryCode": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|id|string|false|none|none|
|osCode|string|false|none|none|
|ownerId|string|false|none|none|
|primaryCategoryCode|string|false|none|none|
|releases|[[dashboard.ResponseReleaseShortDTO](#schemadashboard.responsereleaseshortdto)]|false|none|none|
|secondaryCategoryCode|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_dashboard.ResponseDTO">dashboard.ResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.responsedto"></a>
<a id="schema_dashboard.ResponseDTO"></a>
<a id="tocSdashboard.responsedto"></a>
<a id="tocsdashboard.responsedto"></a>

```json
{
  "allowAnonymousAccess": true,
  "createdAt": "string",
  "id": "string",
  "isPublic": true,
  "name": "string",
  "os": {
    "code": "string"
  },
  "purpose": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|allowAnonymousAccess|boolean|false|none|none|
|createdAt|string|false|none|none|
|id|string|false|none|none|
|isPublic|boolean|false|none|// Deprecated: Use AllowAnonymousAccess instead.|
|name|string|false|none|none|
|os|[dashboard.OSResponseDTO](#schemadashboard.osresponsedto)|false|none|none|
|purpose|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_dashboard.ResponseReleaseShortDTO">dashboard.ResponseReleaseShortDTO</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.responsereleaseshortdto"></a>
<a id="schema_dashboard.ResponseReleaseShortDTO"></a>
<a id="tocSdashboard.responsereleaseshortdto"></a>
<a id="tocsdashboard.responsereleaseshortdto"></a>

```json
{
  "build": {
    "appCode": "string",
    "hasDeveloperSignature": true,
    "id": "string",
    "url": "string",
    "version": [
      null
    ]
  },
  "categoryCodes": [
    "string"
  ],
  "icon": {
    "id": "string",
    "url": "string"
  },
  "id": "string",
  "name": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|build|[dashboard.BuildResponseDTO](#schemadashboard.buildresponsedto)|false|none|none|
|categoryCodes|[string]|false|none|// Deprecated: use PrimaryCategoryCode and SecondaryCategoryCode in application.|
|icon|[dashboard.ResourceResponseDTO](#schemadashboard.resourceresponsedto)|false|none|none|
|id|string|false|none|none|
|name|string|false|none|none|
|version|string|false|none|none|

<h2 id="tocS_dashboard.SaveFilterRulesRequest">dashboard.SaveFilterRulesRequest</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.savefilterrulesrequest"></a>
<a id="schema_dashboard.SaveFilterRulesRequest"></a>
<a id="tocSdashboard.savefilterrulesrequest"></a>
<a id="tocsdashboard.savefilterrulesrequest"></a>

```json
{
  "rules": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rules|[string]|false|none|none|

<h2 id="tocS_dashboard.UpdateRequest">dashboard.UpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemadashboard.updaterequest"></a>
<a id="schema_dashboard.UpdateRequest"></a>
<a id="tocSdashboard.updaterequest"></a>
<a id="tocsdashboard.updaterequest"></a>

```json
{
  "allowAnonymousAccess": true,
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|allowAnonymousAccess|boolean|false|none|none|
|name|string|false|none|none|

<h2 id="tocS_icon.ResponseIconDTO">icon.ResponseIconDTO</h2>
<!-- backwards compatibility -->
<a id="schemaicon.responseicondto"></a>
<a id="schema_icon.ResponseIconDTO"></a>
<a id="tocSicon.responseicondto"></a>
<a id="tocsicon.responseicondto"></a>

```json
{
  "applicationId": "string",
  "createdAt": "string",
  "id": "string",
  "updatedAt": "string",
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|applicationId|string|false|none|none|
|createdAt|string|false|none|none|
|id|string|false|none|none|
|updatedAt|string|false|none|none|
|url|string|false|none|none|

<h2 id="tocS_liberrors.Error">liberrors.Error</h2>
<!-- backwards compatibility -->
<a id="schemaliberrors.error"></a>
<a id="schema_liberrors.Error"></a>
<a id="tocSliberrors.error"></a>
<a id="tocsliberrors.error"></a>

```json
{
  "code": "string",
  "error": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|error|string|false|none|none|

<h2 id="tocS_os.ListResponse">os.ListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaos.listresponse"></a>
<a id="schema_os.ListResponse"></a>
<a id="tocSos.listresponse"></a>
<a id="tocsos.listresponse"></a>

```json
{
  "data": [
    {
      "code": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[os.OS](#schemaos.os)]|false|none|none|

<h2 id="tocS_os.OS">os.OS</h2>
<!-- backwards compatibility -->
<a id="schemaos.os"></a>
<a id="schema_os.OS"></a>
<a id="tocSos.os"></a>
<a id="tocsos.os"></a>

```json
{
  "code": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|

<h2 id="tocS_osrelease.CreateRequestDTO">osrelease.CreateRequestDTO</h2>
<!-- backwards compatibility -->
<a id="schemaosrelease.createrequestdto"></a>
<a id="schema_osrelease.CreateRequestDTO"></a>
<a id="tocSosrelease.createrequestdto"></a>
<a id="tocsosrelease.createrequestdto"></a>

```json
{
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|version|string|false|none|none|

<h2 id="tocS_osrelease.ListResponse">osrelease.ListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaosrelease.listresponse"></a>
<a id="schema_osrelease.ListResponse"></a>
<a id="tocSosrelease.listresponse"></a>
<a id="tocsosrelease.listresponse"></a>

```json
{
  "data": [
    {
      "code": "string",
      "createdAt": "string",
      "isActive": true,
      "osCode": "string",
      "updatedAt": "string",
      "version": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[osrelease.ResponseDTO](#schemaosrelease.responsedto)]|false|none|none|

<h2 id="tocS_osrelease.ResponseDTO">osrelease.ResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemaosrelease.responsedto"></a>
<a id="schema_osrelease.ResponseDTO"></a>
<a id="tocSosrelease.responsedto"></a>
<a id="tocsosrelease.responsedto"></a>

```json
{
  "code": "string",
  "createdAt": "string",
  "isActive": true,
  "osCode": "string",
  "updatedAt": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|isActive|boolean|false|none|none|
|osCode|string|false|none|none|
|updatedAt|string|false|none|none|
|version|string|false|none|none|

<h2 id="tocS_release.ApplicationDTO">release.ApplicationDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.applicationdto"></a>
<a id="schema_release.ApplicationDTO"></a>
<a id="tocSrelease.applicationdto"></a>
<a id="tocsrelease.applicationdto"></a>

```json
{
  "changes": {
    "application": {
      "primaryCategoryCode": "string",
      "secondaryCategoryCode": "string"
    },
    "status": "DRAFT"
  },
  "code": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "id": "string",
  "osCode": "string",
  "ownerId": "string",
  "primaryCategoryCode": "string",
  "releases": {},
  "secondaryCategoryCode": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|changes|[release.ResponseApplicationChangesDTO](#schemarelease.responseapplicationchangesdto)|false|none|none|
|code|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|id|string|false|none|none|
|osCode|string|false|none|none|
|ownerId|string|false|none|none|
|primaryCategoryCode|string|false|none|none|
|releases|object|false|none|// TODO(s.tyapkin): remove this field from dto. It is useless and always nil.|
|secondaryCategoryCode|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_release.BuildResponseDTO">release.BuildResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.buildresponsedto"></a>
<a id="schema_release.BuildResponseDTO"></a>
<a id="tocSrelease.buildresponsedto"></a>
<a id="tocsrelease.buildresponsedto"></a>

```json
{
  "appCode": "string",
  "hasDeveloperSignature": true,
  "id": "string",
  "osCompatibility": {
    "osReleaseCodeFrom": "string",
    "osReleaseCodeTo": "string",
    "osReleaseLatestCompatible": true
  },
  "url": "string",
  "version": [
    null
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|appCode|string|false|none|none|
|hasDeveloperSignature|boolean|false|none|none|
|id|string|false|none|none|
|osCompatibility|[release.CompatibilityResponseDTO](#schemarelease.compatibilityresponsedto)|false|none|none|
|url|string|false|none|none|
|version|[version.Version](#schemaversion.version)|false|none|none|

<h2 id="tocS_release.CompatibilityResponseDTO">release.CompatibilityResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.compatibilityresponsedto"></a>
<a id="schema_release.CompatibilityResponseDTO"></a>
<a id="tocSrelease.compatibilityresponsedto"></a>
<a id="tocsrelease.compatibilityresponsedto"></a>

```json
{
  "osReleaseCodeFrom": "string",
  "osReleaseCodeTo": "string",
  "osReleaseLatestCompatible": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|osReleaseCodeFrom|string|false|none|none|
|osReleaseCodeTo|string|false|none|none|
|osReleaseLatestCompatible|boolean|false|none|none|

<h2 id="tocS_release.DependencyResponseDTO">release.DependencyResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.dependencyresponsedto"></a>
<a id="schema_release.DependencyResponseDTO"></a>
<a id="tocSrelease.dependencyresponsedto"></a>
<a id="tocsrelease.dependencyresponsedto"></a>

```json
{
  "id": "string",
  "name": "string",
  "url": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|name|string|false|none|none|
|url|string|false|none|none|
|version|string|false|none|none|

<h2 id="tocS_release.ListResponse">release.ListResponse</h2>
<!-- backwards compatibility -->
<a id="schemarelease.listresponse"></a>
<a id="schema_release.ListResponse"></a>
<a id="tocSrelease.listresponse"></a>
<a id="tocsrelease.listresponse"></a>

```json
{
  "data": [
    {
      "application": {
        "changes": {
          "application": {
            "primaryCategoryCode": "string",
            "secondaryCategoryCode": "string"
          },
          "status": "DRAFT"
        },
        "code": "string",
        "createdAt": "string",
        "deletedAt": "string",
        "id": "string",
        "osCode": "string",
        "ownerId": "string",
        "primaryCategoryCode": "string",
        "releases": {},
        "secondaryCategoryCode": "string",
        "updatedAt": "string"
      },
      "build": {
        "appCode": "string",
        "hasDeveloperSignature": true,
        "id": "string",
        "osCompatibility": {
          "osReleaseCodeFrom": "string",
          "osReleaseCodeTo": "string",
          "osReleaseLatestCompatible": true
        },
        "url": "string",
        "version": [
          null
        ]
      },
      "changelog": "string",
      "comment": "string",
      "createdAt": "string",
      "deletedAt": "string",
      "dependencies": [
        {
          "id": "string",
          "name": "string",
          "url": "string",
          "version": "string"
        }
      ],
      "description": "string",
      "icon": {
        "id": "string",
        "url": "string"
      },
      "id": "string",
      "keywords": "string",
      "name": "string",
      "policyUrl": "string",
      "screenshots": [
        {
          "id": "string",
          "url": "string"
        }
      ],
      "status": "DRAFT",
      "supportEmail": "string",
      "updatedAt": "string",
      "version": "string",
      "websiteUrl": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[release.ResponseReleaseDTO](#schemarelease.responsereleasedto)]|false|none|none|

<h2 id="tocS_release.RequestReleaseDTO">release.RequestReleaseDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.requestreleasedto"></a>
<a id="schema_release.RequestReleaseDTO"></a>
<a id="tocSrelease.requestreleasedto"></a>
<a id="tocsrelease.requestreleasedto"></a>

```json
{
  "build": {
    "id": "string"
  },
  "changelog": "string",
  "comment": "string",
  "dependencies": [
    {
      "id": "string"
    }
  ],
  "description": "string",
  "icon": {
    "id": "string"
  },
  "keywords": "string",
  "name": "string",
  "policyUrl": "string",
  "screenshots": [
    {
      "id": "string"
    }
  ],
  "supportEmail": "string",
  "version": "string",
  "websiteUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|build|[release.ResourceRequestDTO](#schemarelease.resourcerequestdto)|false|none|none|
|changelog|string|false|none|none|
|comment|string|false|none|none|
|dependencies|[[release.ResourceRequestDTO](#schemarelease.resourcerequestdto)]|false|none|none|
|description|string|false|none|none|
|icon|[release.ResourceRequestDTO](#schemarelease.resourcerequestdto)|false|none|none|
|keywords|string|false|none|none|
|name|string|false|none|none|
|policyUrl|string|false|none|none|
|screenshots|[[release.ResourceRequestDTO](#schemarelease.resourcerequestdto)]|false|none|none|
|supportEmail|string|false|none|none|
|version|string|false|none|none|
|websiteUrl|string|false|none|none|

<h2 id="tocS_release.ResourceRequestDTO">release.ResourceRequestDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.resourcerequestdto"></a>
<a id="schema_release.ResourceRequestDTO"></a>
<a id="tocSrelease.resourcerequestdto"></a>
<a id="tocsrelease.resourcerequestdto"></a>

```json
{
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|

<h2 id="tocS_release.ResourceResponseDTO">release.ResourceResponseDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.resourceresponsedto"></a>
<a id="schema_release.ResourceResponseDTO"></a>
<a id="tocSrelease.resourceresponsedto"></a>
<a id="tocsrelease.resourceresponsedto"></a>

```json
{
  "id": "string",
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|url|string|false|none|none|

<h2 id="tocS_release.ResponseApplicationChangesDTO">release.ResponseApplicationChangesDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.responseapplicationchangesdto"></a>
<a id="schema_release.ResponseApplicationChangesDTO"></a>
<a id="tocSrelease.responseapplicationchangesdto"></a>
<a id="tocsrelease.responseapplicationchangesdto"></a>

```json
{
  "application": {
    "primaryCategoryCode": "string",
    "secondaryCategoryCode": "string"
  },
  "status": "DRAFT"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|application|[release.ResponseApplicationChangesFieldsDTO](#schemarelease.responseapplicationchangesfieldsdto)|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|DRAFT|
|status|REWORK|
|status|REVIEW_PENDING|
|status|APPROVED|

<h2 id="tocS_release.ResponseApplicationChangesFieldsDTO">release.ResponseApplicationChangesFieldsDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.responseapplicationchangesfieldsdto"></a>
<a id="schema_release.ResponseApplicationChangesFieldsDTO"></a>
<a id="tocSrelease.responseapplicationchangesfieldsdto"></a>
<a id="tocsrelease.responseapplicationchangesfieldsdto"></a>

```json
{
  "primaryCategoryCode": "string",
  "secondaryCategoryCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|primaryCategoryCode|string|false|none|none|
|secondaryCategoryCode|string|false|none|none|

<h2 id="tocS_release.ResponseReleaseDTO">release.ResponseReleaseDTO</h2>
<!-- backwards compatibility -->
<a id="schemarelease.responsereleasedto"></a>
<a id="schema_release.ResponseReleaseDTO"></a>
<a id="tocSrelease.responsereleasedto"></a>
<a id="tocsrelease.responsereleasedto"></a>

```json
{
  "application": {
    "changes": {
      "application": {
        "primaryCategoryCode": "string",
        "secondaryCategoryCode": "string"
      },
      "status": "DRAFT"
    },
    "code": "string",
    "createdAt": "string",
    "deletedAt": "string",
    "id": "string",
    "osCode": "string",
    "ownerId": "string",
    "primaryCategoryCode": "string",
    "releases": {},
    "secondaryCategoryCode": "string",
    "updatedAt": "string"
  },
  "build": {
    "appCode": "string",
    "hasDeveloperSignature": true,
    "id": "string",
    "osCompatibility": {
      "osReleaseCodeFrom": "string",
      "osReleaseCodeTo": "string",
      "osReleaseLatestCompatible": true
    },
    "url": "string",
    "version": [
      null
    ]
  },
  "changelog": "string",
  "comment": "string",
  "createdAt": "string",
  "deletedAt": "string",
  "dependencies": [
    {
      "id": "string",
      "name": "string",
      "url": "string",
      "version": "string"
    }
  ],
  "description": "string",
  "icon": {
    "id": "string",
    "url": "string"
  },
  "id": "string",
  "keywords": "string",
  "name": "string",
  "policyUrl": "string",
  "screenshots": [
    {
      "id": "string",
      "url": "string"
    }
  ],
  "status": "DRAFT",
  "supportEmail": "string",
  "updatedAt": "string",
  "version": "string",
  "websiteUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|application|[release.ApplicationDTO](#schemarelease.applicationdto)|false|none|none|
|build|[release.BuildResponseDTO](#schemarelease.buildresponsedto)|false|none|none|
|changelog|string|false|none|none|
|comment|string|false|none|none|
|createdAt|string|false|none|none|
|deletedAt|string|false|none|none|
|dependencies|[[release.DependencyResponseDTO](#schemarelease.dependencyresponsedto)]|false|none|none|
|description|string|false|none|none|
|icon|[release.ResourceResponseDTO](#schemarelease.resourceresponsedto)|false|none|none|
|id|string|false|none|none|
|keywords|string|false|none|none|
|name|string|false|none|none|
|policyUrl|string|false|none|none|
|screenshots|[[release.ResourceResponseDTO](#schemarelease.resourceresponsedto)]|false|none|none|
|status|string|false|none|none|
|supportEmail|string|false|none|none|
|updatedAt|string|false|none|none|
|version|string|false|none|none|
|websiteUrl|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|DRAFT|
|status|REVIEW_PENDING|
|status|APPROVED|
|status|REWORK|
|status|DECLINED|

<h2 id="tocS_screenshot.ResponseScreenshotDTO">screenshot.ResponseScreenshotDTO</h2>
<!-- backwards compatibility -->
<a id="schemascreenshot.responsescreenshotdto"></a>
<a id="schema_screenshot.ResponseScreenshotDTO"></a>
<a id="tocSscreenshot.responsescreenshotdto"></a>
<a id="tocsscreenshot.responsescreenshotdto"></a>

```json
{
  "applicationId": "string",
  "createdAt": "string",
  "id": "string",
  "updatedAt": "string",
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|applicationId|string|false|none|none|
|createdAt|string|false|none|none|
|id|string|false|none|none|
|updatedAt|string|false|none|none|
|url|string|false|none|none|

<h2 id="tocS_version.Version">version.Version</h2>
<!-- backwards compatibility -->
<a id="schemaversion.version"></a>
<a id="schema_version.Version"></a>
<a id="tocSversion.version"></a>
<a id="tocsversion.version"></a>

```json
[
  null
]

```

### Properties

*None*

