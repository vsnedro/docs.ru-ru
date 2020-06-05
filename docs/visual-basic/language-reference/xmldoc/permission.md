---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: b3acec04060367a0b9e54b19c0106644d028357b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400038"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="b10d4-101">\<permission> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b10d4-101">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="b10d4-102">Указывает требуемое разрешение для элемента.</span><span class="sxs-lookup"><span data-stu-id="b10d4-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b10d4-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b10d4-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b10d4-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="b10d4-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="b10d4-105">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="b10d4-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b10d4-106">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="b10d4-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b10d4-107">Заключите `member` в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="b10d4-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="b10d4-108">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="b10d4-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b10d4-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b10d4-109">Remarks</span></span>  
 <span data-ttu-id="b10d4-110">Используйте `<permission>` тег для документирования доступа к элементу.</span><span class="sxs-lookup"><span data-stu-id="b10d4-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="b10d4-111">Используйте <xref:System.Security.PermissionSet> класс, чтобы указать доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="b10d4-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="b10d4-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="b10d4-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b10d4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b10d4-113">Example</span></span>  
 <span data-ttu-id="b10d4-114">В этом примере `<permission>` тег используется для описания того, что объект <xref:System.Security.Permissions.FileIOPermission> является обязательным для `ReadFile` метода.</span><span class="sxs-lookup"><span data-stu-id="b10d4-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="b10d4-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b10d4-115">See also</span></span>

- [<span data-ttu-id="b10d4-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="b10d4-116">XML Comment Tags</span></span>](index.md)
