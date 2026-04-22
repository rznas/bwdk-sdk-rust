# \MerchantWalletApi

All URIs are relative to *https://bwdk-backend.digify.shop*

Method | HTTP request | Description
------------- | ------------- | -------------
[**wallets_api_v1_wallet_balance_retrieve**](MerchantWalletApi.md#wallets_api_v1_wallet_balance_retrieve) | **GET** /wallets/api/v1/wallet-balance/ | Get Wallet Balance



## wallets_api_v1_wallet_balance_retrieve

> models::WalletBalance wallets_api_v1_wallet_balance_retrieve()
Get Wallet Balance

<div dir=\"rtl\" style=\"text-align: right;\">  موجودی کیف پول فروشنده  ## توضیحات  این endpoint موجودی کیف پول فروشنده را برمی‌گرداند. کیف پول برای پرداخت هزینه ارسال دیجی‌اکسپرس استفاده می‌شود. هنگام ثبت مرسوله دیجی‌اکسپرس، هزینه ارسال به‌صورت خودکار از کیف پول کسر می‌شود.  نیاز به **API_KEY** فروشنده دارد.  </div> 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::WalletBalance**](WalletBalance.md)

### Authorization

[MerchantAPIKeyAuth](../README.md#MerchantAPIKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

