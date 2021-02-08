---
description: Дополнительные сведения о перечислении CorSymVarFlag
title: Перечисление CorSymVarFlag
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: 28f4b4775e20703e5dcaa7daf69affd3548aa3f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800465"
---
# <a name="corsymvarflag-enumeration"></a>Перечисление CorSymVarFlag

Указывает, создается ли переменная компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|Указывает, что заданная переменная создается компилятором.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Перечисления хранилища символов диагностики](diagnostics-symbol-store-enumerations.md)
