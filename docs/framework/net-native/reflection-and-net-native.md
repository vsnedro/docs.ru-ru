---
title: Отражение и машинный код .NET
ms.date: 03/30/2017
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
ms.openlocfilehash: c38070ec4afe0a7311133e0ef7b5b24eb2fe4fb5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287843"
---
# <a name="reflection-and-net-native"></a>Отражение и машинный код .NET

В платформа.NET Framework управляемая разработка поддерживает метапрограммирование через интерфейс API отражения. Отражение позволяет проверять объекты в приложении, вызывать методы для объектов, обнаруженные в результате проверки, создавать новые типы во время выполнения и поддерживает множество других сценариев динамического кода. Оно также поддерживает сериализацию и десериализацию, позволяющую сохранять значения полей объекта и восстанавливать их позже. Все эти сценарии требуют использования JIT-компилятора платформы .NET Framework для генерации машинного кода на основе имеющихся метаданных.  
  
 Среда выполнения .NET Native не включает JIT-компилятор. В результате все необходимые машинные коды должны быть созданы заранее. Используется набор эвристических правил, чтобы определить, какой код должен создаваться, но они не могут охватывать все возможные сценарии метапрограммирования.  Таким образом, необходимо предоставить подсказки для этих сценариев метапрограммирования с помощью [директив среды выполнения](runtime-directives-rd-xml-configuration-file-reference.md). Если необходимые метаданные или код реализации недоступны во время выполнения, приложение вызывает исключение [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) или [MissingInteropDataException](missinginteropdataexception-class-net-native.md). Существуют два средства устранения неполадок, создающие соответствующую запись для файла директив среды выполнения, который устраняет исключение.  
  
- [Средство устранения неполадок MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) для типов.  
  
- [Средство устранения неполадок MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) для методов.  
  
> [!NOTE]
> Общие сведения о процессе компиляции машинного кода .NET, обосновывающие необходимость файла директив среды выполнения, см. в разделе [Машинный код .NET и компиляция](net-native-and-compilation.md).  
  
 Кроме того, .NET Native не позволяет отражать закрытых членов библиотеки классов .NET Framework. Например, вызов свойства <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> для извлечения полей типа библиотеки классов платформы .NET Framework возвращает только открытые или защищенные поля.  
  
 В следующих разделах содержится основная и справочная документация, которая может потребоваться для поддержки отражения и сериализации в приложениях:  
  
- [API-интерфейсы, основанные на отражении](apis-that-rely-on-reflection.md)  
  
- [Справочник по API отражения](net-native-reflection-api-reference.md)  
  
- [Ссылка на файл конфигурации директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a>См. также

- [Компиляция приложений с помощью машинного кода .NET](index.md)
- [Машинный код .NET и компиляция](net-native-and-compilation.md)
