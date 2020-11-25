---
title: Метод IInstallReferenceItem::GetReference
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
ms.openlocfilehash: 14286970a4f7093d72b47b780ea880f5ccb1bca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721079"
---
# <a name="iinstallreferenceitemgetreference-method"></a>Метод IInstallReferenceItem::GetReference

Возвращает указатель на структуру [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) , представленную этим объектом [IInstallReferenceItem](iinstallreferenceitem-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppRefData`  
 заполняет Возвращаемый `FUSION_INSTALL_REFERENCE` указатель.  
  
 `dwFlags`  
 окне Зарезервировано для будущего расширения. `dwFlags` значение должно быть равно 0 (нулю).  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IInstallReferenceItem](iinstallreferenceitem-interface.md)
- [Структура FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)
