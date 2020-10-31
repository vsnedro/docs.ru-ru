---
title: Практическое руководство. Восстановление часовых поясов из внедренного ресурса
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], deserializing
- time zones [.NET], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: 1dd3dff2441ac5e21f3ebf97d58919a7c65d42c5
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063434"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Практическое руководство. Восстановление часовых поясов из внедренного ресурса

В этом разделе описывается восстановление часовых поясов, сохраненных в файле ресурсов. Сведения и инструкции по сохранению часовых поясов см. в статье [как сохранить Часовые пояса во внедренном ресурсе](save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Десериализация объекта TimeZoneInfo из внедренного ресурса

1. Если часовой пояс для извлечения не является пользовательским часовым поясом, попробуйте создать его экземпляр с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метода.

2. Создайте экземпляр <xref:System.Resources.ResourceManager> объекта, передав полное имя внедренного файла ресурсов и ссылку на сборку, содержащую файл ресурсов.

   Если не удается определить полное имя внедренного файла ресурсов, используйте [Ildasm.exe (IL-файл)](../../framework/tools/ildasm-exe-il-disassembler.md) для проверки манифеста сборки. `.mresource`Запись идентифицирует ресурс. В этом примере полное имя ресурса — `SerializeTimeZoneData.SerializedTimeZones` .

   Если файл ресурсов внедрен в ту же сборку, которая содержит код создания экземпляра часового пояса, можно получить ссылку на него, вызвав `static` `Shared` метод (в Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .

3. Если вызов <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метода завершается с ошибкой или если требуется создать пользовательский часовой пояс, извлеките строку, содержащую сериализованный часовой пояс, вызвав <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> метод.

4. Десериализация данных часового пояса путем вызова <xref:System.TimeZoneInfo.FromSerializedString%2A> метода.

## <a name="example"></a>Пример

В следующем примере десериализуется <xref:System.TimeZoneInfo> объект, хранящийся во внедренном XML-файле ресурсов .NET.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Этот код иллюстрирует обработку исключений, чтобы убедиться в <xref:System.TimeZoneInfo> наличии объекта, требуемого для приложения. Сначала он пытается создать экземпляр <xref:System.TimeZoneInfo> объекта, извлекая его из реестра с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метода. Если не удается создать экземпляр часового пояса, код извлекает его из файла внедренных ресурсов.

Поскольку данные для пользовательских часовых поясов (часовые пояса, созданные с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода) не хранятся в реестре, код не вызывает метод <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для создания экземпляра часового пояса для Палмер, Антарктида. Вместо этого он сразу же обращается к внедренному файлу ресурсов для получения строки, содержащей данные часового пояса перед вызовом <xref:System.TimeZoneInfo.FromSerializedString%2A> метода.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для добавления в проект ссылки на System.Windows.Forms.dll и System.Core.dll.

- Для импорта следующих пространств имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также раздел

- [Даты, время и часовые пояса](index.md)
- [Общие сведения о часовых поясах](time-zone-overview.md)
- [Как сохранять Часовые пояса во внедренном ресурсе](save-time-zones-to-an-embedded-resource.md)
