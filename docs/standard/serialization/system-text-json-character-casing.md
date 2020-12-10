---
title: Как включить сопоставление имен свойств без учета регистра с помощью System.Text.Json
description: Узнайте, как в .NET включить сопоставление имен свойств без учета регистра при сериализации в JSON и десериализации из JSON.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599080"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a>Как включить сопоставление имен свойств без учета регистра с помощью System.Text.Json

Из этой статьи вы узнаете, как включить сопоставление имен свойств без учета регистра с помощью пространства имен .`System.Text.Json`

## <a name="case-insensitive-property-matching"></a>Сопоставление свойств без учета регистра

По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между кодом JSON и свойствами целевого объекта. Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.

> [!NOTE]
> В [стандартных параметрах веб-приложений](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) регистр не учитывается.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

Ниже приведен пример JSON с именами свойств в "верблюжьем" стиле. Его можно десериализовать в следующий тип, который содержит имена свойств в регистре Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Создание экземпляров JsonSerializerOptions](system-text-json-configure-options.md)
* [Настройка имен и значений свойств](system-text-json-customize-properties.md)
* [Игнорирование свойств](system-text-json-ignore-properties.md)
* [Применение недействительного кода JSON](system-text-json-invalid-json.md)
* [Обработка переполнения JSON](system-text-json-handle-overflow.md)
* [Сохранение циклических ссылок](system-text-json-preserve-references.md)
* [Неизменяемые типы и непубличные методы доступа](system-text-json-immutability.md)
* [Полиморфная сериализация](system-text-json-polymorphism.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
