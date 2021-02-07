---
description: Дополнительные сведения о функции _CorExeMain
title: Функция _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: f94197598d01255c35712aa682f83ca9be1fb377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717138"
---
# <a name="_corexemain-function"></a>Функция _CorExeMain

Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Remarks  

 Эта функция вызывается загрузчиком в процессах, созданных из управляемых исполняемых сборок. Для сборок DLL загрузчик вызывает функцию [_CorDllMain](cordllmain-function.md) .  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле изображения.  
  
 В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorExeMain` функция вызывается непрямо через исправление в загрузчике операционной системы. Во всех остальных версиях Windows он вызывается непосредственно загрузчиком операционной системы.  
  
 Дополнительные сведения см. в подразделе "Примечания" статьи [_CorValidateImage](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
