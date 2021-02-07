---
description: 'Дополнительные сведения о методе: ICorDebugReferenceValue::D ереференце'
title: Метод ICorDebugReferenceValue::Dereference
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: af225f746a9c67a90a7ad73046cd03401e4ba735
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691111"
---
# <a name="icordebugreferencevaluedereference-method"></a>Метод ICorDebugReferenceValue::Dereference

Возвращает объект, на который указывает ссылка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppValue`  
 заполняет Указатель на адрес ICorDebugValue, представляющий объект, на который указывает объект ICorDebugReferenceValue.  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugValue`Объект допустим только в том случае, если его ссылка еще не была отключена.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
