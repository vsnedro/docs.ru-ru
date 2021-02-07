---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: Жетаррайлайаут'
title: Метод ICorDebugProcess5::GetArrayLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: c82b296da3a367f5307240225a560af67a56c866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746403"
---
# <a name="icordebugprocess5getarraylayout-method"></a>Метод ICorDebugProcess5::GetArrayLayout

Предоставляет сведения о структуре типов массивов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Параметры  

 `id`  
 окне Токен [COR_TYPEID](cor-typeid-structure.md) , указывающий массив, макет которого требуется.  
  
 `pLayout`  
 заполняет Указатель на структуру [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) , содержащую сведения о макете массива в памяти.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
