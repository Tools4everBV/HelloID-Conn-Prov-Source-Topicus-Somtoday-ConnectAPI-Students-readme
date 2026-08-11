# HelloID-Conn-Prov-Source-Topicus-Somtoday-ConnectAPI-Students-readme

| :warning: Warning - **You need to sign a contract with the supplier before implementing this connector**|
|:---------------------------|
| This repository contains the connector and configuration code only. The implementer is responsible to acquire the connection details such as username, password, certificate, etc. Please contact the client's application manager to coordinate the connector requirements. |

| :information_source: Contact |
|:---------------------------|
| Please contact your local Tools4ever sales representative for further information and details about the implementation of this connector |

<br />
<p align="center">
  <img src="https://www.tools4ever.nl/connector-logos/somtoday-logo.png">
</p>

## Table of contents

- [HelloID-Conn-Prov-Source-Topicus-Somtoday-ConnectAPI-Students-readme](#helloid-conn-prov-source-topicus-somtoday-connectapi-students-readme)
  - [Table of contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting started](#getting-started)
    - [Connection settings](#connection-settings)
    - [Prerequisites](#prerequisites)
    - [Remarks](#remarks)
      - [Contract types configuration](#contract-types-configuration)
      - [Field mapping examples](#field-mapping-examples)
      - [Memory considerations](#memory-considerations)
      - [Access card and safe information](#access-card-and-safe-information)
      - [Address information](#address-information)
  - [Migration from v1.0.0](#migration-from-v100)
    - [Required Configuration Changes](#required-configuration-changes)
    - [Data Structure Changes](#data-structure-changes)
    - [Recommended Migration Steps](#recommended-migration-steps)
  - [Getting help](#getting-help)
  - [HelloID docs](#helloid-docs)

## Introduction

HelloID-Conn-Prov-Source-Topicus-Somtoday-Students is a source connector. Topicus-Somtoday-Students provides a set of REST APIs that allow you to programmatically interact with its data. The connector retrieves the students from SOMToday. Because working with students and not with employees, there is no such thing as Employments and Positions. The connector formats the "subject choice", "class group", and placements (vakkeuzes, lesgroepen, plaatsingen) to HelloID contracts. This results in three different types of HelloID objects.

**Version 2.0.0:** This is a major release with breaking changes. You can now configure which contract types are included through the connector configuration. Each contract type (placements, class groups, subject choices) can be individually enabled or disabled based on your requirements.

During implementation, you must choose between those contract types or make a combination of multiple. This connector is built with active data and only example future data from a Test environment.

## Getting started

### Connection settings

The following settings are required to connect to the API.

| Setting | Description | Mandatory | Version | Notes |
| --- | --- | --- | --- | --- |
| ClientID | The ClientID to connect to the API | Yes | 1.0.0+ | |
| ClientSecret | The Password to connect to the API | Yes | 1.0.0+ | |
| BaseUrl | The URL to the API | Yes | 1.0.0+ | |
| ProxyTokenUrl | The URL to the connector-proxy for retrieving the OAuth token | Yes | 1.0.0+ | |
| Institution | The name of the organization | Yes | 2.0.0+ | **BREAKING:** Renamed from `Instelling` |
| ~~Instelling~~ | ~~The name of the organization~~ | ~~Yes~~ | 1.0.0 only | Removed in v2.0.0 |
| CollectCardInfo | Collect access card information (switch) | No | 1.0.0+ | |
| CollectSafeInfo | Collect safe information (switch) | No | 1.0.0+ | |
| IncludePlacements | Include placements (plaatsingen) as contracts | No | 2.0.0+ | Default: `true` |
| IncludeClassGroups | Include class groups (lesgroepen) as contracts | No | 2.0.0+ | Default: `true` |
| IncludeSubjectChoices | Include subject choices (vakkeuzes) as contracts | No | 2.0.0+ | Default: `true` |
| IsDebug | Enable debug logging | No | 1.0.0+ | |

### Prerequisites

- As implementer, you need your own set of credentials before you can implement this connector. Therefore you need to sign a contract with the supplier.

### Remarks

#### Contract types configuration

**Version 2.0.0:** The connector provides granular control over which contract types are included:

- **IncludePlacements**: When enabled (default: `true`), placements (plaatsingen) are included as contracts
- **IncludeClassGroups**: When enabled (default: `true`), class groups (lesgroepen) are included as contracts  
- **IncludeSubjectChoices**: When enabled (default: `true`), subject choices (vakkeuzes) are included as contracts

Each contract receives a unique `ExternalId` based on its UUID and validity period (start/end dates) in the format: `uuid_startdatum_einddatum`. This ensures proper tracking and deduplication of contracts.

**Important:** The connector automatically deduplicates contracts based on their ExternalId. If a student appears in multiple school years with the same contract, only one instance will be kept.

**Person DisplayName format (v2.0.0):** The DisplayName now includes the student number: `"Roepnaam Achternaam (12345)"`. This may affect HelloID correlation if you are upgrading from v1.0.0.

#### Field mapping examples

The connector includes a comprehensive `mapping.json` with examples for common mapping scenarios. Below are some key mappings available:

**Person Mappings:**
- **Basic fields**: ExternalId, Name fields (FamilyName, FamilyNamePrefix, GivenName, Initials, NickName)
- **Contact**: Email address (emailadres), phone numbers
- **Custom fields**: UUID, LeerlingNummer, Source, ageGroup (Adult/NotAdult based on birth date)

**Contract Mappings:**
- **Contract identification**: ExternalId, Type (plaatsingen/lesgroepen/vakkeuzes)
- **Dates**: StartDate (dynamically determined based on contract type), EndDate
- **Location**: vestiging.naam, vestiging.afkorting (location name and abbreviation)
- **Department**: Automatically mapped based on contract type (stamgroep for placements, naam for class groups)
- **Manager**: Mapped to first mentor (medewerker_uuid) if available
- **Custom fields**: leerjaar, groep, lesgroep, EndDateInPast (calculated)

**Example: Dynamic StartDate based on contract type**
```javascript
function getStartDate(){
    let startDate = null;

    if (sourceContract.Type == 'plaatsingen') {
        startDate = sourceContract.startdatum;
    }
    else if(sourceContract.Type == 'lesgroepen') {
        startDate = sourceContract.begindatum;
    }
    else if(sourceContract.Type == 'vakkeuzes') {
        startDate = sourceContract.begindatum;
    }

    return startDate;
}

getStartDate();
```

**Example: Department mapping based on contract type**
```javascript
function getDepartmentDisplayName(){
    let departmentDisplayName = null;

    if (sourceContract.Type == 'plaatsingen') {
        if (sourceContract.stamgroep) {
            departmentDisplayName = sourceContract.stamgroep.naam;
        }
    }
    else if(sourceContract.Type == 'lesgroepen') {
        departmentDisplayName = sourceContract.naam;
    }

    return departmentDisplayName;
}

getDepartmentDisplayName();
```


#### Memory considerations

Not each object in (Vakkeuzes) contains a UUID, which seem to be the unique ID. These (Vakkeuzes) do not have a unique id, what results in blocked contracts in HelloID. (This might be a issue of Test data in the Test environment).

There is no calculation of the manager. Due to there being no manager relationship between students and a manager.

The "Vakkeuzes" object for each student contains a lot of data, which may be too much for processing around 3000 students and above, which results in a `System.OutOfMemoryException`. Therefore, if you do not require certain fields, please exclude it from the response. This can be done in the loop at approximately line 180-190. If you still require particular properties of (vakkeuzes) or a different Sub-object please use calculated property and specify only the field(s) required.

See the following Example of an exclusion:

```powershell
$responseStudents = [array](Invoke-TopicusStudentsRestMethod @splatRestParams -ResultCollectionName 'Leerlingen') | Select-Object * , @{Name = 'vakkeuzesUuid'; Expression = { $_.vakkeuzes.uuid } }  -ExcludeProperty adres, plaatsingen, vestiging, lesgroepen, verzorgers, vakkeuzes
```

Calculated property:

```powershell
Select-Object *, @{Name = 'vakkeuzesUuid'; Expression = { $_.vakkeuzes.uuid } }
```

**Alternatively (version 2.0.0):** You can simply disable `IncludeSubjectChoices` in the configuration if you don't need subject choices as contracts. This is cleaner than modifying the code.

#### Access card and safe information

**[November 2024]** The connector has been extended with the options to collect access card ("toegangspas") information, and Safe ("kluis") information. This can be stored as custom properties on the person. If there are more than one access card or safe number associated with a student, the result is stored as a (;-separated) text string.

The custom text properties that need to be added are:

**Access Card Information:**
- CardLocationName
- CardNumber
- CardReturned
- CardValidFrom
- CardValidUntil

**Safe Information:**
- SafeLocationName
- SafeKeyNumber
- SafeKeyReturned
- SafeNumber
- SafeValidFrom
- SafeValidUntil

For more information how to add custom fields see [https://docs.helloid.com/en/provisioning/persons/person-schema/add-a-custom-person-or-contract-field.html](https://docs.helloid.com/en/provisioning/persons/person-schema/add-a-custom-person-or-contract-field.html)

> **Version 2.0.0 Note:** These properties are only added to the person object when `CollectCardInfo` or `CollectSafeInfo` are enabled in the configuration. If you are upgrading from v1.0.0 where these properties were always added (even when empty), ensure your HelloID field mappings can handle missing properties or enable these flags.

#### Address information

By default, a user in SOM has a property called `adres_geheim`. When this property is set to `true`, no address information is available for that specific user. When adding address information in your fieldmapping we recommend you use this example below:

```javascript
function HouseNumber() {
  if (source.adres_geheim === true || source.adres_geheim === "True") {
    return null;
  }
  return source.adres.huisnummer_zonder_toevoeging;
}
HouseNumber();
```

## Migration from v1.0.0

⚠️ **Version 2.0.0 contains breaking changes.** If you are upgrading from v1.0.0, please review the following:

### Required Configuration Changes

1. **Rename configuration parameter:**
   - Change `Instelling` to `Institution`

2. **Add new configuration flags (all default to `true`):**
   - `IncludePlacements`
   - `IncludeClassGroups`
   - `IncludeSubjectChoices`

### Data Structure Changes

1. **Person DisplayName format changed:**
   - v1.0.0: `"Jan Jansen"`
   - v2.0.0: `"Jan Jansen (12345)"`
   - **Action required:** Review HelloID correlation rules if they depend on DisplayName

2. **Contract ExternalId added:**
   - All contracts now have a unique ExternalId in format: `uuid_startdatum_einddatum`
   - Automatic deduplication based on ExternalId
   - **Action required:** None, this is an improvement

3. **Card and Safe properties now conditional:**
   - v1.0.0: Always added (even when empty)
   - v2.0.0: Only added when `CollectCardInfo` or `CollectSafeInfo` are `true`
   - **Action required:** Ensure your field mappings can handle missing properties, or enable these flags

4. **Location (vestiging) enrichment:**
   - Placements and class groups now include full location object with additional details
   - New field available: `vestiging.afkorting` (location abbreviation)
   - **Action required:** None, this is an enhancement

5. **Enhanced mapping.json:**
   - Comprehensive examples for contract type differentiation
   - Department and Manager mappings now available
   - Dynamic StartDate handling based on contract type
   - **Action required:** Review and update your field mappings to leverage new capabilities

### Recommended Migration Steps

1. Test the connector in a non-production environment first
2. Update configuration with new parameter names and flags
3. Review and update HelloID field mappings if needed
4. Verify correlation rules still work with new DisplayName format
5. Deploy to production during a maintenance window

## Getting help

> _For more information on how to configure a HelloID PowerShell connector, please refer to our [documentation](https://docs.helloid.com/hc/en-us/articles/360012557600-Configure-a-custom-PowerShell-source-system) pages_

## HelloID docs

The official HelloID documentation can be found at: https://docs.helloid.com/
