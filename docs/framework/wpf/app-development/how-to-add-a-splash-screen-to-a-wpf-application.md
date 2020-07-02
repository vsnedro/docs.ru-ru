---
title: Добавление экрана-заставки
description: Узнайте, как добавить окно запуска или экран-заставку в приложение Windows Presentation Foundation (WPF).
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 0d0cf2e2a550320650c3b4a0c257071a0403c32b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617964"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="32bb9-103">Практическое руководство. Добавление в WPF-приложение экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="32bb9-103">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="32bb9-104">В этом разделе показано, как добавить окно запуска или *экран-заставку*в приложение Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="32bb9-104">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="32bb9-105">Добавление существующего изображения в качестве экрана-заставки</span><span class="sxs-lookup"><span data-stu-id="32bb9-105">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="32bb9-106">Создайте или найдите изображение, которое вы хотите использовать для экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="32bb9-106">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="32bb9-107">Можно использовать любой формат изображения, поддерживаемый компонентом Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="32bb9-107">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="32bb9-108">Например, можно использовать формат BMP, GIF, JPEG, PNG или TIFF.</span><span class="sxs-lookup"><span data-stu-id="32bb9-108">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="32bb9-109">Добавьте файл изображения в проект приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="32bb9-109">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="32bb9-110">В **Обозреватель решений**выберите изображение.</span><span class="sxs-lookup"><span data-stu-id="32bb9-110">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="32bb9-111">В окно свойств щелкните стрелку раскрывающегося списка для свойства **действие сборки** .</span><span class="sxs-lookup"><span data-stu-id="32bb9-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="32bb9-112">Выберите **SplashScreen** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="32bb9-112">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="32bb9-113">Нажмите клавишу **F5** , чтобы создать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="32bb9-113">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="32bb9-114">Изображение экрана-заставки отображается в центре экрана, а затем исчезает при появлении главного окна приложения.</span><span class="sxs-lookup"><span data-stu-id="32bb9-114">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="32bb9-115">Исключение экрана-заставки из сборки</span><span class="sxs-lookup"><span data-stu-id="32bb9-115">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="32bb9-116">В **Обозреватель решений**выберите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="32bb9-116">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="32bb9-117">В окне **Свойства** задайте для **действия сборки** значение **нет**.</span><span class="sxs-lookup"><span data-stu-id="32bb9-117">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="32bb9-118">Удаление экрана-заставки из приложения</span><span class="sxs-lookup"><span data-stu-id="32bb9-118">To remove the splash screen from an application</span></span>

<span data-ttu-id="32bb9-119">В **Обозреватель решений**удалите изображение экрана-заставки.</span><span class="sxs-lookup"><span data-stu-id="32bb9-119">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="32bb9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="32bb9-120">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="32bb9-121">[Как добавить существующие элементы в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="32bb9-121">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
