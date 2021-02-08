---
description: Дополнительные сведения см. в статье интерфейсы метаданных.
title: Интерфейсы метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 4851fbc93bfa29f1b4b5015c82f05c1b200b9092
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799139"
---
# <a name="metadata-interfaces"></a>Интерфейсы метаданных

В этом разделе описываются неуправляемые интерфейсы, обеспечивающие доступ к метаданным, предоставляемым типами, методами, полями и прочими объектами .NET Framework.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Интерфейс ICeeGen](iceegen-interface.md)  
 Предоставляет методы для динамической компиляции кода.  
  
 [Интерфейс IHostFilter](ihostfilter-interface.md)  
 Предоставляет метод, с помощью которого узел среды выполнения помечает лексемы метаданных для обработки.  
  
 [Интерфейс IMapToken](imaptoken-interface.md)  
 Предоставляет возможности сопоставления между импортированными и выпущенными сигнатурами метаданных.  
  
 [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)  
 Предоставляет методы, поддерживающие модель самоописания, которая используется средой CLR для разрешения и потребления ресурсов.  
  
 [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)  
 Предоставляет методы для доступа и изучения содержимого манифеста сборки.  
  
 [Интерфейс IMetaDataConverter](imetadataconverter-interface.md)  
 Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.  
  
 [Интерфейс IMetaDataDispenser](imetadatadispenser-interface.md)  
 `IMetaDataDispenser` устарел. Взамен рекомендуется использовать `IMetaDataDispenserEx`.  
  
 [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)  
 Предоставляет методы, назначающие области памяти для создания или изменения метаданных.  
  
 [Интерфейс IMetaDataEmit](imetadataemit-interface.md)  
 Предоставляет методы для создания, изменения и хранения метаданных о сборке в текущей заданной области.  
  
 [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)  
 Предоставляет методы для определения и изменения сигнатур метаданных методов и конструкторов с помощью параметров типа <xref:System.Type?displayProperty=nameWithType>.  
  
 [Интерфейс IMetaDataError](imetadataerror-interface.md)  
 Предоставляет механизм обратного вызова для сообщения об ошибках в процессе разрешения сигнатуры метаданных для сборки.  
  
 [Интерфейс IMetaDataFilter](imetadatafilter-interface.md)  
 Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.  
  
 [Интерфейс IMetaDataImport](imetadataimport-interface.md)  
 Предоставляет методы для импорта типов из других сборок и манипуляций с ними.  
  
 [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)  
 Расширяет `IMetaDataImport` для обеспечения возможности работы с универсальными типами.  
  
 [Интерфейс IMetaDataInfo](imetadatainfo-interface.md)  
 Предоставляет метод, который получает сведения о сопоставлении метаданных из файла на диске с памятью.  
  
 [Интерфейс IMetaDataTables](imetadatatables-interface.md)  
 Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.  
  
 [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)  
 Расширяет `IMetaDataTables` для включения методов работы с потоками метаданных.  
  
 [Интерфейс IMetaDataValidate](imetadatavalidate-interface.md)  
 Предоставляет методы, используемые для проверки сигнатур метаданных.  
  
## <a name="related-sections"></a>См. также  

 [Глобальные статические функции метаданных](metadata-global-static-functions.md)  
  
 [Перечисления метаданных](metadata-enumerations.md)  
  
 [Структуры метаданных](metadata-structures.md)  
  
 [Объединения метаданных](metadata-unions.md)
