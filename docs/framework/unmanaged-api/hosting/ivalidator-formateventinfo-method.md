---
title: Метод IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: c5c89e0eda6e93e34775c00d5ec8fb4ff0940707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701020"
---
# <a name="ivalidatorformateventinfo-method"></a>Метод IValidator::FormatEventInfo

Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `hVECode`  
 окне Значение HRESULT, которое было передано обработчику ошибок проверки.  
  
 `Context`  
 окне `VEContext` Экземпляр, содержащий контекстные сведения об ошибке проверки.  
  
 `msg`  
 [вход, выход] Строка, содержащая возвращенное сообщение об ошибке.  
  
 `ulMaxLength`  
 окне Максимальная длина сообщения об ошибке.  
  
 `psa`  
 окне Защищенный массив, содержащий дополнительные параметры, описывающие ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
