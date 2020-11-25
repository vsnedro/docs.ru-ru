---
title: Интерфейс ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 02b1866f2b9e89cdc8c8795f399ecc0c733c7202
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707169"
---
# <a name="isymunmanagedasyncmethod-interface"></a>Интерфейс ISymUnmanagedAsyncMethod

Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a>Методы  

 Этот интерфейс содержит следующие методы:  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAsyncStepInfo](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|См. раздел [метод дефинеасинкстепинфо](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[Метод GetAsyncStepInfoCount](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|См. раздел [метод дефинеасинкстепинфо](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[Метод GetCatchHandlerILOffset](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|См. раздел [метод DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[Метод GetKickoffMethod](isymunmanagedasyncmethod-getkickoffmethod-method.md)|См. раздел [метод DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).|  
|[Метод HasCatchHandlerILOffset](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|См. раздел [метод DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[Метод IsAsyncMethod](isymunmanagedasyncmethod-isasyncmethod-method.md)|Проверяет, имеет ли метод асинхронную информацию.<br /><br /> Если этот метод возвращает значение `FALSE` , то он недопустим для вызова любых других методов в этом интерфейсе. `E_UNEXPECTED`В этом случае они будут возвращаться.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
