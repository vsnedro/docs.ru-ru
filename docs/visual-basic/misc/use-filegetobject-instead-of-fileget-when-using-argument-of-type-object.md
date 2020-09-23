---
title: При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059409"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="7ad5a-102">При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet</span><span class="sxs-lookup"><span data-stu-id="7ad5a-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="7ad5a-103">Метод `FileGet` включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="7ad5a-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="7ad5a-104">Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .</span><span class="sxs-lookup"><span data-stu-id="7ad5a-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="7ad5a-105">Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="7ad5a-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7ad5a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7ad5a-106">To correct this error</span></span>  
  
1. <span data-ttu-id="7ad5a-107">Замените `FileGet` на `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="7ad5a-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="7ad5a-108">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="7ad5a-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad5a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7ad5a-109">See also</span></span>

- [<span data-ttu-id="7ad5a-110">My. Computer. FileSystem</span><span class="sxs-lookup"><span data-stu-id="7ad5a-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
