---
title: Метод IAssemblyName::GetName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 58b8b83ce1db9338612cbaa01a0db0862cf1054e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727904"
---
# <a name="iassemblynamegetname-method"></a>Метод IAssemblyName::GetName

Возвращает простое незашифрованное имя сборки, на которую ссылается этот объект [IAssemblyName](iassemblyname-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `lpcwBuffer`  
 [вход, выход] Размер `pwzName` в расширенных символах, включая символ конца null.  
  
 `pwzName`  
 заполняет Буфер для хранения имени сборки, на которую указывает ссылка.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
