---
description: 'Дополнительные сведения о: структура SYMLINEDELTA'
title: Структура SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: ae00d2be9809b48180d2cd99d05e410624033419
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761451"
---
# <a name="symlinedelta-structure"></a>Структура SYMLINEDELTA

Предоставляет сведения обработчику символов о методах, которые были перемещены в результате изменений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`mdMethod`|Токен метаданных метода.|  
|`delta`|Число строк, в которые был перемещен метод.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl  
  
## <a name="see-also"></a>См. также

- [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)
