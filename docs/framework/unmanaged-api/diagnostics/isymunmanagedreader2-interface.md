---
title: Интерфейс ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709080"
---
# <a name="isymunmanagedreader2-interface"></a>Интерфейс ISymUnmanagedReader2

Представляет средство чтения символов, которое предоставляет доступ к документам, методам и переменным в хранилище символов. Этот интерфейс расширяет интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetMethodByVersionPreRemap](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Получение метода чтения символов по заданному маркеру метода и номеру версии "изменить и продолжить".|  
|[Метод GetMethodsInDocument](isymunmanagedreader2-getmethodsindocument-method.md)|Возвращает каждый метод, имеющий сведения о строке в указанном документе.|  
|[Метод GetSymAttributePreRemap](isymunmanagedreader2-getsymattributepreremap-method.md)|Возвращает настраиваемый атрибут на основе его имени.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
