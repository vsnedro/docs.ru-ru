---
description: 'Дополнительные сведения о методе: ICorDebugArrayValue:: ХасбасеиндиЦиес'
title: Метод ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: b251653004801ff2d312dfb34749c413774ddf40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722962"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a>Метод ICorDebugArrayValue::HasBaseIndicies

Возвращает значение, указывающее, имеют ли измерения данного массива базовый индекс, отличный от нуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbHasBaseIndicies`  
 заполняет Указатель на логическое значение, равное, `true` Если одно или несколько измерений этого `ICorDebugArrayValue` объекта имеют базовый индекс ненулевого значения; в противном случае логическое значение равно `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]
