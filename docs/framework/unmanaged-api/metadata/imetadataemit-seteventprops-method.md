---
description: 'Дополнительные сведения: Метод IMetaDataEmit:: SetEventProps'
title: Метод IMetaDataEmit::SetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: 888999bc0f80e82e0d139eecac7152a94104ed7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658130"
---
# <a name="imetadataemitseteventprops-method"></a>Метод IMetaDataEmit::SetEventProps

Задает или обновляет указанную функцию события, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинивент](imetadataemit-defineevent-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ev`  
 окне Токен события.  
  
 `dwEventFlags`  
 окне Флаги событий. Это битовая маска `CorEventAttr` значений.  
  
 `tkEventType`  
 окне Токен для класса событий. Это либо маркер, либо `mdTypeDef` `mdTypeRef` .  
  
 `mdAddOn`  
 окне Метод, используемый для подписки на событие, или значение null.  
  
 `mdRemoveOn`  
 окне Метод, используемый для отмены подписки на событие или значение null.  
  
 `mdFire`  
 окне Метод, используемый (производным классом) для вызова события.  
  
 `rmdOtherMethods[]`  
 окне Массив токенов для других методов, связанных с событием. Последний элемент массива должен быть `mdMethodDefNil` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
