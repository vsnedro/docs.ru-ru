---
title: При компиляции XML-схем в проекте возникли ошибки
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 747c2c8cb1e5dc3d4fcae86a9acf84446c4e59c9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162041"
---
# <a name="bc36810-errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="40425-102">BC36810: произошли ошибки при компиляции XML-схем в проекте</span><span class="sxs-lookup"><span data-stu-id="40425-102">BC36810: Errors occurred while compiling the XML schemas in the project</span></span>

<span data-ttu-id="40425-103">Произошли ошибки при компиляции XML-схем в проекте.</span><span class="sxs-lookup"><span data-stu-id="40425-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="40425-104">По этой причине XML IntelliSense недоступен.</span><span class="sxs-lookup"><span data-stu-id="40425-104">Because of this, XML IntelliSense is not available.</span></span>

 <span data-ttu-id="40425-105">Ошибка в схеме определения схемы XML (XSD), включенной в проект.</span><span class="sxs-lookup"><span data-stu-id="40425-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="40425-106">Эта ошибка возникает при добавлении файла XSD-схемы (XSD), который конфликтует с существующим набором схем XSD для проекта.</span><span class="sxs-lookup"><span data-stu-id="40425-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>

 <span data-ttu-id="40425-107">**Идентификатор ошибки:** BC36810</span><span class="sxs-lookup"><span data-stu-id="40425-107">**Error ID:** BC36810</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="40425-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="40425-108">To correct this error</span></span>

- <span data-ttu-id="40425-109">Дважды щелкните предупреждение в окне **Список ошибок** .</span><span class="sxs-lookup"><span data-stu-id="40425-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="40425-110">Visual Basic перейдет к расположению в XSD-файле, который является источником предупреждения.</span><span class="sxs-lookup"><span data-stu-id="40425-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="40425-111">Исправьте ошибку в схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="40425-111">Correct the error in the XSD schema.</span></span>

- <span data-ttu-id="40425-112">Убедитесь, что в проект включены все необходимые файлы XSD-схемы (. xsd).</span><span class="sxs-lookup"><span data-stu-id="40425-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="40425-113">Чтобы просмотреть XSD-файлы в **Обозреватель решений**, может потребоваться выбрать пункт **Показать все файлы** в меню **проект** .</span><span class="sxs-lookup"><span data-stu-id="40425-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="40425-114">Щелкните правой кнопкой мыши XSD-файл и выберите **включить в проект** , чтобы включить файл в проект.</span><span class="sxs-lookup"><span data-stu-id="40425-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>

- <span data-ttu-id="40425-115">Если используется Мастер XML для схемы, эта ошибка может возникать, если вы выводите схемы несколько раз из одного источника.</span><span class="sxs-lookup"><span data-stu-id="40425-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="40425-116">В этом случае можно удалить существующие файлы XSD-схемы из проекта, добавить новый XML в шаблон элемента схемы, а затем предоставить мастеру XML для схемы все применимые источники XML для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="40425-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>

- <span data-ttu-id="40425-117">Если в схеме XSD не обнаружена ошибка, компилятор XML может не иметь достаточной информации для предоставления подробного сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="40425-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="40425-118">Если вы убедитесь, что пространства имен XML для XSD-файлов, включаемых в проект, соответствуют пространствам имен XML, определенным для набора XML-схем в Visual Studio, вы можете получить более подробные сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="40425-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="40425-119">См. также</span><span class="sxs-lookup"><span data-stu-id="40425-119">See also</span></span>

- [<span data-ttu-id="40425-120">Окно Список ошибок</span><span class="sxs-lookup"><span data-stu-id="40425-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="40425-121">XML</span><span class="sxs-lookup"><span data-stu-id="40425-121">XML</span></span>](../../programming-guide/language-features/xml/index.md)
