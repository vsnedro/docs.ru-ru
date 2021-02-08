---
description: 'Дополнительные сведения: Метод IMetaDataEmit:: Сетмесодпропс'
title: Метод IMetaDataEmit::SetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: edecdc14abb386f8fa4cd70535f2b8c012bdc59f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772111"
---
# <a name="imetadataemitsetmethodprops-method"></a>Метод IMetaDataEmit::SetMethodProps

Задает или обновляет компонент, хранящийся по указанному относительному виртуальному адресу метода, определенного в предыдущем вызове [IMetaDataEmit::D ефинемесод](imetadataemit-definemethod-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a>Параметры  

 `md`  
 окне Токен для изменяемого метода.  
  
 `dwMethodFlags`  
 окне Атрибуты элемента.  
  
 `ulCodeRVA`  
 окне Адрес кода.  
  
 `dwImplFlags`  
 окне Флаги реализации для метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
