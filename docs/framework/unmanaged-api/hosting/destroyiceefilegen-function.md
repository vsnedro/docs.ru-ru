---
description: Дополнительные сведения о функции Дестройицеефилежен
title: Функция DestroyICeeFileGen
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: 14ae990999247b90f16b10115dea3408b965a04a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785657"
---
# <a name="destroyiceefilegen-function"></a>Функция DestroyICeeFileGen

Уничтожает объект [ицеефилежен](iceefilegen-class.md) .  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ceeFileGen`  
 окне `ICeeFileGen` Объект для уничтожения.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает стандартные коды ошибок COM.  
  
## <a name="remarks"></a>Remarks  

 `DestroyICeeFileGen` уничтожает `ICeeFileGen` объект, созданный функцией [креатеицеефилежен](createiceefilegen-function.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Ицеефилежен. h  
  
 **Библиотека:** MSCorPE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
