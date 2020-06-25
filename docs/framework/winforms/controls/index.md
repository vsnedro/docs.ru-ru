---
title: Элементы управления
description: Сведения о добавлении и размещении элементов управления Windows Forms. Можно также управлять элементами управления в конструкторе и писать код для динамического добавления элементов управления во время выполнения.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls
- controls [Windows Forms]
- Windows Forms controls, about Windows Forms controls
ms.assetid: f050de8f-4ebd-4042-94b8-edf9a1dbd52a
ms.openlocfilehash: 9ca4a2a1205663ae0ff4537a58cc1991a15da5d8
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324043"
---
# <a name="windows-forms-controls"></a><span data-ttu-id="1539a-104">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1539a-104">Windows Forms controls</span></span>

<span data-ttu-id="1539a-105">При проектировании и изменении пользовательского интерфейса приложений Windows Forms, вам потребуется добавлять, выравнивать и размещать элементы управления.</span><span class="sxs-lookup"><span data-stu-id="1539a-105">As you design and modify the user interface of your Windows Forms applications, you will need to add, align, and position controls.</span></span> <span data-ttu-id="1539a-106">Элементы управления — это объекты, содержащиеся в объектах форм.</span><span class="sxs-lookup"><span data-stu-id="1539a-106">Controls are objects that are contained within form objects.</span></span> <span data-ttu-id="1539a-107">Каждый тип элемента управления имеет собственный набор свойств, методов и событий для достижения определенной цели.</span><span class="sxs-lookup"><span data-stu-id="1539a-107">Each type of control has its own set of properties, methods, and events that make it suitable for a particular purpose.</span></span> <span data-ttu-id="1539a-108">Вы можете управлять элементами управления в конструкторе и писать код для динамического добавления элементов управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1539a-108">You can manipulate controls in the designer and write code to add controls dynamically at run time.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1539a-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="1539a-109">In this section</span></span>

<span data-ttu-id="1539a-110">[Размещение элементов управления на Windows Forms](putting-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-110">[Putting Controls on Windows Forms](putting-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="1539a-111">Ссылки, связанные с размещением элементов управления в формах.</span><span class="sxs-lookup"><span data-stu-id="1539a-111">Provides links related to putting controls on forms.</span></span>

<span data-ttu-id="1539a-112">[Упорядочивание элементов управления в Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-112">[Arranging Controls on Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="1539a-113">Статьи, связанные с упорядочиванием элементов управления в формах.</span><span class="sxs-lookup"><span data-stu-id="1539a-113">Articles related to arranging controls on forms.</span></span>

<span data-ttu-id="1539a-114">[Добавление меток к отдельным элементам управления Windows Forms и предоставление им ярлыков](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-114">[Labeling Individual Windows Forms Controls and Providing Shortcuts to Them](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span></span>\
<span data-ttu-id="1539a-115">Использование сочетаний клавиш, текстовых меток на элементах управления, а также клавиш-модификаторов.</span><span class="sxs-lookup"><span data-stu-id="1539a-115">Describes the uses of keyboard shortcuts, text labels on controls, and modifier keys.</span></span>

<span data-ttu-id="1539a-116">[Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-116">[Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md)</span></span>\
<span data-ttu-id="1539a-117">Список элементов управления, которые работают с Windows Forms, а также основные действия, которые можно выполнить с каждым элементом.</span><span class="sxs-lookup"><span data-stu-id="1539a-117">Lists the controls that work with Windows Forms, and basic things you can accomplish with each control.</span></span>

<span data-ttu-id="1539a-118">[Разработка пользовательских элементов управления Windows Forms с помощью .NET Framework](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-118">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="1539a-119">Дополнительные сведения и образцы, которые помогут вам в разработке пользовательских элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1539a-119">Provides background information and samples to help users develop custom Windows Forms controls.</span></span>

<span data-ttu-id="1539a-120">[Разработка элементов управления Windows Forms во время разработки](developing-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-120">[Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="1539a-121">Способы создания пользовательских элементов управления с помощью проектирования и наследования.</span><span class="sxs-lookup"><span data-stu-id="1539a-121">Describes techniques for creating custom controls through design and inheritance.</span></span>

## <a name="related-sections"></a><span data-ttu-id="1539a-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="1539a-122">Related sections</span></span>

<span data-ttu-id="1539a-123">[Клиентские приложения](../../develop-client-apps.md)</span><span class="sxs-lookup"><span data-stu-id="1539a-123">[Client Applications](../../develop-client-apps.md)</span></span>\
<span data-ttu-id="1539a-124">Сведения о разработке приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="1539a-124">Provides an overview of developing Windows-based applications.</span></span>
