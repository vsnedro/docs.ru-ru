---
title: 'Ошибка при создании манифеста сборки: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: a772167966c4ec858197cc2032f4ae3d4e86070c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163419"
---
# <a name="bc30140-error-creating-assembly-manifest-error-message"></a><span data-ttu-id="6f2af-102">BC30140: ошибка при создании манифеста сборки: \<error message></span><span class="sxs-lookup"><span data-stu-id="6f2af-102">BC30140: Error creating assembly manifest: \<error message></span></span>

<span data-ttu-id="6f2af-103">Компилятор Visual Basic вызывает компоновщик сборок (Al.exe, также известный как ALink) для создания сборки с манифестом.</span><span class="sxs-lookup"><span data-stu-id="6f2af-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="6f2af-104">Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.</span><span class="sxs-lookup"><span data-stu-id="6f2af-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>

 <span data-ttu-id="6f2af-105">Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей.</span><span class="sxs-lookup"><span data-stu-id="6f2af-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="6f2af-106">Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах.</span><span class="sxs-lookup"><span data-stu-id="6f2af-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="6f2af-107">Чтобы использовать для сборки отложенную подпись, необходимо установить флажок **Только отложенная подпись** и предоставить допустимый файл ключа с информацией о ключах.</span><span class="sxs-lookup"><span data-stu-id="6f2af-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="6f2af-108">При использовании отложенной подписи для сборки наличие закрытого ключа не требуется.</span><span class="sxs-lookup"><span data-stu-id="6f2af-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="6f2af-109">Дополнительные сведения см. в разделе [Как подписать сборку строгим именем](../../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="6f2af-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>

 <span data-ttu-id="6f2af-110">**Идентификатор ошибки:** BC30140</span><span class="sxs-lookup"><span data-stu-id="6f2af-110">**Error ID:** BC30140</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6f2af-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6f2af-111">To correct this error</span></span>

1. <span data-ttu-id="6f2af-112">Изучите сообщение об ошибке в кавычках и ознакомьтесь с разделом [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="6f2af-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="6f2af-113">дополнительные объяснения и советы по ошибке AL1019</span><span class="sxs-lookup"><span data-stu-id="6f2af-113">for error AL1019 further explanation and advice</span></span>

2. <span data-ttu-id="6f2af-114">Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6f2af-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f2af-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6f2af-115">See also</span></span>

- [<span data-ttu-id="6f2af-116">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="6f2af-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="6f2af-117">Страница "Подписывание" в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="6f2af-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
- [<span data-ttu-id="6f2af-118">Al.exe</span><span class="sxs-lookup"><span data-stu-id="6f2af-118">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="6f2af-119">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="6f2af-119">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
