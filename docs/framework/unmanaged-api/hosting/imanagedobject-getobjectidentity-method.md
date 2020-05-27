---
title: Метод IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
ms.openlocfilehash: 1b40ed8e107d30c22b4ade25d29376b1b74583d1
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842417"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>Метод IManagedObject::GetObjectIdentity
Возвращает удостоверение этого управляемого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBSTRGUID`  
 заполняет Указатель на идентификатор GUID процесса, в котором находится объект.  
  
 `AppDomainID`  
 заполняет Указатель на идентификатор домена приложения объекта.  
  
 `pCCW`  
 заполняет Указатель на индекс объекта в классической таблице v-таблицы COM.  
  
## <a name="remarks"></a>Примечания  
 Удостоверение управляемого объекта включает идентификатор GUID процесса, идентификатор домена приложения и индекс объекта в классической таблице v-таблицы COM.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс IManagedObject](imanagedobject-interface.md)
