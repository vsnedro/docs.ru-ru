---
title: Функция CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 707e182e62f4a7b7b813e6b288c6825b0d3d2eab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731759"
---
# <a name="coinitializeee-function"></a>Функция CoInitializeEE

Гарантирует, что подсистема выполнения среды CLR загружается в процесс. Эта функция является устаревшей в .NET Framework 4. Используйте вместо этого метод [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `fFlags`  
 окне Одна из констант перечисления [коинитии](../metadata/coinitiee-enumeration.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает стандартные коды ошибок COM, определенные в файле Winerror. h, и значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Подсистема выполнения успешно загружена.|  
|S_FALSE|Подсистема выполнения уже загружена.|  
|E_FAIL|Не удалось загрузить подсистему выполнения.|  
  
## <a name="remarks"></a>Комментарии  

 Этот метод загружает подсистему выполнения, если он не был загружен ранее.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
