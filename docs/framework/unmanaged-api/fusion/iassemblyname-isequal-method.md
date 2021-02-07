---
description: 'См. Дополнительные сведения о методе IAssemblyName:: Equals'
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
ms.openlocfilehash: f1bb0e26a217354e904ff79b397771d727a7a661
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760695"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Перечисления Fusion](fusion-enumerations.md)
