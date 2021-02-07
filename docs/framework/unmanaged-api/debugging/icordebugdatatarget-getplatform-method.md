---
description: 'Дополнительные сведения о методе: ICorDebugDataTarget:: WebMethod'
title: Метод ICorDebugDataTarget::GetPlatform
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: dec691238009ad69d2e48d994ac250bfb6641863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764532"
---
# <a name="icordebugdatatargetgetplatform-method"></a>Метод ICorDebugDataTarget::GetPlatform

Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Параметры  

 `pTargetPlatform`  
 заполняет Указатель на перечисление [кордебугплатформенум](cordebugplatform-enumeration.md) , описывающее целевую платформу.  
  
## <a name="remarks"></a>Remarks  

 `CorDebugPlatformEnum`Возвращаемое значение перечисления используется интерфейсом [ICorDebug](icordebug-interface.md) для определения сведений о целевом процессе, таких как размер указателя, макет адресного пространства, набор регистров, формат инструкций, контекстный макет и соглашения о вызовах.  
  
 `pTargetPlatform`Значение может ссылаться на платформу, которая эмулируется для целевого объекта, вместо того, чтобы указывать фактическое используемое оборудование. Например, процесс, выполняемый в среде Windows on Windows (WOW) в 64-разрядном выпуске операционной системы Windows, должен использовать `CORDB_PLATFORM_WINDOWS_X86` значение перечисления [кордебугплатформенум](cordebugplatform-enumeration.md) .  
  
 Этот метод должен быть выполнен. В случае сбоя Целевая платформа будет непригодна для использования. Метод может завершиться ошибкой по следующим причинам:  
  
- Платформа, которая эмулируется для целевого объекта, непригодна для использования.  
  
- Фактическое оборудование на целевой платформе непригодно для использования.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
