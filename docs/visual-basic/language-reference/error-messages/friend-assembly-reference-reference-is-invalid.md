---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160715"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="2e5ad-102">BC31535: Недопустимая ссылка на дружественную сборку \<reference></span><span class="sxs-lookup"><span data-stu-id="2e5ad-102">BC31535: Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="2e5ad-103">Недопустимая ссылка на дружественную сборку \<reference> .</span><span class="sxs-lookup"><span data-stu-id="2e5ad-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="2e5ad-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="2e5ad-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>

 <span data-ttu-id="2e5ad-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута, определяет сборку со строгим именем, но не включает `PublicKey` атрибут.</span><span class="sxs-lookup"><span data-stu-id="2e5ad-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>

 <span data-ttu-id="2e5ad-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="2e5ad-106">**Error ID:** BC31535</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2e5ad-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2e5ad-107">To correct this error</span></span>

1. <span data-ttu-id="2e5ad-108">Определите открытый ключ для дружественной сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="2e5ad-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="2e5ad-109">Включите открытый ключ как часть имени сборки, передаваемой <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="2e5ad-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e5ad-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2e5ad-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="2e5ad-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="2e5ad-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
