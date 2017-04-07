# ApChallengeMicroservice.InlineResponse2002ResultContent

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**phaseType** | **String** | the phase type | [optional] 
**status** | **String** | the status | [optional] 
**fixedStarTime** | **Date** | fixed start time ISO-8601 formatted date times (YYYY-MM-DDTHH:mm:ss.sssZ) | [optional] 
**scheduledStarTime** | **Date** | the scheduled start time ISO-8601 formatted date times (YYYY-MM-DDTHH:mm:ss.sssZ) | [optional] 
**scheduledEndTime** | **Date** | the scheduled end time ISO-8601 formatted date times (YYYY-MM-DDTHH:mm:ss.sssZ) | [optional] 
**actualStartTime** | **Date** | the actual start time ISO-8601 formatted date times (YYYY-MM-DDTHH:mm:ss.sssZ) | [optional] 
**actualEndTime** | **Date** | the actual end time ISO-8601 formatted date times (YYYY-MM-DDTHH:mm:ss.sssZ) | [optional] 
**duration** | **String** | the duration | [optional] 


<a name="PhaseTypeEnum"></a>
## Enum: PhaseTypeEnum


* `Registration` (value: `"Registration"`)

* `Submission` (value: `"Submission"`)

* `Screening` (value: `"Screening"`)

* `Review` (value: `"Review"`)

* `Appeals` (value: `"Appeals"`)

* `Appeals Response` (value: `"Appeals Response"`)

* `Aggregation` (value: `"Aggregation"`)

* `Aggregation Review` (value: `"Aggregation Review"`)

* `Final Fix` (value: `"Final Fix"`)

* `Final Review` (value: `"Final Review"`)

* `Approval` (value: `"Approval"`)

* `Post-Mortem` (value: `"Post-Mortem"`)

* `Specification Submission` (value: `"Specification Submission"`)

* `Specification Review` (value: `"Specification Review"`)

* `Checkpoint Submission` (value: `"Checkpoint Submission"`)

* `Checkpoint Screening` (value: `"Checkpoint Screening"`)

* `Checkpoint Review` (value: `"Checkpoint Review"`)

* `Iterative Review` (value: `"Iterative Review"`)




<a name="StatusEnum"></a>
## Enum: StatusEnum


* `Scheduled` (value: `"Scheduled"`)

* `Open` (value: `"Open"`)

* `Closed` (value: `"Closed"`)




