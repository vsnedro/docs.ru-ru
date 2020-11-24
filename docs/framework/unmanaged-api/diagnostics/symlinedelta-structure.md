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
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690945"
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
  
## <a name="see-also"></a>См. также раздел

- [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)
