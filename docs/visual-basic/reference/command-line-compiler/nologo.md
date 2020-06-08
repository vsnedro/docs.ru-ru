---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: d1307603ebc06b4eb4c3786f1cd2fb432c0cf636
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360466"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="7c847-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c847-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="7c847-103">Отключает отображение баннера авторских прав и информационных сообщений во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7c847-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c847-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c847-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="7c847-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c847-105">Remarks</span></span>  
 <span data-ttu-id="7c847-106">При указании `-nologo` компилятор не отображает баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="7c847-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="7c847-107">По умолчанию `-nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="7c847-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c847-108">Параметр `-nologo` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7c847-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c847-109">Пример</span><span class="sxs-lookup"><span data-stu-id="7c847-109">Example</span></span>  
 <span data-ttu-id="7c847-110">Следующий код компилирует `T2.vb` и не отображает баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="7c847-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c847-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7c847-111">See also</span></span>

- [<span data-ttu-id="7c847-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7c847-112">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="7c847-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7c847-113">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
