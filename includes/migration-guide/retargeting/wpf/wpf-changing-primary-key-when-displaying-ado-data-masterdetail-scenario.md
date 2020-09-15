---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614972"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="a618d-101">Изменение первичного ключа в WPF при отображении данных ADO в сценарии "главный — подчиненный"</span><span class="sxs-lookup"><span data-stu-id="a618d-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

#### <a name="details"></a><span data-ttu-id="a618d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a618d-102">Details</span></span>

<span data-ttu-id="a618d-103">Давайте рассмотрим сценарий, в котором у вас есть коллекция ADO с элементами типа `Order` и отношение с именем &quot;OrderDetails&quot;, которое сопоставляет ее с другой коллекцией элементов типа `Detail` через первичный ключ &quot;OrderID&quot;.</span><span class="sxs-lookup"><span data-stu-id="a618d-103">Suppose you have an ADO collection of items of type `Order`, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type `Detail` via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="a618d-104">В приложении WPF можно привязать элемент управления "Список" к подробным сведениям о конкретном заказе:</span><span class="sxs-lookup"><span data-stu-id="a618d-104">In your WPF app, you can bind a list control to the details for a given order:</span></span>

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

<span data-ttu-id="a618d-105">DataContext имеет значение `Order`.</span><span class="sxs-lookup"><span data-stu-id="a618d-105">where the DataContext is an `Order`.</span></span> <span data-ttu-id="a618d-106">WPF получает значение свойства `OrderDetails`, коллекцию D всех элементов `Detail`, для которых `OrderID` совпадает с `OrderID` главного элемента.</span><span class="sxs-lookup"><span data-stu-id="a618d-106">WPF gets the value of the `OrderDetails` property - a collection D of all the `Detail` items whose `OrderID` matches the `OrderID` of the master item.</span></span> <span data-ttu-id="a618d-107">Поведение изменяется при изменении первичного ключа `OrderID` главного элемента.</span><span class="sxs-lookup"><span data-stu-id="a618d-107">The behavior change arises when you change the primary key `OrderID` of the master item.</span></span> <span data-ttu-id="a618d-108">ADO автоматически изменяет `OrderID` в каждой из затронутых записей в коллекции Details (то есть в тех, которые копируются в коллекцию D).</span><span class="sxs-lookup"><span data-stu-id="a618d-108">ADO automatically changes the `OrderID` of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="a618d-109">Что же происходит с коллекцией D?</span><span class="sxs-lookup"><span data-stu-id="a618d-109">But what happens to D?</span></span>

- <span data-ttu-id="a618d-110">Старое поведение: коллекция D очищена.</span><span class="sxs-lookup"><span data-stu-id="a618d-110">Old behavior: Collection D is cleared.</span></span> <span data-ttu-id="a618d-111">Главный элемент *не* вызывает уведомление об изменении свойства `OrderDetails`.</span><span class="sxs-lookup"><span data-stu-id="a618d-111">The master item does *not* raise a change notification for property `OrderDetails`.</span></span> <span data-ttu-id="a618d-112">Поле со списком продолжает использовать коллекцию D, которая теперь пуста.</span><span class="sxs-lookup"><span data-stu-id="a618d-112">The ListBox continues to use collection D, which is now empty.</span></span>
- <span data-ttu-id="a618d-113">Новое поведение:  коллекция D — без изменений.</span><span class="sxs-lookup"><span data-stu-id="a618d-113">New behavior:  Collection D is unchanged.</span></span> <span data-ttu-id="a618d-114">Каждый из ее элементов вызывает уведомление об изменении свойства `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="a618d-114">Each of its items raises a change notification for the `OrderID` property.</span></span> <span data-ttu-id="a618d-115">Поле со списком продолжает использовать коллекцию D и отображает подробные сведения с новым значением `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="a618d-115">The ListBox continues to use collection D, and displays the details with the new `OrderID`.</span></span> <span data-ttu-id="a618d-116">Чтобы реализовать новое поведение, WPF создает коллекцию D другим способом, вызывая метод ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> с аргументом `followParent`, который имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a618d-116">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the `followParent` argument set to `true`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a618d-117">Предложение</span><span class="sxs-lookup"><span data-stu-id="a618d-117">Suggestion</span></span>

<span data-ttu-id="a618d-118">Приложение может получит новое поведение, если указать следующий параметр AppContext.</span><span class="sxs-lookup"><span data-stu-id="a618d-118">An app gets the new behavior by using the following AppContext switch.</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

<span data-ttu-id="a618d-119">По умолчанию параметр `true` (старое поведение) используется для приложений, предназначенных для .NET 4.7.1 или ниже, а `false` (новое поведение) — для приложений, предназначенных для .NET 4.7.2 или выше.</span><span class="sxs-lookup"><span data-stu-id="a618d-119">The switch defaults to `true` (old behavior) for apps that target .NET 4.7.1 or below, and to `false` (new behavior) for apps that target .NET 4.7.2 or above.</span></span>

| <span data-ttu-id="a618d-120">name</span><span class="sxs-lookup"><span data-stu-id="a618d-120">Name</span></span>    | <span data-ttu-id="a618d-121">Значение</span><span class="sxs-lookup"><span data-stu-id="a618d-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a618d-122">Область</span><span class="sxs-lookup"><span data-stu-id="a618d-122">Scope</span></span>   | <span data-ttu-id="a618d-123">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="a618d-123">Minor</span></span>       |
| <span data-ttu-id="a618d-124">Version</span><span class="sxs-lookup"><span data-stu-id="a618d-124">Version</span></span> | <span data-ttu-id="a618d-125">4.7.2</span><span class="sxs-lookup"><span data-stu-id="a618d-125">4.7.2</span></span>       |
| <span data-ttu-id="a618d-126">Type</span><span class="sxs-lookup"><span data-stu-id="a618d-126">Type</span></span>    | <span data-ttu-id="a618d-127">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="a618d-127">Retargeting</span></span> |
