---
description: 'Дополнительные сведения о методе: ICLRDataTarget:: GetImageBase'
title: Метод ICLRDataTarget::GetImageBase
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: 34e8341b219aaa184b4894c631f854e0a31921d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794875"
---
# <a name="iclrdatatargetgetimagebase-method"></a>Метод ICLRDataTarget::GetImageBase

Возвращает адрес базовой памяти указанного образа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `imagePath`  
 окне Имя файла образа, включая его путь.  
  
 `baseAddress`  
 заполняет Указатель на CLRDATA_ADDRESS, в котором хранится базовый адрес изображения.  
  
## <a name="remarks"></a>Remarks  

 Имя файла изображения может содержать или не иметь пути. Если указан путь, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только с именем файла.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
