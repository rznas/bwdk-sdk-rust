# OrderDetail

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | [readonly]
**created_at** | **String** |  | [readonly]
**order_uuid** | **uuid::Uuid** |  | [readonly]
**reservation_expired_at** | Option<**i32**> | Unix timestamp تا زمانی که سفارش برای پرداخت رزرو شده است | [readonly]
**merchant_order_id** | **String** | شناسه منحصر به فرد سفارش در سیستم فروشنده | [readonly]
**status** | [**models::OrderStatusEnum**](OrderStatusEnum.md) |  | [readonly]
**status_display** | **String** |  | [readonly]
**main_amount** | **i32** | مجموع قیمت اولیه تمام کالاهای سفارش بدون تخفیف (به تومان) | [readonly]
**final_amount** | **i32** | قیمت نهایی قابل پرداخت توسط مشتری: مبلغ_اصلی - مبلغ_تخفیف + مبلغ_مالیات (به تومان) | [readonly]
**total_paid_amount** | **i32** | مبلغ کل پرداخت شده توسط کاربر: مبلغ_نهایی + هزینه_ارسال (به تومان) | [readonly]
**discount_amount** | **i32** | مبلغ کل تخفیف اعمال شده بر سفارش (به تومان) | [readonly]
**tax_amount** | **i32** | مبلغ کل مالیات برای سفارش (به تومان) | [readonly]
**shipping_amount** | **i32** | هزینه ارسال برای سفارش (به تومان) | [readonly]
**loyalty_amount** | **i32** | مقدار تخفیف از برنامه باشگاه مشتریان/پاداش (به تومان) | [readonly]
**callback_url** | **String** | آدرسی برای دریافت اطلاع رسانی وضعیت پرداخت پس از تکمیل سفارش | [readonly]
**merchant** | [**models::Merchant**](Merchant.md) |  | 
**items** | [**Vec<models::OrderItemCreate>**](OrderItemCreate.md) |  | 
**source_address** | Option<**serde_json::Value**> |  | [readonly]
**destination_address** | Option<**serde_json::Value**> |  | [readonly]
**selected_shipping_method** | [**models::ShippingMethod**](ShippingMethod.md) |  | [readonly]
**shipping_selected_at** | Option<**String**> |  | [readonly]
**address_selected_at** | Option<**String**> |  | [readonly]
**packing_amount** | **i32** | هزینه روش بسته‌بندی انتخاب‌شده (به تومان) | [readonly]
**packing_selected_at** | Option<**String**> |  | [readonly]
**selected_packing** | [**models::Packing**](Packing.md) |  | [readonly]
**can_select_packing** | **bool** |  | [readonly]
**can_select_shipping** | **bool** |  | [readonly]
**can_select_address** | **bool** |  | [readonly]
**can_proceed_to_payment** | **bool** |  | [readonly]
**is_paid** | **bool** |  | [readonly]
**user** | [**models::OrderUser**](OrderUser.md) |  | [readonly]
**payment** | [**models::PaymentOrder**](PaymentOrder.md) |  | [readonly]
**preparation_time** | **i32** | Preparation time for the order (in days) | [readonly]
**weight** | **f64** | Total weight of the order (in grams) | [readonly]
**selected_shipping_data** | **std::collections::HashMap<String, serde_json::Value>** |  | [readonly]
**reference_code** | **String** | کد مرجع یکتا برای پیگیری سفارش مشتری (قالب: BD-XXXXXXXX) | [readonly]
**promotion_discount_amount** | **f64** |  | [readonly]
**promotion_data** | **std::collections::HashMap<String, serde_json::Value>** |  | [readonly]
**digipay_markup_amount** | **i32** | Markup amount for the order (in Tomans) | [readonly]
**markup_commission_percentage** | **i32** | Markup commission percentage for the order (in percent) | [readonly]
**previous_status** | Option<[**models::OrderStatusEnum**](OrderStatusEnum.md)> |  | [readonly]
**previous_status_display** | **String** |  | [readonly]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


