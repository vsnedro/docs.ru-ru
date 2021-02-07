---
description: 'Дополнительные сведения о методе: ICorDebugAppDomain:: Жетмодулефромметадатаинтерфаце'
title: Метод ICorDebugAppDomain::GetModuleFromMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: 7b0c74bd04024f9f4bf26b5ee8abe18a3a7059e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754242"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a>Метод ICorDebugAppDomain::GetModuleFromMetaDataInterface

Возвращает модуль, соответствующий заданному интерфейсу метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pIMetaData`  
 окне Указатель на объект, который является одним из [интерфейсов метаданных](../metadata/metadata-interfaces.md).  
  
 `ppModule`  
 заполняет Указатель на адрес объекта ICorDebugModule, который представляет модуль, соответствующий заданному интерфейсу метаданных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
