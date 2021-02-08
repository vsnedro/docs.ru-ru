---
description: 'Дополнительные сведения о методе: ICorDebugILFrame:: EnumerateArguments'
title: Метод ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 513f931e70a4e914b89f440545cf33ea1cce1fdf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791404"
---
# <a name="icordebugilframeenumeratearguments-method"></a>Метод ICorDebugILFrame::EnumerateArguments

Возвращает перечислитель для аргументов в этом кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppValueEnum`  
 заполняет Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для аргументов в этом кадре.  
  
## <a name="remarks"></a>Remarks  

 `EnumerateArguments` Возвращает перечислитель, который может перечислить аргументы, доступные в кадре вызова, представленном этим объектом ICorDebugILFrame. Список будет содержать аргументы [vararg](/cpp/windows/vararg) (то есть переменное число аргументов), а также аргументы, которые не являются аргументами `vararg` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
