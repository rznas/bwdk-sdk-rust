# ShippingMethod

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | [readonly]
**name** | **String** | نام روش/گزینه بسته‌بندی | 
**description** | Option<**String**> | شناسه روش ارسال برای استفاده در سفارش | [optional]
**shipping_type** | Option<[**models::ShippingTypeEnum**](ShippingTypeEnum.md)> | شناسه وضعیت ارسال از دیجی اکسپرس  * `1` - سایر * `2` - دیجی اکسپرس | [optional]
**get_shipping_type_display** | **String** |  | [readonly]
**shipping_type_display** | **String** |  | [readonly]
**cost** | Option<**i32**> | هزینه ارسال برای منطقه اصلی (مثلاً تهران) به تومان | [optional]
**secondary_cost** | Option<**i32**> | هزینه ارسال برای مناطق دیگر به تومان | [optional]
**minimum_time_sending** | Option<**i32**> | حداقل تعداد روز از تاریخ سفارش تا تحویل | [optional]
**maximum_time_sending** | Option<**i32**> | Maximum number of days from order date to delivery | [optional]
**delivery_time_display** | **String** |  | [readonly]
**delivery_time_range_display** | [**models::DeliveryTimeRangeDisplay**](DeliveryTimeRangeDisplay.md) |  | [readonly]
**inventory_address** | [**models::BusinessAddress**](BusinessAddress.md) |  | [readonly]
**is_pay_at_destination** | Option<**bool**> | آیا روش ارسال پرداخت در مقصد است | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


