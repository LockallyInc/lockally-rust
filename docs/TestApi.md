# \TestApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_test_inbound_post**](TestApi.md#v1_test_inbound_post) | **POST** /v1/test/inbound | Simulate an inbound email (test keys only)



## v1_test_inbound_post

> serde_json::Value v1_test_inbound_post()
Simulate an inbound email (test keys only)

Runs a synthetic message through the REAL indexing pipeline — thread adoption, deterministic extraction (incl. injection_risk), and the message.received webhook — so the whole agent loop is testable without a real domain or MTA. Requires an lk_test_* key (create with {\"test\": true} on POST /v1/api-keys). Body: {mailbox, from, subject, text, in_reply_to?, references?}.

### Parameters

This endpoint does not need any parameter.

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

