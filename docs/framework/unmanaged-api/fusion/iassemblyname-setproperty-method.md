---
description: 'Дополнительные сведения о методе IAssemblyName:: SetProperty.'
title: Метод IAssemblyName::SetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: cab132c2cd8a0744a2a946a1d8b21f49012c6eac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760694"
---
# <a name="iassemblynamesetproperty-method"></a>Метод IAssemblyName::SetProperty

Задает значение свойства, на которое ссылается указанный идентификатор свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `PropertyId`  
 окне Уникальный идентификатор свойства, значение которого будет задано.  
  
 `pvProperty`  
 окне Значение, для которого задается свойство, на которое ссылается `PropertyId` .  
  
 `cbProperty`  
 окне Размер (в байтах) `pvProperty` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
