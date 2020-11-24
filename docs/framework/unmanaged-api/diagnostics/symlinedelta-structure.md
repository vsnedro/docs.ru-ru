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
# <a name="symlinedelta-structure"></a><span data-ttu-id="13512-102">Структура SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="13512-102">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="13512-103">Предоставляет сведения обработчику символов о методах, которые были перемещены в результате изменений.</span><span class="sxs-lookup"><span data-stu-id="13512-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13512-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13512-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="13512-105">Члены</span><span class="sxs-lookup"><span data-stu-id="13512-105">Members</span></span>  
  
|<span data-ttu-id="13512-106">Член</span><span class="sxs-lookup"><span data-stu-id="13512-106">Member</span></span>|<span data-ttu-id="13512-107">Описание</span><span class="sxs-lookup"><span data-stu-id="13512-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="13512-108">Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="13512-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="13512-109">Число строк, в которые был перемещен метод.</span><span class="sxs-lookup"><span data-stu-id="13512-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13512-110">Требования</span><span class="sxs-lookup"><span data-stu-id="13512-110">Requirements</span></span>  

 <span data-ttu-id="13512-111">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="13512-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13512-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13512-112">See also</span></span>

- [<span data-ttu-id="13512-113">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="13512-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
