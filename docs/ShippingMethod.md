# ShippingMethod

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | [readonly]
**name** | **String** | نام روش ارسال | 
**description** | Option<**String**> | توضیحات روش ارسال و جزئیات تحویل آن | [optional]
**shipping_type** | Option<[**models::ShippingTypeEnum**](ShippingTypeEnum.md)> | نوع روش ارسال: عادی یا دیجی اکسپرس  * `1` - سایر * `2` - دیجی اکسپرس | [optional]
**get_shipping_type_display** | **String** |  | [readonly]
**shipping_type_display** | **String** |  | [readonly]
**cost** | Option<**i32**> | هزینه ارسال برای منطقه اولیه (مثلاً تهران) به تومان | [optional]
**secondary_cost** | Option<**i32**> | هزینه ارسال برای مناطق دیگر به تومان | [optional]
**minimum_time_sending** | Option<**i32**> | حداقل تعداد روزها از تاریخ سفارش تا تحویل | [optional]
**maximum_time_sending** | Option<**i32**> | حداکثر تعداد روزها از تاریخ سفارش تا تحویل | [optional]
**delivery_time_display** | **String** |  | [readonly]
**delivery_time_range_display** | [**models::DeliveryTimeRangeDisplay**](DeliveryTimeRangeDisplay.md) |  | [readonly]
**inventory_address** | [**models::BusinessAddress**](BusinessAddress.md) |  | [readonly]
**is_pay_at_destination** | Option<**bool**> | Whether the shipping method is pay at destination | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


