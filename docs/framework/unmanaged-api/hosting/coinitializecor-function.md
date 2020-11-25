---
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
ms.openlocfilehash: 9d077d5c5a414568b5643cad0171e101d7bb06f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731713"
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
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
