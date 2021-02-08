---
description: Дополнительные сведения о функции Коишутдовнком
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
ms.openlocfilehash: 4f1ac8107c9a121ebf52ef21a5f2c9006880914f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799867"
---
# <a name="coeeshutdowncom-function"></a>Функция CoEEShutDownCOM

Заставляет общеязыковую среду выполнения (CLR) освобождать все указатели интерфейсов, содержащиеся внутри вызываемых оболочек времени выполнения (RCW). Это приведет к освобождению всех кэшей RCW. Эта глобальная функция является устаревшей в платформа .NET Framework 4. Вместо этого используйте точку входа для конкретной среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Remarks  

 `CoEEShutDownCOM`Функция сначала освобождает все вызываемые оболочки RCW во всех контекстах и во всех кэшах, а затем удаляет все уведомления о разрыве, существующие в программе установки. Выгрузка библиотек DLL не выполняется.  
  
> [!CAUTION]
> Эта функция влияет на все среды выполнения, загруженные в процесс.  
  
 Начиная с платформа .NET Framework 4, вызовите точку входа для этой функции в конкретной среде выполнения, которую необходимо изменить. Чтобы получить точку входа, вызовите метод [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) и укажите "коишутдовнком".  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
