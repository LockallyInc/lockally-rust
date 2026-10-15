# \TestApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**simulate_inbound_email**](TestApi.md#simulate_inbound_email) | **POST** /v1/test/inbound | Simulate an inbound email (test keys only)



## simulate_inbound_email

> models::SimulatedInbound simulate_inbound_email()
Simulate an inbound email (test keys only)

Runs a synthetic message through the REAL indexing pipeline — thread adoption, deterministic extraction (incl. injection_risk), and the message.received webhook — so the whole agent loop is testable without a real domain or MTA. Requires an lk_test_* key (create with {\"test\": true} on POST /v1/api-keys). Body: {mailbox, from, subject, text, in_reply_to?, references?}.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::SimulatedInbound**](SimulatedInbound.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

