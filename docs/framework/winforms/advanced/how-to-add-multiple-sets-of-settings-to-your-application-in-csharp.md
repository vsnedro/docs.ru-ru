---
title: 'Как выполнить: Добавление нескольких наборов параметров в приложение на C#'
description: Узнайте, как добавить несколько наборов параметров Windows Forms в приложение на C# с помощью Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173449"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="8cf0c-103">Как добавить несколько наборов параметров в приложение на языке C\#</span><span class="sxs-lookup"><span data-stu-id="8cf0c-103">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="8cf0c-104">В некоторых случаях может потребоваться несколько наборов параметров в приложении.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-104">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="8cf0c-105">Например, при разработке приложения, в котором определенная группа параметров будет часто изменяться, может быть разумно разделить их на один файл, чтобы файл можно было заменить оптовой, при этом другие параметры не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-105">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="8cf0c-106">Visual Studio позволяет добавлять в проект несколько наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-106">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="8cf0c-107">Доступ к дополнительным наборам параметров можно получить через `Properties.Settings` объект.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-107">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="8cf0c-108">Добавление дополнительного набора параметров</span><span class="sxs-lookup"><span data-stu-id="8cf0c-108">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="8cf0c-109">В Visual Studio в меню **проект** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-109">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="8cf0c-110">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-110">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="8cf0c-111">В диалоговом окне **Добавление нового элемента** выберите **файл параметров**, введите имя файла и нажмите кнопку **добавить** , чтобы добавить новый файл параметров в решение.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-111">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="8cf0c-112">В **Обозреватель решений**перетащите новый файл параметров в папку **свойства** .</span><span class="sxs-lookup"><span data-stu-id="8cf0c-112">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="8cf0c-113">Это позволит сделать новые параметры доступными в коде.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-113">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="8cf0c-114">Добавьте и используйте параметры в этом файле так же, как и любые другие файлы параметров.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-114">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="8cf0c-115">Доступ к этой группе параметров можно получить с помощью `Properties.Settings` объекта.</span><span class="sxs-lookup"><span data-stu-id="8cf0c-115">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cf0c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8cf0c-116">See also</span></span>

- [<span data-ttu-id="8cf0c-117">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="8cf0c-117">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="8cf0c-118">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="8cf0c-118">Application Settings Overview</span></span>](application-settings-overview.md)
