---
description: Дополнительные сведения о функции Креатеицеефилежен
title: Функция CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 10aefaad4dd1173e4ef55f727371bab508e2d40c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716936"
---
# <a name="createiceefilegen-function"></a>Функция CreateICeeFileGen

Создает объект [ицеефилежен](iceefilegen-class.md) .  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ceeFileGen`  
 заполняет Указатель на адрес нового `ICeeFileGen` объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает стандартные коды ошибок COM.  
  
## <a name="remarks"></a>Remarks  

 `ICeeFileGen`Объект используется для создания переносимых исполняемых (PE) файлов среды CLR.  
  
 Вызовите функцию [дестройицеефилежен](destroyiceefilegen-function.md) , чтобы уничтожить `ICeeFileGen` объект после завершения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Ицеефилежен. h  
  
 **Библиотека:** MSCorPE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
