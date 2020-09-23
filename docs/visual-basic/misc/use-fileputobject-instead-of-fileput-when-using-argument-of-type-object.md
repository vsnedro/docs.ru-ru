---
title: При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: c6ae755ad3eca4b1c50b83049885b6cf66f13c07
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100338"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="15aa5-102">При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut</span><span class="sxs-lookup"><span data-stu-id="15aa5-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>

<span data-ttu-id="15aa5-103">Метод `FilePut` включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="15aa5-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="15aa5-104">Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="15aa5-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15aa5-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="15aa5-105">To correct this error</span></span>  
  
- <span data-ttu-id="15aa5-106">Замените `FilePut` на `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="15aa5-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="15aa5-107">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="15aa5-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="15aa5-108">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="15aa5-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15aa5-109">См. также</span><span class="sxs-lookup"><span data-stu-id="15aa5-109">See also</span></span>

- [<span data-ttu-id="15aa5-110">My. Computer. FileSystem</span><span class="sxs-lookup"><span data-stu-id="15aa5-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="15aa5-111">My. Computer. FileSystem. WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="15aa5-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
