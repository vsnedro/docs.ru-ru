---
title: Руководство по программированию на C#. Реализация событий интерфейса
description: Сведения о реализации событий интерфейса в классе. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 153a2efa254bf2f2c81cec4b28a53207cdc4efe5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167552"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Руководство по программированию на C#. Реализация событий интерфейса

[Интерфейс](../../language-reference/keywords/interface.md) может объявлять [события](../../language-reference/keywords/event.md). Следующий пример демонстрирует реализацию событий интерфейса в классе. По сути правила остаются таким же, как при реализации любого метода или свойства интерфейса.  
  
## <a name="to-implement-interface-events-in-a-class"></a>Реализация событий интерфейса в классе  
  
Объявите событие в классе и вызовите его, когда потребуется.  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a>Пример  

Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем. Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий. Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`. Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.  
  
Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям. Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе. В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [События](./index.md)
- [Делегаты](../delegates/index.md)
- [Явная реализация интерфейса](../interfaces/explicit-interface-implementation.md)
- [Практическое руководство. Создание событий базового класса в производных классах](./how-to-raise-base-class-events-in-derived-classes.md)
