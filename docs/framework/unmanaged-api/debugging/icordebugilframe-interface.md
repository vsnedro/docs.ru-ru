---
title: Интерфейс ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 4f34fdf9a0eeb47e027cc874afee5bd04f5bd9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712395"
---
# <a name="icordebugilframe-interface"></a>Интерфейс ICorDebugILFrame

Представляет кадр стека кода промежуточного языка MSIL. Этот интерфейс является подклассом интерфейса ICorDebugFrame.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](icordebugilframe-cansetip-method.md)|Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.|  
|[Метод EnumerateArguments](icordebugilframe-enumeratearguments-method.md)|Возвращает перечислитель для аргументов в этом кадре.|  
|[Метод EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)|Возвращает перечислитель для локальных переменных в этом кадре.|  
|[Метод GetArgument](icordebugilframe-getargument-method.md)|Возвращает значение указанного аргумента в этом кадре стека MSIL.|  
|[Метод GetIP](icordebugilframe-getip-method.md)|Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.|  
|[Метод GetLocalVariable](icordebugilframe-getlocalvariable-method.md)|Возвращает значение указанной локальной переменной в этом кадре стека MSIL.|  
|[Метод GetStackDepth](icordebugilframe-getstackdepth-method.md)|Не реализован.|  
|[Метод GetStackValue](icordebugilframe-getstackvalue-method.md)|Не реализован.|  
|[Метод SetIP](icordebugilframe-setip-method.md)|Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.|  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugILFrame`Интерфейс является специализированным интерфейсом ICorDebugFrame. Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT. JIT-скомпилированные кадры реализуют `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
