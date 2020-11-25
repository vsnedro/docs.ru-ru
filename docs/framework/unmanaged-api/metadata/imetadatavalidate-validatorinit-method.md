---
title: Метод IMetaDataValidate::ValidatorInit
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708560"
---
# <a name="imetadatavalidatevalidatorinit-method"></a>Метод IMetaDataValidate::ValidatorInit

Устанавливает флаг, который указывает тип модуля в текущей области метаданных, и регистрирует указанный метод обратного вызова для ошибок проверки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwModule`  
 окне Значение перечисления [корвалидатормодулетипе](corvalidatormoduletype-enumeration.md) , указывающее тип модуля в текущей области метаданных.  
  
 `pUnk`  
 окне Указатель на экземпляр [IUnknown](/cpp/atl/iunknown) , который служит функцией обратного вызова функции для ошибок проверки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataValidate](imetadatavalidate-interface.md)
