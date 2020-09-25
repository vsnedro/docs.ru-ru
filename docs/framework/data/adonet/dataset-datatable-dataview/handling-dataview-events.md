---
title: Обработка событий DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 2a67cb040c5d438d17ad91d41e97f24f3166262b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204545"
---
# <a name="handling-dataview-events"></a>Обработка событий DataView

Событие <xref:System.Data.DataView.ListChanged> объекта <xref:System.Data.DataView> используется для определения того, было ли обновлено представление. К обновлениям, которые вызывают это событие, относятся добавление, удаление или изменение строки в базовой таблице, добавление или удаление столбца из схемы базовой таблицы, изменение в родительской или дочерней связи. Событие **ListChanged** также уведомляет вас, если список просматриваемых строк существенно изменился из-за применения нового порядка сортировки или фильтра.  
  
 Событие **ListChanged** реализует делегат **листчанжедевенсандлер** <xref:System.ComponentModel> пространства имен и принимает в качестве входных данных <xref:System.ComponentModel.ListChangedEventArgs> объект. Вы можете определить, какой тип изменения произошло с помощью <xref:System.ComponentModel.ListChangedType> значения перечисления в свойстве **ListChangedType** объекта **ListChangedEventArgs** . Для изменений, затрагивающих Добавление, удаление или перемещение строк, можно получить доступ к новому индексу добавленной или перемещенной строки и предыдущему индексу удаленной строки с помощью свойства **невиндекс** объекта **ListChangedEventArgs** . В случае перемещенной строки доступ к предыдущему индексу перемещенной строки можно получить с помощью свойства **олдиндекс** объекта **ListChangedEventArgs** .  
  
 **DataViewManager** также предоставляет событие **ListChanged** для уведомления о том, что таблица была добавлена или удалена, или если в коллекцию **связей** базового **набора данных**было внесено изменение.  
  
 В следующем примере кода показано, как добавить обработчик событий **ListChanged** .  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [Объекты DataView](dataviews.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
