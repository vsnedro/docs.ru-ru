---
title: Использование параметров приложения и параметров пользователя
ms.date: 03/30/2017
description: Узнайте, как использовать параметры приложения и параметры пользователя для создания и доступа к значениям, сохраняемым между сеансами выполнения приложения.
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: a30fd354986265eca002fce57bccf5b3bb2adc15
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903172"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="95ed3-103">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="95ed3-103">Using Application Settings and User Settings</span></span>
<span data-ttu-id="95ed3-104">Начиная с .NET Framework 2,0 можно создавать значения, которые сохраняются между сеансами выполнения приложения, и получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="95ed3-104">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="95ed3-105">Эти значения называются *параметрами*.</span><span class="sxs-lookup"><span data-stu-id="95ed3-105">These values are called *settings*.</span></span> <span data-ttu-id="95ed3-106">Параметры могут представлять пользовательские настройки или ценную информацию, которую приложение должно использовать.</span><span class="sxs-lookup"><span data-stu-id="95ed3-106">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="95ed3-107">Например, можно создать ряд параметров, которые сохраняют пользовательские настройки для цветовой схемы приложения.</span><span class="sxs-lookup"><span data-stu-id="95ed3-107">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="95ed3-108">Или можно сохранить строку подключения, указывающую базу данных, используемую приложением.</span><span class="sxs-lookup"><span data-stu-id="95ed3-108">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="95ed3-109">Параметры позволяют сохранять данные, критически важные для приложения, за пределами кода, а также создавать профили, в которых хранятся предпочтения отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="95ed3-109">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="95ed3-110">В подразделах этого раздела описывается использование параметров во время разработки и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="95ed3-110">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95ed3-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="95ed3-111">In This Section</span></span>  
 [<span data-ttu-id="95ed3-112">Как выполнить: Создание нового параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="95ed3-112">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="95ed3-113">Описание использования Visual Studio для создания нового параметра для приложения.</span><span class="sxs-lookup"><span data-stu-id="95ed3-113">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="95ed3-114">Как выполнить: Изменение значения существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="95ed3-114">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="95ed3-115">Описание использования Visual Studio для изменения значения существующего параметра.</span><span class="sxs-lookup"><span data-stu-id="95ed3-115">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="95ed3-116">Как выполнить: Изменение значения параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="95ed3-116">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="95ed3-117">Сведения о том, как изменить значение параметра в скомпилированном приложении между сеансами приложения.</span><span class="sxs-lookup"><span data-stu-id="95ed3-117">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="95ed3-118">Как выполнить: Считывание параметров во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="95ed3-118">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="95ed3-119">Описывает, как использовать код для чтения параметров с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="95ed3-119">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="95ed3-120">Как выполнить: Написание параметров пользователя во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="95ed3-120">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="95ed3-121">Объясняется, как использовать код для записи и сохранения значений параметров пользователя с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="95ed3-121">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="95ed3-122">Как выполнить: Добавление нескольких наборов параметров в приложение на C#</span><span class="sxs-lookup"><span data-stu-id="95ed3-122">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="95ed3-123">Сведения о добавлении нескольких наборов параметров в приложение с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="95ed3-123">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ed3-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="95ed3-124">See also</span></span>

- [<span data-ttu-id="95ed3-125">Параметры приложения для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95ed3-125">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
