---
description: 'Дополнительные сведения о: интерфейс Иенумдефинитионидентити'
title: Интерфейс IEnumDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
ms.openlocfilehash: 1055031c064115410334bbe4b20b48deee7ec4c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800166"
---
# <a name="ienumdefinitionidentity-interface"></a>Интерфейс IEnumDefinitionIdentity

Служит в качестве перечислителя для коллекции `IDefinitionIdentity` объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Возвращает указатель интерфейса на новый `IEnumDefinitionIdentity` объект, содержащий те же элементы, что и этот `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Next`|Возвращает указанное число `IDefinitionIdentity` объектов, начиная с текущей позиции.|  
|`IEnumDefinitionIdentity::Reset`|Перемещает указатель инструкций в начало `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Skip`|Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Интерфейс IDefinitionIdentity](idefinitionidentity-interface.md)
