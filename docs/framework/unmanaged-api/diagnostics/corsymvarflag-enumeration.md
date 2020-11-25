---
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
ms.openlocfilehash: ed08d9f818f6fc180dbd655243488bf8a527ae11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725291"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="4a71e-102">Перечисление CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="4a71e-102">CorSymVarFlag Enumeration</span></span>

<span data-ttu-id="4a71e-103">Указывает, создается ли переменная компилятором.</span><span class="sxs-lookup"><span data-stu-id="4a71e-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a71e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a71e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="4a71e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4a71e-105">Members</span></span>  
  
|<span data-ttu-id="4a71e-106">Член</span><span class="sxs-lookup"><span data-stu-id="4a71e-106">Member</span></span>|<span data-ttu-id="4a71e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4a71e-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="4a71e-108">Указывает, что заданная переменная создается компилятором.</span><span class="sxs-lookup"><span data-stu-id="4a71e-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a71e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4a71e-109">Requirements</span></span>  

 <span data-ttu-id="4a71e-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4a71e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a71e-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a71e-111">See also</span></span>

- [<span data-ttu-id="4a71e-112">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="4a71e-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
