---
title: Функция CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 774704698f92d546d6bafa61c65d18d083c65f89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716763"
---
# <a name="coeeshutdowncom-function"></a>Функция CoEEShutDownCOM

Заставляет общеязыковую среду выполнения (CLR) освобождать все указатели интерфейсов, содержащиеся внутри вызываемых оболочек времени выполнения (RCW). Это приведет к освобождению всех кэшей RCW. Эта глобальная функция является устаревшей в .NET Framework 4. Вместо этого используйте точку входа для конкретной среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Remarks  

 `CoEEShutDownCOM`Функция сначала освобождает все вызываемые оболочки RCW во всех контекстах и во всех кэшах, а затем удаляет все уведомления о разрыве, существующие в программе установки. Выгрузка библиотек DLL не выполняется.  
  
> [!CAUTION]
> Эта функция влияет на все среды выполнения, загруженные в процесс.  
  
 Начиная с .NET Framework 4, вызовите точку входа для этой функции в конкретной среде выполнения, которую необходимо изменить. Чтобы получить точку входа, вызовите метод [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) и укажите "коишутдовнком".  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
