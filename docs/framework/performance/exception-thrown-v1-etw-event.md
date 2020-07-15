---
title: Событие ExceptionThrown_V1 (трассировка событий Windows)
description: Просмотр подробных сведений о событии трассировки событий Windows ExceptionThrown_V1. Такие данные событий, как имена полей, типы данных и описания, предоставляются для вызываемых исключений.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f800a43d0ed2a82bc51a5e3a028b5fa1870df3fb
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309460"
---
# <a name="exception-thrown_v1-etw-event"></a>Событие ExceptionThrown_V1 (трассировка событий Windows)
Это событие захватывает информацию о вызванных исключениях.  
  
 В следующей таблице показаны ключевое слово, в котором вызывается событие, и уровень события. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Level|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Предупреждение (2)|  
  
 В таблице ниже представлены сведения о событии.  
  
|Событие|Идентификатор события|Условие вызова|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Возникло управляемое исключение.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|Тип исключения|win:UnicodeString|Тип исключения, например `System.NullReferenceException`.|  
|Сообщение об исключении|win:UnicodeString|Фактическое сообщение об исключении.|  
|EIPCodeThrow|win:Pointer|Указатель на инструкцию, в которой возникло исключение.|  
|ExceptionHR|win:UInt32|Исключение [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (см. раздел [События трассировки событий Windows в среде CLR](clr-etw-events.md) в документации по Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: Искорруптедстатиксцептион (указывает, что состояние процесса повреждено; см. раздел [обработка исключений поврежденного состояния](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).<br /><br /> 0x10: IsCLSCompliant (исключение, производное от <xref:System.Exception>, является CLS-совместимым; в противном случае такое исключение не является CLS-совместимым).|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
## <a name="see-also"></a>См. также раздел

- [События трассировки событий Windows в среде CLR](clr-etw-events.md)
