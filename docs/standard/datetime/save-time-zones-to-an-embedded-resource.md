---
description: Дополнительные сведения о том, как сохранять Часовые пояса во внедренном ресурсе.
title: Практическое руководство. Сохранение часовых поясов во внедренном ресурсе
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], saving
- time zone objects [.NET], serializing
- time zone objects [.NET], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
ms.openlocfilehash: 4f1455ffa790652d2dad605a0eb71fb81a05326d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702474"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Практическое руководство. Сохранение часовых поясов во внедренном ресурсе

Для приложения, поддерживающего Часовые пояса, часто требуется наличие определенного часового пояса. Однако, поскольку доступность отдельных <xref:System.TimeZoneInfo> объектов зависит от информации, хранящейся в реестре локальной системы, даже нестандартно доступные часовые пояса могут отсутствовать. Кроме того, сведения о настраиваемых часовых поясах, создаваемых с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода, не сохраняются с другими сведениями о часовом поясе в реестре. Чтобы обеспечить доступность этих часовых поясов при необходимости, их можно сохранить путем их сериализации и последующего восстановления путем их десериализации.

Как правило, сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения, поддерживающего часовой пояс. В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, данные часового пояса могут быть сериализованы как часть программы установки или установки (например, когда данные хранятся в ключе реестра) или как часть служебной программы, выполняемой перед компиляцией окончательного приложения (например, когда сериализованные данные хранятся в файле ресурсов .NET XML (RESX)).

Помимо файла ресурсов, компилируемого с приложением, для сведений о часовом поясе можно использовать несколько других хранилищ данных. Вот некоторые из них.

- Реестр. Обратите внимание, что приложение должно использовать подразделы собственного ключа приложения для хранения пользовательских данных часового пояса вместо использования подразделов HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

- Файлы конфигурации.

- Другие системные файлы.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Сохранение часового пояса путем его сериализации в RESX-файл

1. Получение существующего часового пояса или создание нового часового пояса.

   Чтобы получить существующий часовой пояс, см. раздел [как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу](access-utc-and-local.md) и [как создать объект TimeZoneInfo](instantiate-time-zone-info.md).

   Чтобы создать новый часовой пояс, вызовите одну из перегрузок <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода. Дополнительные сведения см. в статьях [как создавать Часовые пояса без правил коррекции](create-time-zones-without-adjustment-rules.md) и [как создавать Часовые пояса с правилами коррекции](create-time-zones-with-adjustment-rules.md).

2. Вызовите <xref:System.TimeZoneInfo.ToSerializedString%2A> метод, чтобы создать строку, содержащую данные часового пояса.

3. Создайте экземпляр <xref:System.IO.StreamWriter> объекта, указав имя и, при необходимости, путь к RESX-файлу <xref:System.IO.StreamWriter> конструктора класса.

4. Создайте экземпляр <xref:System.Resources.ResXResourceWriter> объекта, передав <xref:System.IO.StreamWriter> объект в <xref:System.Resources.ResXResourceWriter> конструктор класса.

5. Передайте сериализованную строку часового пояса в <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> метод.

6. Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> .

7. Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> .

8. Закройте <xref:System.IO.StreamWriter> объект, вызвав его <xref:System.IO.StreamWriter.Close%2A> метод.

9. Добавьте созданный RESX файл в проект приложения Visual Studio.

10. С помощью окна **Свойства** в Visual Studio убедитесь, что для свойства **действие сборки** RESX-файла задано значение **внедренный ресурс**.

## <a name="example"></a>Пример

В следующем примере сериализуется <xref:System.TimeZoneInfo> объект, представляющий центральное стандартное время, и <xref:System.TimeZoneInfo> объект, представляющий Палмер станцию, Антарктида время в файл ресурсов .NET XML с именем сериализедтимезонес. resx. Центральное стандартное время обычно определяется в реестре; Палмер станция, Антарктида — настраиваемый часовой пояс.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

В этом примере сериализуются <xref:System.TimeZoneInfo> объекты, чтобы они были доступны в файле ресурсов во время компиляции.

Поскольку <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> метод добавляет полные данные заголовка в файл ресурсов XML .NET, он не может использоваться для добавления ресурсов в существующий файл. Этот пример обрабатывает это путем проверки файла Сериализедтимезонес. resx и (если он существует), сохраняя все ресурсы, кроме двух сериализованных часовых поясов, в универсальный <xref:System.Collections.Generic.Dictionary%602> объект. После этого существующий файл удаляется, а существующие ресурсы добавляются в новый файл Сериализедтимезонес. resx. Сериализованные данные часового пояса также добавляются в этот файл.

Поля ключа (или **имени**) ресурсов не должны содержать пробелы. <xref:System.String.Replace%28System.String%2CSystem.String%29>Метод вызывается для удаления всех внедренных пробелов в идентификаторах часовых поясов до их назначения в файл ресурсов.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для добавления в проект ссылки на System.Windows.Forms.dll и System.Core.dll.

- Для импорта следующих пространств имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](index.md)
- [Общие сведения о часовых поясах](time-zone-overview.md)
- [Как восстановить Часовые пояса из внедренного ресурса](restore-time-zones-from-an-embedded-resource.md)
