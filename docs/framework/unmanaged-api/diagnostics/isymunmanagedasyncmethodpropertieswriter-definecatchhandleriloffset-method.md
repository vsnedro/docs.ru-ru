---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: a37d319a39b959700944f9e111d2945e286c99ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707143"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a>Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset

Задает смещение IL для обработчика catch, созданного компилятором, который создает оболочку для асинхронного метода.  
  
 Смещение IL созданного блока catch используется отладчиком для управления перехватом, как если бы он был непользовательским кодом, даже если он может возникнуть в методе пользовательского кода. В частности, он используется в ответ на событие исключения **катчхандлерфаунд** .  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает `HRESULT`.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md)
