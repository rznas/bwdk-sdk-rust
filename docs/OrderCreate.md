# OrderCreate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**merchant_order_id** | **String** | شناسه منحصر به فرد این سفارش در سیستم فروشنده | 
**merchant_unique_id** | **String** | شناسه منحصر به فرد برای تأیید اصالت سفارش | 
**main_amount** | Option<**i32**> | مجموع قیمت‌های اولیه تمام کالاها بدون تخفیف (به تومان) | [optional]
**final_amount** | Option<**i32**> | مبلغ نهایی: مبلغ_اصلی - مبلغ_تخفیف + مبلغ_مالیات (به تومان) | [optional]
**total_paid_amount** | Option<**i32**> | مبلغ کل پرداخت شده توسط کاربر: مبلغ_نهایی + هزینه_ارسال (به تومان) | [optional]
**discount_amount** | Option<**i32**> | مبلغ کل تخفیف برای تمام سفارش (به تومان) | [optional]
**tax_amount** | Option<**i32**> | مبلغ کل مالیات برای تمام سفارش (به تومان) | [optional]
**shipping_amount** | Option<**i32**> | هزینه ارسال برای سفارش (به تومان) | [optional]
**loyalty_amount** | Option<**i32**> | مبلغ تخفیف باشگاه مشتریان/پاداش (به تومان) | [optional]
**callback_url** | **String** | آدرس وب‌هوک برای دریافت اطلاع رسانی وضعیت پرداخت | 
**destination_address** | Option<**serde_json::Value**> |  | [readonly]
**items** | [**Vec<models::OrderItemCreate>**](OrderItemCreate.md) |  | 
**merchant** | Option<**i32**> | مقدار توسط سیستم جایگذاری می شود | [optional]
**source_address** | Option<**serde_json::Value**> | مقدار توسط سیستم جایگذاری می شود | [optional]
**user** | Option<**i32**> |  | [readonly]
**reservation_expired_at** | Option<**i32**> | مهلت پرداخت (به عنوان Unix timestamp) قبل از اتمام سفارش | [optional]
**reference_code** | **String** | کد مرجع منحصر به فرد برای پیگیری سفارش مشتری (فرمت: BD-XXXXXXXX) | [readonly]
**preparation_time** | Option<**i32**> | زمان آمادهسازی سفارش (به روز) | [optional][default to 2]
**weight** | Option<**f64**> | وزن کل سفارش (بر حسب گرم) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


