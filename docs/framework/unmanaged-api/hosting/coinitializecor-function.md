---
description: Дополнительные сведения о функции Коинитиализекор
title: Функция CoInitializeCor
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: e1db9914cce8a92cecf78123a2e247d75ec74acf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799854"
---
# <a name="coinitializecor-function"></a>Функция CoInitializeCor

`CoInitializeCor` устарел.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Remarks  

 Чтобы инициализировать среду CLR, используйте либо [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , либо [корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** COR. h  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
