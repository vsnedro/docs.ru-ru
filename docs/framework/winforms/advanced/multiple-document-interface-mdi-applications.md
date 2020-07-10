---
title: Приложения с интерфейсом MDI
description: Узнайте, как Windows Forms приложения с многодокументным интерфейсом (MDI) позволяют одновременно отображать несколько документов, при этом каждый документ отображается в отдельном окне.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174657"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="a8e8a-103">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="a8e8a-103">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="a8e8a-104">Приложения с многодокументным интерфейсом (MDI) позволяют отображать несколько документов одновременно, при этом каждый документ отображается в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-104">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="a8e8a-105">Приложения MDI часто имеют пункт меню «окно» с подменю для переключения между окнами или документами.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-105">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8e8a-106">Существуют различия в поведении между формами MDI и окнами однодокументного интерфейса (SDI) в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-106">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="a8e8a-107">`Opacity`Свойство не влияет на внешний вид дочерних форм MDI.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-107">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="a8e8a-108">Кроме того, <xref:System.Windows.Forms.Form.CenterToParent%2A> метод не влияет на поведение дочерних форм MDI.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-108">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8e8a-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a8e8a-109">In This Section</span></span>  
 [<span data-ttu-id="a8e8a-110">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="a8e8a-110">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="a8e8a-111">Инструкции по созданию контейнера для нескольких документов в приложении MDI.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-111">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="a8e8a-112">Практическое руководство. Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="a8e8a-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="a8e8a-113">Инструкции по созданию одного или нескольких окон, которые работают в родительской форме MDI.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-113">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="a8e8a-114">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="a8e8a-114">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="a8e8a-115">Инструкции по проверке дочернего окна, имеющего фокус (и отправке его содержимого в буфер обмена).</span><span class="sxs-lookup"><span data-stu-id="a8e8a-115">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="a8e8a-116">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="a8e8a-116">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="a8e8a-117">Инструкции по переносу сведений в активное дочернее окно.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-117">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="a8e8a-118">Практическое руководство. Упорядочение дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="a8e8a-118">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="a8e8a-119">Инструкции по мозаичному разбиению, каскаду или упорядочению дочерних окон приложения MDI.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-119">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
