---
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: f34095becf321c6cb4b316b6378a2da0107577ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162483"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a><span data-ttu-id="41116-102">BC30830: операторы "Line" больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="41116-102">BC30830: 'Line' statements are no longer supported</span></span>

<span data-ttu-id="41116-103">Операторы Line больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="41116-103">Line statements are no longer supported.</span></span> <span data-ttu-id="41116-104">Функциональные возможности файлового ввода-вывода доступны как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступны в виде `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="41116-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>

 <span data-ttu-id="41116-105">**Идентификатор ошибки:** BC30830</span><span class="sxs-lookup"><span data-stu-id="41116-105">**Error ID:** BC30830</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="41116-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="41116-106">To correct this error</span></span>

- <span data-ttu-id="41116-107">При выполнении доступа к файлу используйте `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="41116-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>

- <span data-ttu-id="41116-108">Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="41116-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>

## <a name="see-also"></a><span data-ttu-id="41116-109">См. также</span><span class="sxs-lookup"><span data-stu-id="41116-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="41116-110">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41116-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
