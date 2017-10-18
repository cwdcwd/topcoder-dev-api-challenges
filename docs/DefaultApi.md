# ApChallengeMicroservice.DefaultApi

All URIs are relative to *http://api.topcoder-dev.com/v3*

Method | HTTP request | Description
------------- | ------------- | -------------
[**activateChallenge**](DefaultApi.md#activateChallenge) | **POST** /challenges/{id}/activate | 
[**cancelPrivateContest**](DefaultApi.md#cancelPrivateContest) | **POST** /challenges/{id}/cancel | 
[**challengeResultsGet**](DefaultApi.md#challengeResultsGet) | **GET** /challengeResults | 
[**challengesGet**](DefaultApi.md#challengesGet) | **GET** /challenges | 
[**challengesIdGet**](DefaultApi.md#challengesIdGet) | **GET** /challenges/{id} | 
[**challengesIdPut**](DefaultApi.md#challengesIdPut) | **PUT** /challenges/{id} | 
[**challengesIdResourcesDelete**](DefaultApi.md#challengesIdResourcesDelete) | **DELETE** /challenges/{id}/resources | 
[**challengesIdResourcesGet**](DefaultApi.md#challengesIdResourcesGet) | **GET** /challenges/{id}/resources | 
[**challengesIdResourcesPost**](DefaultApi.md#challengesIdResourcesPost) | **POST** /challenges/{id}/resources | 
[**closePrivateContest**](DefaultApi.md#closePrivateContest) | **POST** /challenges/{id}/close | 
[**directChallengesGet**](DefaultApi.md#directChallengesGet) | **GET** /direct/challenges | 
[**getChallengeTypes**](DefaultApi.md#getChallengeTypes) | **GET** /challenge-types | 
[**marathonMatcheResultsGet**](DefaultApi.md#marathonMatcheResultsGet) | **GET** /marathonMatcheResults | 
[**marathonMatchesGet**](DefaultApi.md#marathonMatchesGet) | **GET** /marathonMatches | 
[**membersHandleChallengesGet**](DefaultApi.md#membersHandleChallengesGet) | **GET** /members/{handle}/challenges | 
[**membersHandleMmsGet**](DefaultApi.md#membersHandleMmsGet) | **GET** /members/{handle}/mms | 
[**membersHandleSrmsGet**](DefaultApi.md#membersHandleSrmsGet) | **GET** /members/{handle}/srms | 
[**phasesGet**](DefaultApi.md#phasesGet) | **GET** /phases | 
[**platformsGet**](DefaultApi.md#platformsGet) | **GET** /platforms | 
[**platformsIdDelete**](DefaultApi.md#platformsIdDelete) | **DELETE** /platforms/{id} | 
[**platformsIdPatch**](DefaultApi.md#platformsIdPatch) | **PATCH** /platforms/{id} | 
[**platformsPost**](DefaultApi.md#platformsPost) | **POST** /platforms | 
[**registerChallenge**](DefaultApi.md#registerChallenge) | **POST** /challenges/{id}/register | 
[**saveDraftContest**](DefaultApi.md#saveDraftContest) | **POST** /challenges | 
[**srmResultsGet**](DefaultApi.md#srmResultsGet) | **GET** /srmResults | 
[**srmsGet**](DefaultApi.md#srmsGet) | **GET** /srms | 
[**technologiesGet**](DefaultApi.md#technologiesGet) | **GET** /technologies | 
[**technologiesIdDelete**](DefaultApi.md#technologiesIdDelete) | **DELETE** /technologies/{id} | 
[**technologiesIdPatch**](DefaultApi.md#technologiesIdPatch) | **PATCH** /technologies/{id} | 
[**technologiesPost**](DefaultApi.md#technologiesPost) | **POST** /technologies | 
[**unregisterChallenge**](DefaultApi.md#unregisterChallenge) | **POST** /challenges/{id}/unregister | 


<a name="activateChallenge"></a>
# **activateChallenge**
> ChallengeResponse activateChallenge(id)



Activate a draft challenge

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = "id_example"; // String | the id of the draft challenge


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.activateChallenge(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| the id of the draft challenge | 

### Return type

[**ChallengeResponse**](ChallengeResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="cancelPrivateContest"></a>
# **cancelPrivateContest**
> NullResponse cancelPrivateContest(id)



Cancel the private task

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | the id of the challenge


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.cancelPrivateContest(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| the id of the challenge | 

### Return type

[**NullResponse**](NullResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="challengeResultsGet"></a>
# **challengeResultsGet**
> InlineResponse200 challengeResultsGet(opts)



Retrieves results of dev and design challenges. These parameters parameters are optional, if none is provided, returns 10 first phases accessible by the user, ordered by createAt date desc, i.e. recent 10 phases.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + userId - filter by challenges in which the user has a role + challengeId - id of the challenge for which to return the results. 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengeResultsGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + userId - filter by challenges in which the user has a role + challengeId - id of the challenge for which to return the results.  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse200**](InlineResponse200.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="challengesGet"></a>
# **challengesGet**
> InlineResponse2001 challengesGet(opts)



Retrieve active/past results for dev/design/data science challenges.  This endpoint serves results based on filter variable list_type ( active/past) and filter variable type ( data_science / develop /design ). 

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec  + userId - Filter by user_id + challengeType + challengeName - Challenge Name + challengeId + platforms + technologies + reviewType + prizeLowerBound + prizeUpperBound + submissionEndFrom + submissionEndTo + projectId - Filter by Direct project id + projectName - Filter by Direct project name, only available for admin + isTask - Filter by isTask field + groupIds - Filter by the group ids, it will only be used and when the API is called with authenticated user.  The value should be ids separated by comma. 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengesGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec  + userId - Filter by user_id + challengeType + challengeName - Challenge Name + challengeId + platforms + technologies + reviewType + prizeLowerBound + prizeUpperBound + submissionEndFrom + submissionEndTo + projectId - Filter by Direct project id + projectName - Filter by Direct project name, only available for admin + isTask - Filter by isTask field + groupIds - Filter by the group ids, it will only be used and when the API is called with authenticated user.  The value should be ids separated by comma.  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2001**](InlineResponse2001.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="challengesIdGet"></a>
# **challengesIdGet**
> InlineResponse2002 challengesIdGet(id)



Get challenge details.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | The challenge id to get the challenge details.


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengesIdGet(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| The challenge id to get the challenge details. | 

### Return type

[**InlineResponse2002**](InlineResponse2002.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="challengesIdPut"></a>
# **challengesIdPut**
> ChallengeResponse challengesIdPut(id, body)



Update the challenge

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | The id of the challenge.

var body = new ApChallengeMicroservice.UpdateChallengeBodyParam(); // UpdateChallengeBodyParam | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengesIdPut(id, body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| The id of the challenge. | 
 **body** | [**UpdateChallengeBodyParam**](UpdateChallengeBodyParam.md)|  | 

### Return type

[**ChallengeResponse**](ChallengeResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="challengesIdResourcesDelete"></a>
# **challengesIdResourcesDelete**
> ManageResourceResponse challengesIdResourcesDelete(id, body)



Remove Resource from a challenge

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | The id of the challenge from which to remove the resource

var body = new ApChallengeMicroservice.RemoveResourceBody(); // RemoveResourceBody | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengesIdResourcesDelete(id, body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| The id of the challenge from which to remove the resource | 
 **body** | [**RemoveResourceBody**](RemoveResourceBody.md)|  | 

### Return type

[**ManageResourceResponse**](ManageResourceResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="challengesIdResourcesGet"></a>
# **challengesIdResourcesGet**
> GetResourceResponse challengesIdResourcesGet(id)



Get all resources for a challenge.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | The id of the challenge.


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengesIdResourcesGet(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| The id of the challenge. | 

### Return type

[**GetResourceResponse**](GetResourceResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="challengesIdResourcesPost"></a>
# **challengesIdResourcesPost**
> ManageResourceResponse challengesIdResourcesPost(id, body)



Add Resource to a challenge.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | The id of the challenge to which to add the resource.

var body = new ApChallengeMicroservice.AddResourceBody(); // AddResourceBody | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.challengesIdResourcesPost(id, body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| The id of the challenge to which to add the resource. | 
 **body** | [**AddResourceBody**](AddResourceBody.md)|  | 

### Return type

[**ManageResourceResponse**](ManageResourceResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="closePrivateContest"></a>
# **closePrivateContest**
> NullResponse closePrivateContest(id)



Close the private task

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | the id of the challenge


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.closePrivateContest(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| the id of the challenge | 

### Return type

[**NullResponse**](NullResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="directChallengesGet"></a>
# **directChallengesGet**
> InlineResponse2003 directChallengesGet(opts)



get challenges

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec  + type - Filter by challenge status type, it must be active, past, or draft + creator - Only return challenges created by current user + directProjectId - Filter by direct project id + clientId - Filter by client id + billingId - Filter by billing id + startDateFrom - Left range of the challenge start date  + startDateTo - Right range of the challenge start date + endDateFrom - Left range of the challenge end date + endDateTo - Right range of the challenge end date + challengeType - Filter by challenge type + challengeStatus - Filter by challenge status + challengeTechnologies - Filter by challenge technologies + challengePlatforms - Filter by challenge platforms + directProjectName - Filter by direct project name 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
  'orderBy': "orderBy_example" // String | sort the result by the provided order by clause
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.directChallengesGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec  + type - Filter by challenge status type, it must be active, past, or draft + creator - Only return challenges created by current user + directProjectId - Filter by direct project id + clientId - Filter by client id + billingId - Filter by billing id + startDateFrom - Left range of the challenge start date  + startDateTo - Right range of the challenge start date + endDateFrom - Left range of the challenge end date + endDateTo - Right range of the challenge end date + challengeType - Filter by challenge type + challengeStatus - Filter by challenge status + challengeTechnologies - Filter by challenge technologies + challengePlatforms - Filter by challenge platforms + directProjectName - Filter by direct project name  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 
 **orderBy** | **String**| sort the result by the provided order by clause | [optional] 

### Return type

[**InlineResponse2003**](InlineResponse2003.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="getChallengeTypes"></a>
# **getChallengeTypes**
> ChallengeTypeResponse getChallengeTypes()



Get challenge types

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.getChallengeTypes(callback);
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**ChallengeTypeResponse**](ChallengeTypeResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="marathonMatcheResultsGet"></a>
# **marathonMatcheResultsGet**
> InlineResponse2004 marathonMatcheResultsGet(opts)



Retrieves results for marathon matches. These parameters parameters are optional, if none is provided, returns 10 first phases accessible by the user, ordered by createAt date desc, i.e. recent 10 phases.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + contestId - id of the marathon match + userId - filters by user id 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.marathonMatcheResultsGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + contestId - id of the marathon match + userId - filters by user id  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2004**](InlineResponse2004.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="marathonMatchesGet"></a>
# **marathonMatchesGet**
> InlineResponse2005 marathonMatchesGet(opts)



Retrieves marathon matches. These parameters parameters are optional, if none is provided, returns 10 first phases accessible by the user, ordered by createAt date desc, i.e. recent 10 phases.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + listType - active or past + userId - filters by marathon matches in which the user has a role 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.marathonMatchesGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + listType - active or past + userId - filters by marathon matches in which the user has a role  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2005**](InlineResponse2005.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="membersHandleChallengesGet"></a>
# **membersHandleChallengesGet**
> InlineResponse2006 membersHandleChallengesGet(handle, opts)



Retrieve Challenges of a particular user handle.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var handle = "handle_example"; // String | the handle of the user

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + id - Filter by challenge id, it supports a single id as in id=123 or an in filter: id=in(123,456) + isPrivate - Filter by private flag, boolean + technologies - Filter by a single technology + platforms - Filter by a single platform + userIds - Filter by a single userId + forumId - Filter by a forum id + reviewType - Filter by review type, values are Internal, peer + status - Active, Completed + subTrack - One of the allowed subTrack Values + track - One of the allowed Track values + hasUserSubmittedForReview - boolean value indicating if user has submitted for review + name - Challenge name + projectId - Filter by Direct project id + projectName - Filter by Direct project name, only available for admin + isTask - Filter type isTask field + groupIds - Filter by the group ids, it will only be used and when the API is called with authenticated user.  The value should be ids separated by comma. 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.membersHandleChallengesGet(handle, opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **handle** | **String**| the handle of the user | 
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + id - Filter by challenge id, it supports a single id as in id&#x3D;123 or an in filter: id&#x3D;in(123,456) + isPrivate - Filter by private flag, boolean + technologies - Filter by a single technology + platforms - Filter by a single platform + userIds - Filter by a single userId + forumId - Filter by a forum id + reviewType - Filter by review type, values are Internal, peer + status - Active, Completed + subTrack - One of the allowed subTrack Values + track - One of the allowed Track values + hasUserSubmittedForReview - boolean value indicating if user has submitted for review + name - Challenge name + projectId - Filter by Direct project id + projectName - Filter by Direct project name, only available for admin + isTask - Filter type isTask field + groupIds - Filter by the group ids, it will only be used and when the API is called with authenticated user.  The value should be ids separated by comma.  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2006**](InlineResponse2006.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="membersHandleMmsGet"></a>
# **membersHandleMmsGet**
> InlineResponse2007 membersHandleMmsGet(handle, opts)



Retrieve MMs of a particular user handle.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var handle = "handle_example"; // String | the handle of the user

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + id - Filter by srm id + userIds - Filter by a single userId + forumId - Filter by a forum id + status - Active, Completed + name - MM name + startDate - Start date of particular MM + endDate - End date of particular MM + isRatedForMM - Boolean, indicating is user is rated for this MM 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.membersHandleMmsGet(handle, opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **handle** | **String**| the handle of the user | 
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + id - Filter by srm id + userIds - Filter by a single userId + forumId - Filter by a forum id + status - Active, Completed + name - MM name + startDate - Start date of particular MM + endDate - End date of particular MM + isRatedForMM - Boolean, indicating is user is rated for this MM  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2007**](InlineResponse2007.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="membersHandleSrmsGet"></a>
# **membersHandleSrmsGet**
> InlineResponse2008 membersHandleSrmsGet(handle, opts)



Retrieve SRMs of a particular user handle.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var handle = "handle_example"; // String | the handle of the user

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + id - Filter by srm id + userIds - Filter by a single userId + forumId - Filter by a forum id + status - Active, Completed + name - SRM name + startDate - Start date of particular SRM + endDate - End date of particular SRM + isRatedForSRM - Boolean, indicating is user is rated for this SRM 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.membersHandleSrmsGet(handle, opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **handle** | **String**| the handle of the user | 
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + id - Filter by srm id + userIds - Filter by a single userId + forumId - Filter by a forum id + status - Active, Completed + name - SRM name + startDate - Start date of particular SRM + endDate - End date of particular SRM + isRatedForSRM - Boolean, indicating is user is rated for this SRM  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2008**](InlineResponse2008.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="phasesGet"></a>
# **phasesGet**
> InlineResponse2009 phasesGet(opts)



Retrieves phases for dev and design challenges. These parameters parameters are optional, if none is provided, returns 10 first phases accessible by the user, ordered by createAt date desc, i.e. recent 10 phases.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + challengeId - The id of the challenge for which to fetch phases. Supports comma separated list of values to fetch phases for multiple challenges. 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.phasesGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + challengeId - The id of the challenge for which to fetch phases. Supports comma separated list of values to fetch phases for multiple challenges.  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse2009**](InlineResponse2009.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="platformsGet"></a>
# **platformsGet**
> PlatformArrayResponse platformsGet()



return all platforms

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.platformsGet(callback);
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**PlatformArrayResponse**](PlatformArrayResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="platformsIdDelete"></a>
# **platformsIdDelete**
> NormalResponse platformsIdDelete(id)



delete a single platform. currently this endpoint is just a mock.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.platformsIdDelete(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**|  | 

### Return type

[**NormalResponse**](NormalResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="platformsIdPatch"></a>
# **platformsIdPatch**
> PlatformResponse platformsIdPatch(id, body)



update a single platform

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | 

var body = new ApChallengeMicroservice.NewPlatformBodyParam(); // NewPlatformBodyParam | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.platformsIdPatch(id, body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**|  | 
 **body** | [**NewPlatformBodyParam**](NewPlatformBodyParam.md)|  | 

### Return type

[**PlatformResponse**](PlatformResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="platformsPost"></a>
# **platformsPost**
> PlatformResponse platformsPost(body)



create a new platform

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var body = new ApChallengeMicroservice.NewPlatformBodyParam(); // NewPlatformBodyParam | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.platformsPost(body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**NewPlatformBodyParam**](NewPlatformBodyParam.md)|  | 

### Return type

[**PlatformResponse**](PlatformResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="registerChallenge"></a>
# **registerChallenge**
> NormalResponse registerChallenge(id)



Register for a challenge

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | the id of the challenge


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.registerChallenge(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| the id of the challenge | 

### Return type

[**NormalResponse**](NormalResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="saveDraftContest"></a>
# **saveDraftContest**
> ChallengeResponse saveDraftContest(body)



Create a draft challenge

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var body = new ApChallengeMicroservice.NewChallengeBodyParam(); // NewChallengeBodyParam | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.saveDraftContest(body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**NewChallengeBodyParam**](NewChallengeBodyParam.md)|  | 

### Return type

[**ChallengeResponse**](ChallengeResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="srmResultsGet"></a>
# **srmResultsGet**
> InlineResponse20010 srmResultsGet(opts)



Retrieves single round matche results. These parameters parameters are optional, if none is provided, returns 10 first phases accessible by the user, ordered by createAt date desc, i.e. recent 10 phases.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + userId - filters by srms in which the user has a role + contestId - Id of the srm to return results 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.srmResultsGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + userId - filters by srms in which the user has a role + contestId - Id of the srm to return results  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse20010**](InlineResponse20010.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="srmsGet"></a>
# **srmsGet**
> InlineResponse20011 srmsGet(opts)



Retrieves single round matches. These parameters parameters are optional, if none is provided, returns 10 first phases accessible by the user, ordered by createAt date desc, i.e. recent 10 phases.

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var opts = { 
  'filter': "filter_example", // String | fieldName=fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + listType - future, active, or past + userId - filters by srms in which the user has a role 
  'offset': 56, // Integer | number of items to skip. Defaults to 0
  'limit': 56 // Integer | max records to return. Defaults to 10
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.srmsGet(opts, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **String**| fieldName&#x3D;fieldValue (enum[string],optional)  - parameter for filtering the fields according to v3 spec + listType - future, active, or past + userId - filters by srms in which the user has a role  | [optional] 
 **offset** | **Integer**| number of items to skip. Defaults to 0 | [optional] 
 **limit** | **Integer**| max records to return. Defaults to 10 | [optional] 

### Return type

[**InlineResponse20011**](InlineResponse20011.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="technologiesGet"></a>
# **technologiesGet**
> TechnologyArrayResponse technologiesGet()



return all technologies

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.technologiesGet(callback);
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**TechnologyArrayResponse**](TechnologyArrayResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="technologiesIdDelete"></a>
# **technologiesIdDelete**
> NormalResponse technologiesIdDelete(id)



delete a single technology

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.technologiesIdDelete(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**|  | 

### Return type

[**NormalResponse**](NormalResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="technologiesIdPatch"></a>
# **technologiesIdPatch**
> TechnologyResponse technologiesIdPatch(id, body)



update a single technology

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | 

var body = new ApChallengeMicroservice.NewTechnologyBodyParam(); // NewTechnologyBodyParam | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.technologiesIdPatch(id, body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**|  | 
 **body** | [**NewTechnologyBodyParam**](NewTechnologyBodyParam.md)|  | 

### Return type

[**TechnologyResponse**](TechnologyResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="technologiesPost"></a>
# **technologiesPost**
> TechnologyResponse technologiesPost(body)



create a new technology

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var body = new ApChallengeMicroservice.NewTechnologyBodyParam(); // NewTechnologyBodyParam | 


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.technologiesPost(body, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**NewTechnologyBodyParam**](NewTechnologyBodyParam.md)|  | 

### Return type

[**TechnologyResponse**](TechnologyResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

<a name="unregisterChallenge"></a>
# **unregisterChallenge**
> NormalResponse unregisterChallenge(id)



Unregister for a challenge

### Example
```javascript
var ApChallengeMicroservice = require('ap_challenge_microservice');
var defaultClient = ApChallengeMicroservice.ApiClient.default;

// Configure API key authorization: bearer
var bearer = defaultClient.authentications['bearer'];
bearer.apiKey = 'YOUR API KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//bearer.apiKeyPrefix = 'Token';

var apiInstance = new ApChallengeMicroservice.DefaultApi();

var id = 3.4; // Number | the id of the challenge


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
apiInstance.unregisterChallenge(id, callback);
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **Number**| the id of the challenge | 

### Return type

[**NormalResponse**](NormalResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

