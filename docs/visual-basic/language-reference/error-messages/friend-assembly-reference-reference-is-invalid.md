---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874089"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="2df68-102">Ссылка \<reference> на дружественную сборку является недопустимой</span><span class="sxs-lookup"><span data-stu-id="2df68-102">Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="2df68-103">Недопустимая ссылка на дружественную сборку \<reference> .</span><span class="sxs-lookup"><span data-stu-id="2df68-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="2df68-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="2df68-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="2df68-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута, определяет сборку со строгим именем, но не включает `PublicKey` атрибут.</span><span class="sxs-lookup"><span data-stu-id="2df68-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="2df68-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="2df68-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2df68-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2df68-107">To correct this error</span></span>  
  
1. <span data-ttu-id="2df68-108">Определите открытый ключ для дружественной сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="2df68-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="2df68-109">Включите открытый ключ как часть имени сборки, передаваемой <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="2df68-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df68-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2df68-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="2df68-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="2df68-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
