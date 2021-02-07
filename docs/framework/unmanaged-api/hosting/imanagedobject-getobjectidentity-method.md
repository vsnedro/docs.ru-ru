---
description: 'Дополнительные сведения о методе: IManagedObject:: Getobjectidentity-'
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
ms.openlocfilehash: 8929819bbf490680b5f3f1f47b9f3b8e830d57ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671169"
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
  
## <a name="remarks"></a>Remarks  

 Удостоверение управляемого объекта включает идентификатор GUID процесса, идентификатор домена приложения и индекс объекта в классической таблице v-таблицы COM.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IManagedObject](imanagedobject-interface.md)
