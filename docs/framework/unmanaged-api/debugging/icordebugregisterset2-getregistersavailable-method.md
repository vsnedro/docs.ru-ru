---
title: Метод ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378211"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Метод ICorDebugRegisterSet2::GetRegistersAvailable
Возвращает массив байтов, предоставляющий битовую карту доступных регистров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `numChunks`  
 [in] Размер массива `availableRegChunks`.  
  
 `availableRegChunks`  
 заполняет Массив байтов, каждый бит которого соответствует регистру. Если регистр доступен, устанавливается соответствующий бит регистра.  
  
## <a name="remarks"></a>Remarks  
 Значения перечисления CorDebugRegister указывают регистры различных микропроцессоров. Верхние пять битов каждого значения являются индексом в `availableRegChunks` массиве байтов. Младшие три бита каждого значения обозначают битовую точку в индексируемом байте. Учитывая `CorDebugRegister` значение, указывающее конкретный регистр, расположение регистра в маске определяется следующим образом:  
  
1. Извлеките индекс, необходимый для доступа к нужному байту в `availableRegChunks` массиве:  
  
     `CorDebugRegister`значение >> 3  
  
2. Извлечение битовой позиции в индексируемом байте, где нулевой бит является наименее значимым битом:  
  
     `CorDebugRegister`значение & 7  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
