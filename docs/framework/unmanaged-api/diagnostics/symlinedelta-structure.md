---
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
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609304"
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`mdMethod`|Токен метаданных метода.|  
|`delta`|Число строк, в которые был перемещен метод.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl  
  
## <a name="see-also"></a>Дополнительно

- [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)
