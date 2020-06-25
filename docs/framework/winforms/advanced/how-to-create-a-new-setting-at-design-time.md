---
title: 'Как выполнить: Создание нового параметра во время разработки'
description: Узнайте, как создать новый параметр Windows Forms во время разработки с помощью конструктора параметров в Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325850"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="75b67-103">Как создать новый параметр во время разработки</span><span class="sxs-lookup"><span data-stu-id="75b67-103">How To: Create a new setting at design time</span></span>

<span data-ttu-id="75b67-104">Новый параметр можно создать во время разработки с помощью конструктора параметров в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75b67-104">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="75b67-105">Конструктор параметров — это интерфейс в стиле сетки, позволяющий создавать новые параметры и задавать свойства этих параметров.</span><span class="sxs-lookup"><span data-stu-id="75b67-105">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="75b67-106">Для новых параметров необходимо указать имя, значение, тип и область.</span><span class="sxs-lookup"><span data-stu-id="75b67-106">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="75b67-107">После создания параметра он доступен в коде.</span><span class="sxs-lookup"><span data-stu-id="75b67-107">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="75b67-108">Создание нового параметра во время разработки в C\#</span><span class="sxs-lookup"><span data-stu-id="75b67-108">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="75b67-109">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75b67-109">Open Visual Studio.</span></span>

2. <span data-ttu-id="75b67-110">В **Обозреватель решений**разверните узел **свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="75b67-110">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="75b67-111">Дважды щелкните файл. Settings, в который нужно добавить новый параметр.</span><span class="sxs-lookup"><span data-stu-id="75b67-111">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="75b67-112">По умолчанию для этого файла используется имя Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="75b67-112">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="75b67-113">В конструкторе параметров задайте **имя**, **значение**, **тип**и **область** для параметра.</span><span class="sxs-lookup"><span data-stu-id="75b67-113">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="75b67-114">Каждая строка представляет отдельный параметр.</span><span class="sxs-lookup"><span data-stu-id="75b67-114">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="75b67-115">Создание нового параметра во время разработки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75b67-115">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="75b67-116">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75b67-116">Open Visual Studio.</span></span>

2. <span data-ttu-id="75b67-117">В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="75b67-117">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="75b67-118">На странице **Свойства** перейдите на вкладку **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="75b67-118">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="75b67-119">В конструкторе параметров задайте **имя**, **значение**, **тип**и **область** для параметра.</span><span class="sxs-lookup"><span data-stu-id="75b67-119">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="75b67-120">Каждая строка представляет отдельный параметр.</span><span class="sxs-lookup"><span data-stu-id="75b67-120">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="75b67-121">См. также</span><span class="sxs-lookup"><span data-stu-id="75b67-121">See also</span></span>

- [<span data-ttu-id="75b67-122">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="75b67-122">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="75b67-123">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="75b67-123">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="75b67-124">Как выполнить: Изменение значения существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="75b67-124">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
