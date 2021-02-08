---
description: 'Дополнительные сведения о: структура CoreClrDebugProcInfo'
title: Структура CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 04befb057be689e68dd3571a13990da9af64551f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801492"
---
# <a name="coreclrdebugprocinfo-structure"></a>Структура CoreClrDebugProcInfo

Представляет процесс, который выполняется на удаленном компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`m_dwPID`|Идентификатор процесса, назначенный операционной системой.|  
|`m_dwInternalID`|Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере. Этот идентификатор перезапускается реже, чем идентификатор ОС.|  
|`m_wszName`|Командная строка процесса. Этот член может быть усечен.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Платформа .NET Framework версии:** 3,5 SP1
