---
title: Операторы Module могут присутствовать только на уровне файлов или пространств имен
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 91e6c81bb64c259411cbef8a36629b8b320ea584
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873760"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="64007-102">Операторы Module могут присутствовать только на уровне файлов или пространств имен</span><span class="sxs-lookup"><span data-stu-id="64007-102">'Module' statements can occur only at file or namespace level</span></span>

<span data-ttu-id="64007-103">`Module` операторы должны находиться в верхней части исходного файла сразу после `Option` и `Imports` инструкций, глобальных атрибутов и объявлений пространств имен, но перед всеми остальными объявлениями.</span><span class="sxs-lookup"><span data-stu-id="64007-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="64007-104">**Идентификатор ошибки:** BC30617</span><span class="sxs-lookup"><span data-stu-id="64007-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="64007-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="64007-105">To correct this error</span></span>  
  
- <span data-ttu-id="64007-106">Переместите оператор `Module` в начало объявления пространства имен или исходного файла.</span><span class="sxs-lookup"><span data-stu-id="64007-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64007-107">См. также</span><span class="sxs-lookup"><span data-stu-id="64007-107">See also</span></span>

- [<span data-ttu-id="64007-108">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="64007-108">Module Statement</span></span>](../statements/module-statement.md)
