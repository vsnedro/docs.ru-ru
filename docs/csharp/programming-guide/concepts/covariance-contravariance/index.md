---
title: Ковариация и контравариантность (C#)
description: Сведения о ковариации и контравариантности, а также о том, как они влияют на совместимость назначений. Пример кода демонстрирует различия между ними.
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: d0309ec1bb3161412433e1b44e8e35410911b38d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176335"
---
# <a name="covariance-and-contravariance-c"></a>Ковариация и контравариантность (C#)

В C# ковариация и контрвариантность позволяют использовать неявное преобразование ссылок для типов массивов и делегатов, а также для аргументов универсального типа. Ковариация сохраняет совместимость присваивания, а при контрвариантности присваивание начинает работать противоположным образом.  
  
 Следующий код показывает разницу между совместимостью присваивания, ковариацией и контрвариантностью.  
  
```csharp  
// Assignment compatibility.
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument
// is assigned to an object instantiated with a less derived type argument.
// Assignment compatibility is preserved.
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;  
```  
  
 Ковариация для массивов позволяет неявно преобразовать массив более производного типа в массив менее производного типа. Но эта операция не является типобезопасной, как показано в следующем примере кода.  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 Поддержка ковариации и контрвариантности для групп методов позволяет сопоставить сигнатуры методов с типами делегатов. За счет этого вы можете назначать делегатам не только методы с совпадающими сигнатурами, но и методы, которые возвращают более производные типы (ковариация) или принимают параметры с менее производными типами (контрвариантность), чем задает тип делегата. Дополнительные сведения см. в разделах [Вариативность в делегатах (C#)](./variance-in-delegates.md) и [Использование вариативности в делегатах (C#)](./using-variance-in-delegates.md).  
  
 В следующем примере кода демонстрируется поддержка ковариации и контрвариантности для групп методов.  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 В .NET Framework 4 и более поздних версиях язык C# поддерживает ковариацию и контрвариантность для универсальных интерфейсов и делегатов, а также позволяет выполнять неявное преобразование параметров универсального типа. Дополнительные сведения см. в разделах [Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md) и [Вариативность в делегатах (C#)](./variance-in-delegates.md).  
  
 В следующем примере кода показано неявное преобразование ссылок для универсальных интерфейсов.  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 Универсальный интерфейс или делегат называется *вариантным*, если его универсальные параметры объявлены ковариантными или контрвариантными. C# позволяет вам создавать собственные вариантные интерфейсы и делегаты. Дополнительные сведения см. в разделах [Создание вариантных универсальных интерфейсов (C#)](./creating-variant-generic-interfaces.md) и [Вариативность в делегатах (C#)](./variance-in-delegates.md).  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md)|В этом разделе описываются ковариантность и контрвариантность в универсальных интерфейсах, а также представлен список вариативных универсальных интерфейсов в .NET.|  
|[Создание вариантных универсальных интерфейсов (C#)](./creating-variant-generic-interfaces.md)|Узнайте, как создавать ваши собственные вариантные интерфейсы.|  
|[Использование вариативности в интерфейсах для универсальных коллекций (C#)](./using-variance-in-interfaces-for-generic-collections.md)|Узнайте, как использовать поддержку ковариации и контрвариантности в интерфейсах <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601> для многократного использования кода.|  
|[Вариативность в делегатах (C#)](./variance-in-delegates.md)|В этом разделе описываются ковариантность и контрвариантность в универсальных и неуниверсальных делегатах, а также представлен список вариантных универсальных делегатов в .NET.|  
|[Использование вариативности в делегатах (C#)](./using-variance-in-delegates.md)|Узнайте, как использовать поддержку ковариации и контрвариантности в неуниверсальных делегатах для сопоставления сигнатур методов с типами делегатов.|  
|[Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)|Узнайте, как использовать поддержку ковариации и контрвариантности в делегатах `Func` и `Action` для многократного использования кода.|
