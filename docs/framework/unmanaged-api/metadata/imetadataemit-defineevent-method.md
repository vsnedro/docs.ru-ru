---
title: Метод IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 3c03497f48b8199da545d796637e5f8a5c532362
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675703"
---
# <a name="imetadataemitdefineevent-method"></a>Метод IMetaDataEmit::DefineEvent

Создает определение для события с указанной сигнатурой метаданных и получает маркер для этого определения события.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне Токен для целевого класса или интерфейса. Это либо токен, `mdTypeDef` либо `mdTypeDefNil` .  
  
 `szEvent`  
 [in] Имя события.  
  
 `dwEventFlags`  
 окне Флаги событий.  
  
 `tkEventType`  
 окне Токен для класса событий. Это `mdTypeDef` , `mdTypeRef` или, или `mdTokenNil` маркер.  
  
 `mdAddOn`  
 окне Метод, используемый для подписки на событие, или значение null.  
  
 `mdRemoveOn`  
 окне Метод, используемый для отмены подписки на событие или значение null.  
  
 `mdFire`  
 окне Метод, используемый (производным классом) для вызова события.  
  
 `rmdOtherMethods[]`  
 окне Массив токенов для других методов, связанных с событием. Массив завершается `mdMethodDefNil` токеном.  
  
 `pmdEvent`  
 заполняет Маркер метаданных, назначенный событию.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
