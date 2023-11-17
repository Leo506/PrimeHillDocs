# Конфигурация

## Список параметров


| Параметр                       | Предназначение                                                                                                                                                                                                                   |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PrimeHilApiAddress             | Url до API PrimeHill-а. По умолчанию: https://iiko-api.p-h.app. Для Windows 7 используется http://iiko-api.p-h.app                                                                                                               |
| Token                          | Токен для работы с обычными заказами. Выпускается в личном кабинете PrimeHill, в Настройки -> Точки продаж                                                                                                                       |
| DeliveryToken                  | Токен для работы с доставочными заказами. Выпускается в личном кабинете PrimeHill, в Настройки -> Точки продаж                                                                                                                   |
| PickupToken                    | Токен для работы с заказами на самовывоз. Выпускается в личном кабинете PrimeHill, в Настройки -> Точки продаж                                                                                                                   |
| PluginHostPort                 | Порт, на котором запускается плагин                                                                                                                                                                                              |
| DecimalPlacesToRoundOff        | Количество знаков после запятой. Используется для округления сумм списания                                                                                                                                                       |
| AdminPin                       | Пин-код администратора. Используется при чекине гостя с экрана кассы ([сценарий](Scenarios.md#checkin_from_payment_screen_in_bill))                                                                                              |
| AnonymousCardEnabled           | Определяет, могут ли заказы закрываться без гостя. **true** - плагин будет закрывать заказы на PrimeHill-е независимо от того,  есть или нет гость в заказе. **false** - плагин не будет закрывать заказ, если он не имеет гостя |
| PrintGuestInfoOnCashCheque     | Определяет, нужно ли печатать информацию о госте на чеке. **true** - печатать. **false** - не печатать                                                                                                                           |
| ClientsImportIntervalInMinutes | Временной интервал в минутах между импортами гостей из PrimeHill-а в БРД ([сценарий](Scenarios.md#guests_import))                                                                                                                |
| DeliveriesDiscountId           | Id скидки, которая используется для конвертации скидки в бонусный платеж для доставочных заказов ([сценарий](Scenarios.md#discount_to_payment))                                                                                  |
| AllowManualCardEntry           | Определяет, можно ли добавлять гостя с экрана кассы. **true** - можно. **false** - нельзя                                                                                                                                        |
| Organizations                  | Список организаций в заведении и их мест приготовления блюд. Используется для разделения на 2ФР ([сценарий](Scenarios.md#2fr))                                                                                                   |
| GiftDishesSKUs                 | Список артикулов товаров, которые используются для пополнения депозита ([сценарий](Scenarios.md#adding_deposit))                                                                                                                 |


## Актуальная схема конфига
```json
{
  "PrimeHillApiAddress": "https://iiko-api.p-h.app",
  "Token": "",
  "DeliveryToken": "",
  "PickupToken": "",
  "PluginHostPort": 8115,
  "DecimalPlacesToRoundOff": 3,
  "AdminPin": "",
  "AnonymousCardEnabled": true,
  "PrintGuestInfoOnCashCheque": true,
  "ClientsImportIntervalInMinutes": 30,
  "DeliveriesDiscountId": "00000000-0000-0000-0000-000000000000",
  "AllowManualCardEntry": true,
  "Organizations": [
    {
      "Name": "ИП",
      "CookingSections": [
        "Кухня"
      ]
    },
    {
      "Name": "ООО",
      "CookingSections": [
        "Бар"
      ]
    }
  ],
  "GiftDishesSKUs": [
    "00052"
  ]
}
```