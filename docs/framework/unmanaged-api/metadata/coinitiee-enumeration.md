---
title: Перечисление COINITIEE
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: 673450bb8209abede15e3cb65dd764b418073bc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724199"
---
# <a name="coinitiee-enumeration"></a>Перечисление COINITIEE

Указывает константы, используемые [CoInitialize](../hosting/coinitializeee-function.md) при инициализации среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Режим инициализации по умолчанию. Это Инициализирует среду выполнения и создает значение по умолчанию <xref:System.AppDomain> .|  
|`COINITEE_DLL`|Инициализирует для запуска управляемой библиотеки DLL.|  
|`COINITEE_MAIN`|Инициализирует для запуска управляемого EXE-файла. При этом инициализируется среда выполнения, но не создается значение по умолчанию <xref:System.AppDomain> , которое создается после ввода основной подпрограммы exe-файла.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
