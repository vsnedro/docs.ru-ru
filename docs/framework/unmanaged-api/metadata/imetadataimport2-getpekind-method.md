---
description: 'Дополнительные сведения о методе: IMetaDataImport2:: GetPEKind'
title: Метод IMetaDataImport2::GetPEKind
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
ms.openlocfilehash: 3cd003f4b1a56f59b9e8c89bf1c4f8f2f8c7fea1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688589"
---
# <a name="imetadataimport2getpekind-method"></a>Метод IMetaDataImport2::GetPEKind

Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файле (обычно это DLL или EXE-файл), который определен в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwPEKind`  
 заполняет Указатель на значение перечисления [CorPEKind](corpekind-enumeration.md) , ОПИСЫВАЮЩее PE-файл.  
  
 `pdwMachine`  
 заполняет Указатель на значение, идентифицирующее архитектуру компьютера. Возможные значения см. в следующем разделе.  
  
## <a name="remarks"></a>Remarks  

 Значение, на которое ссылается `pdwMachine` параметр, может быть одним из следующих.  
  
|Значение|Архитектура компьютера|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|X64|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Перечисление CorPEKind](corpekind-enumeration.md)
