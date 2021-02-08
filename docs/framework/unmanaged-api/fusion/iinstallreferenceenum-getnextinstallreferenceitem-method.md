---
description: 'Дополнительные сведения о методе: IInstallReferenceEnum:: Жетнекстинсталлреференцеитем'
title: Метод IInstallReferenceEnum::GetNextInstallReferenceItem
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
ms.openlocfilehash: d410407fe16a46b45786ff74f694aaa8931be542
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800127"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a>Метод IInstallReferenceEnum::GetNextInstallReferenceItem

Возвращает указатель на следующий объект [IInstallReferenceItem](iinstallreferenceitem-interface.md) , содержащийся в этом объекте [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppRefItem`  
 заполняет Возвращаемый `IInstallReferenceItem` указатель.  
  
 `dwFlags`  
 окне Зарезервировано для будущего расширения. `dwFlags` значение должно быть равно 0 (нулю).  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IInstallReferenceItem](iinstallreferenceitem-interface.md)
- [Интерфейс IInstallReferenceEnum](iinstallreferenceenum-interface.md)
