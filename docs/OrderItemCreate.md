# OrderItemCreate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **String** | نام کامل محصول شامل تمام مشخصات | 
**primary_amount** | Option<**i32**> | قیمت اولیه برای هر واحد بدون تخفیف (به تومان) | [optional]
**amount** | Option<**i32**> | قیمت نهایی برای تمام واحدها بعد از تخفیف (به تومان) | [optional]
**count** | **i32** | تعداد واحدهای این کالا در سفارش | 
**discount_amount** | Option<**i32**> | مبلغ کل تخفیف برای این کالا (به تومان) | [optional]
**tax_amount** | Option<**i32**> | مبلغ کل مالیات برای این کالا (به تومان) | [optional]
**image_link** | Option<**String**> | آدرس تصویر محصول | [optional]
**options** | [**Vec<models::Option>**](Option.md) |  | 
**preparation_time** | Option<**i32**> | Preparation time for the item (in days) | [optional][default to 2]
**weight** | Option<**f64**> | Weight of the item (in grams) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


