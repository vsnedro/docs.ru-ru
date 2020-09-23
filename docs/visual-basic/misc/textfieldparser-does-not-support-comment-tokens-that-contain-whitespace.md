---
title: TextFieldParser не поддерживает маркеры комментариев, содержащие пробелы
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 825f999f8eab3563dd77039ef19ae5e329bb4240
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078506"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a><span data-ttu-id="e9f5e-102">TextFieldParser не поддерживает маркеры комментариев, содержащие пробелы</span><span class="sxs-lookup"><span data-stu-id="e9f5e-102">TextFieldParser does not support comment tokens that contain white space</span></span>

<span data-ttu-id="e9f5e-103">Представлен токен комментария, содержащий пробел.</span><span class="sxs-lookup"><span data-stu-id="e9f5e-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="e9f5e-104">`TextFieldParser` не поддерживает токены комментариев, содержащие пробелы, если это не пробел в начале токена.</span><span class="sxs-lookup"><span data-stu-id="e9f5e-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="e9f5e-105">Пробелы в начале токена игнорируются.</span><span class="sxs-lookup"><span data-stu-id="e9f5e-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9f5e-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e9f5e-106">To correct this error</span></span>  
  
- <span data-ttu-id="e9f5e-107">Укажите правильный токен комментария.</span><span class="sxs-lookup"><span data-stu-id="e9f5e-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f5e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e9f5e-108">See also</span></span>

- [<span data-ttu-id="e9f5e-109">Свойство TextFieldParser.CommentTokens</span><span class="sxs-lookup"><span data-stu-id="e9f5e-109">TextFieldParser.CommentTokens Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [<span data-ttu-id="e9f5e-110">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="e9f5e-110">Parsing Text Files with the TextFieldParser Object</span></span>](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="e9f5e-111">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="e9f5e-111">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
