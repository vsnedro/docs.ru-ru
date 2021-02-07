---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: GetTypeLayout'
title: Метод ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: d4496fa832b048dfc0bbe792aeb8fdcd460f5158
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746286"
---
# <a name="icordebugprocess5gettypelayout-method"></a>Метод ICorDebugProcess5::GetTypeLayout

Возвращает сведения о макете объекта в памяти на основе его идентификатора типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Параметры  

 `id`  
 окне Токен [COR_TYPEID](cor-typeid-structure.md) , указывающий тип, макет которого требуется.  
  
 `pLayout`  
 заполняет Указатель на структуру [COR_TYPE_LAYOUT](cor-type-layout-structure.md) , содержащую сведения о макете объекта в памяти.  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugProcess5::GetTypeLayout`Метод предоставляет сведения об объекте на основе его [COR_TYPEID](cor-typeid-structure.md), который возвращается несколькими другими методами [метод ICorDebugProcess5](icordebugprocess5-interface.md) . Сведения предоставляются структурой [COR_TYPE_LAYOUT](cor-type-layout-structure.md) , которая заполняется методом.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структура COR_TYPE_LAYOUT](cor-type-layout-structure.md)
- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
