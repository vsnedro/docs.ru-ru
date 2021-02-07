---
description: Дополнительные сведения о функции Жетидентитяусорити
title: Функция GetIdentityAuthority
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: 5126aa9b319af41f7ecd30845a9f74ba69016588
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761002"
---
# <a name="getidentityauthority-function"></a>Функция GetIdentityAuthority

Возвращает указатель на экземпляр [IIdentityAuthority](iidentityauthority-interface.md) , который управляет ключами для объектов кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `ppIIdentityAuthority`  
 заполняет Возвращаемый `IIdentityAuthority` указатель.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IIdentityAuthority](iidentityauthority-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
