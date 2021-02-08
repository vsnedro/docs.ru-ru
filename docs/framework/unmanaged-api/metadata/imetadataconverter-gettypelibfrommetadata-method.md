---
description: 'Дополнительные сведения о методе: IMetaDataConverter:: Жеттипелибфромметадата'
title: Метод IMetaDataConverter::GetTypeLibFromMetaData
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: 5eecc87f938740366b7938d6ec3d1460ebcfb7eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789272"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>Метод IMetaDataConverter::GetTypeLibFromMetaData

Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами библиотеки и модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `strModule`  
 окне Имя модуля библиотеки типов.  
  
 `strTlbName`  
 окне Имя библиотеки типов.  
  
 `ppITL`  
 заполняет Указатель на расположение, которое получает адрес `ITypeLib` экземпляра, представляющий библиотеку типов.  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataConverter](imetadataconverter-interface.md)
