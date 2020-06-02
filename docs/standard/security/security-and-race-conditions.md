---
title: Безопасность и конфликты
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: 715bf240a5f7f44ba3f914ad6788631074aa41b2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291023"
---
# <a name="security-and-race-conditions"></a>Безопасность и конфликты
Другой проблемой является возможность использования брешей в безопасности в условиях состязания. Это может произойти несколькими способами. Подразделы, приведенные ниже, описывают некоторые основные ошибки, которые разработчику следует избегать.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Состояния гонки в методе Dispose  
 Если метод **Dispose** класса (Дополнительные сведения см. в разделе [сборка мусора](../garbage-collection/index.md)) не синхронизирован, возможно, что код очистки внутри **Dispose** может быть запущен более одного раза, как показано в следующем примере.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()
{  
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Так как эта реализация **Dispose** не синхронизирована, можно `Cleanup` вызвать сначала один поток, а затем — `_myObj` **значение NULL**для второго потока. Является ли это нарушением безопасности, зависит от того, что происходит при `Cleanup` выполнении кода. Основной проблемой с несинхронизированными реализациями **Dispose** является использование таких дескрипторов ресурсов, как файлы. Неправильное удаление может привести к тому, что не будет использован некорректный маркер, что часто приводит к уязвимостям безопасности.  
  
## <a name="race-conditions-in-constructors"></a>Состояния гонки в конструкторах  
 В некоторых приложениях другие потоки могут обращаться к членам класса, прежде чем их конструкторы класса будут полностью запущены. Следует проверить все конструкторы классов, чтобы убедиться в отсутствии проблем безопасности, если это необходимо, или синхронизировать потоки при необходимости.  
  
## <a name="race-conditions-with-cached-objects"></a>Состояния гонки с кэшированными объектами  
 Код, который кэширует сведения о безопасности или использует операцию [утверждения](../../framework/misc/using-the-assert-method.md) управления доступом для кода, может также быть уязвимым для состояний гонки, если другие части класса не синхронизированы должным образом, как показано в следующем примере.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()
{  
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
    {  
        DoSomethingTrusted();  
    }  
    else
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 Если есть другие пути `DoOtherWork` , которые можно вызвать из другого потока с тем же объектом, недоверенный вызывающий объект может потребовать поочередного запроса.  
  
 Если ваш код кэширует сведения о безопасности, обязательно ознакомьтесь с этой уязвимостью.  
  
## <a name="race-conditions-in-finalizers"></a>Состояния гонки в методах завершения  
 Состояния гонки могут также возникать в объекте, который ссылается на статический или неуправляемый ресурс, который затем освобождается в методе завершения. Если несколько объектов совместно используют ресурс, который управляется в методе завершения класса, объекты должны синхронизировать весь доступ к этому ресурсу.  
  
## <a name="see-also"></a>См. также

- [Правила написания безопасного кода](secure-coding-guidelines.md)
