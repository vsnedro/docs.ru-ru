---
title: Метод IAssemblyName::IsEqual
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: 0fabf8159c2626d4e1716e3be60baaf1ec834032
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712993"
---
# <a name="iassemblynameisequal-method"></a>Метод IAssemblyName::IsEqual

Определяет, равен ли указанный объект [IAssemblyName](iassemblyname-interface.md) этому объекту `IAssemblyName` на основе указанных флагов сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pName`  
 окне `IAssemblyName` Объект, с которым необходимо выполнить сравнение `IAssemblyName` .  
  
 `dwCmpFlags`  
 окне Побитовое сочетание значений [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) , влияющих на сравнение.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Перечисления Fusion](fusion-enumerations.md)
