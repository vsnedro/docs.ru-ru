---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614972"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>Изменение первичного ключа в WPF при отображении данных ADO в сценарии "главный — подчиненный"

#### <a name="details"></a>Подробнее

Давайте рассмотрим сценарий, в котором у вас есть коллекция ADO с элементами типа `Order` и отношение с именем &quot;OrderDetails&quot;, которое сопоставляет ее с другой коллекцией элементов типа `Detail` через первичный ключ &quot;OrderID&quot;. В приложении WPF можно привязать элемент управления "Список" к подробным сведениям о конкретном заказе:

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

DataContext имеет значение `Order`. WPF получает значение свойства `OrderDetails`, коллекцию D всех элементов `Detail`, для которых `OrderID` совпадает с `OrderID` главного элемента. Поведение изменяется при изменении первичного ключа `OrderID` главного элемента. ADO автоматически изменяет `OrderID` в каждой из затронутых записей в коллекции Details (то есть в тех, которые копируются в коллекцию D).  Что же происходит с коллекцией D?

- Старое поведение: коллекция D очищена. Главный элемент *не* вызывает уведомление об изменении свойства `OrderDetails`. Поле со списком продолжает использовать коллекцию D, которая теперь пуста.
- Новое поведение:  коллекция D — без изменений. Каждый из ее элементов вызывает уведомление об изменении свойства `OrderID`. Поле со списком продолжает использовать коллекцию D и отображает подробные сведения с новым значением `OrderID`. Чтобы реализовать новое поведение, WPF создает коллекцию D другим способом, вызывая метод ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> с аргументом `followParent`, который имеет значение `true`.

#### <a name="suggestion"></a>Предложение

Приложение может получит новое поведение, если указать следующий параметр AppContext.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

По умолчанию параметр `true` (старое поведение) используется для приложений, предназначенных для .NET 4.7.1 или ниже, а `false` (новое поведение) — для приложений, предназначенных для .NET 4.7.2 или выше.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
