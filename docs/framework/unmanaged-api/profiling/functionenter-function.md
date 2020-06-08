---
title: Функция FunctionEnter
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: 52870c7446987817ff00b90db26c3265bccdd096
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500732"
---
# <a name="functionenter-function"></a>Функция FunctionEnter
Уведомляет профилировщик о передаче управления в функцию.  
  
> [!NOTE]
> `FunctionEnter`Функция является устаревшей в .NET Framework версии 2,0, и ее использование приведет к снижению производительности. Вместо этого используйте функцию [FunctionEnter2](functionenter2-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Параметры

- `funcID`

  \[in] идентификатор функции, для которой передается элемент управления.

## <a name="remarks"></a>Примечания  
 `FunctionEnter`Функция является обратным вызовом. ее необходимо реализовать. Реализация должна использовать `__declspec` `naked` атрибут класса хранения ().  
  
 Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.  
  
- Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.  
  
 Реализация `FunctionEnter` не должна блокироваться, так как она приведет к задержке сборки мусора. Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора. Если выполняется сборка мусора, среда выполнения будет блокироваться до тех пор, пока не `FunctionEnter` вернет.  
  
 Кроме того, `FunctionEnter` функция не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Функция FunctionEnter2](functionenter2-function.md)
- [Функция FunctionLeave2](functionleave2-function.md)
- [Функция FunctionTailcall2](functiontailcall2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
