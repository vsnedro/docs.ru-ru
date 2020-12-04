---
title: События среды выполнения взаимодействия
description: См. раздел события среды выполнения .NET, собирающие диагностическую информацию, относящуюся к взаимодействию.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Interop events (CoreCLR)
- ETW, EventPipe, LTTng interop events (CoreCLR)
ms.openlocfilehash: 5635fb55b3a6ffa3f5611da80cdb2909e226e2ea
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594047"
---
# <a name="net-runtime-interop-events"></a>События взаимодействия среды выполнения .NET

Эти события времени выполнения захватывают сведения о создании заглушек на стандартном промежуточном языке (CIL). Дополнительные сведения об использовании этих событий в целях диагностики см. в разделе [ведение журнала и трассировка приложений .NET](../../core/diagnostics/logging-tracing.md) .

## <a name="ilstubgenerated-event"></a>Событие событие ilstubgenerated

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`InteropKeyword` (0x2000)|Информационный (4)|
  
|Событие|Идентификатор события|Условие вызова|
|-----------|--------------|-----------------|
|`ILStubGenerated`|88|Создается заглушка IL.|

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt16`|Идентификатор модуля.|
|`StubMethodID`|`win:UInt64`|Идентификатор метода-заглушки.|
|`StubFlags`|`win:UInt32`|Флаги для заглушки:<br /><br /> `0x1` — Обратная взаимодействие.<br /><br /> `0x2` — COM-взаимодействие.<br /><br /> `0x4` -Заглушка, созданная NGen.exe.<br /><br /> `0x8` Получить.<br /><br /> `0x10` -Переменный аргумент.<br /><br /> `0x20` — Неуправляемый вызываемый метод.<br /><br /> `0x40` -Маршалирование структуры|
|`ManagedInteropMethodToken`|`win:UInt32`|Токен управляемого метода взаимодействия.|
|`ManagedInteropMethodNameSpace`|`win:UnicodeString`|Пространство имен и включающий тип управляемого метода взаимодействия.|
|`ManagedInteropMethodName`|`win:UnicodeString`|Имя управляемого метода взаимодействия.|
|`ManagedInteropMethodSignature`|`win:UnicodeString`|Сигнатура управляемого метода взаимодействия.|
|`NativeMethodSignature`|`win:UnicodeString`|Сигнатура неуправляемого метода.|
|`StubMethodSignature`|`win:UnicodeString`|Сигнатура метода-заглушки.|
|`StubMethodILCode`|`win:UnicodeString`|Код общего промежуточного языка (CIL) для метода-заглушки.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|
