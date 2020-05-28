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
ms.openlocfilehash: 7babd0a90b9882acb03b6360753f55c57a399b9e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005639"
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
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
