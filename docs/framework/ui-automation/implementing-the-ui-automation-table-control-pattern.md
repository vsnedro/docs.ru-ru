---
title: Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса
description: Ознакомьтесь с правилами и соглашениями для реализации шаблона элемента управления Table в модели автоматизации пользовательского интерфейса. Знание обязательных членов для интерфейса Итаблепровидер.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 9c1d57e46aed9ec2441a95544d26244d2dfa9496
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265756"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="2a7dd-104">Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-104">Implementing the UI Automation Table Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="2a7dd-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="2a7dd-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2a7dd-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="2a7dd-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2a7dd-107">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITableProvider>, включая сведения о свойствах, методах и событиях.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="2a7dd-108">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="2a7dd-109">Шаблон элемента управления <xref:System.Windows.Automation.TablePattern> используется для поддержки элементов управления, которые действуют как контейнеры для коллекции дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-109">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="2a7dd-110">Дочерние элементы данного элемента должны реализовывать <xref:System.Windows.Automation.Provider.ITableItemProvider> и быть организованы в двумерной логической системе координат, к которой можно обращаться по строкам и столбцам.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-110">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="2a7dd-111">Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IGridProvider>, с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableProvider>, также должен предоставлять отношение заголовка столбца и строки для каждого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="2a7dd-112">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2a7dd-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="2a7dd-113">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="2a7dd-113">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="2a7dd-114">При реализации шаблона элемента управления Table обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-114">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="2a7dd-115">Доступ к содержимому отдельных ячеек осуществляется через двумерную логическую систему координат или массив, предоставляемый требуемой параллельной реализацией интерфейса <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-115">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
- <span data-ttu-id="2a7dd-116">Заголовок столбца или строки может содержаться в объекте таблицы или быть отдельным объектом заголовка, связанным с объектом таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-116">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
- <span data-ttu-id="2a7dd-117">Заголовки столбцов и строк могут включать и основной заголовок, и любые поддерживаемые заголовки.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-117">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a7dd-118">Эта концепция станет очевидной в электронной таблице Microsoft Excel, где пользователь определил столбец «First Name» (имя).</span><span class="sxs-lookup"><span data-stu-id="2a7dd-118">This concept becomes evident in a Microsoft Excel spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="2a7dd-119">Теперь этот столбец имеет два заголовка: заголовок "Имя", определенный пользователем, и алфавитно-цифровое обозначение этого столбца, назначенное приложением.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-119">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
- <span data-ttu-id="2a7dd-120">См. раздел [Реализация шаблона элемента управления сетки модели автоматизации пользовательского интерфейса](implementing-the-ui-automation-grid-control-pattern.md) для связанных функций сетки.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-120">See [Implementing the UI Automation Grid Control Pattern](implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="2a7dd-121">![Таблица с двумя сложными элементами верхнего колонтитула.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="2a7dd-121">![Table with complex header items.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="2a7dd-122">Пример таблицы со сложными заголовками столбцов</span><span class="sxs-lookup"><span data-stu-id="2a7dd-122">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="2a7dd-123">![Таблица с неоднозначным свойством RowOrColumnMajor.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="2a7dd-123">![Table with ambiguous RowOrColumnMajor property.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="2a7dd-124">Пример таблицы с неоднозначным свойством RowOrColumnMajor.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-124">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>

## <a name="required-members-for-itableprovider"></a><span data-ttu-id="2a7dd-125">Обязательные члены для ITableProvider</span><span class="sxs-lookup"><span data-stu-id="2a7dd-125">Required Members for ITableProvider</span></span>  

 <span data-ttu-id="2a7dd-126">Следующие свойства и методы обязательны для реализации интерфейса ITableProvider.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-126">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="2a7dd-127">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="2a7dd-127">Required members</span></span>|<span data-ttu-id="2a7dd-128">Тип члена</span><span class="sxs-lookup"><span data-stu-id="2a7dd-128">Member type</span></span>|<span data-ttu-id="2a7dd-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a7dd-129">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="2a7dd-130">Свойство.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-130">Property</span></span>|<span data-ttu-id="2a7dd-131">Нет</span><span class="sxs-lookup"><span data-stu-id="2a7dd-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="2a7dd-132">Метод</span><span class="sxs-lookup"><span data-stu-id="2a7dd-132">Method</span></span>|<span data-ttu-id="2a7dd-133">Нет</span><span class="sxs-lookup"><span data-stu-id="2a7dd-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="2a7dd-134">Метод</span><span class="sxs-lookup"><span data-stu-id="2a7dd-134">Method</span></span>|<span data-ttu-id="2a7dd-135">Нет</span><span class="sxs-lookup"><span data-stu-id="2a7dd-135">None</span></span>|  
  
 <span data-ttu-id="2a7dd-136">Этот шаблон элемента управления не имеет связанных событий.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="2a7dd-137">Исключения</span><span class="sxs-lookup"><span data-stu-id="2a7dd-137">Exceptions</span></span>  

 <span data-ttu-id="2a7dd-138">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="2a7dd-138">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7dd-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2a7dd-139">See also</span></span>

- [<span data-ttu-id="2a7dd-140">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-140">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="2a7dd-141">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-141">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="2a7dd-142">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="2a7dd-142">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="2a7dd-143">Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-143">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="2a7dd-144">Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-144">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="2a7dd-145">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-145">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="2a7dd-146">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2a7dd-146">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
