---
title: Олицетворение и возвращение
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 7eecc7d6cb3fa4cc1c1bd971d36f9d3ca47a7144
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555684"
---
# <a name="impersonating-and-reverting"></a>Олицетворение и возвращение

> [!NOTE]
> Эта статья относится к Windows.
>
> Сведения о ASP.NET Core см. в разделе [ASP.NET Core Security](/aspnet/core/security/).

Иногда может потребоваться получить токен учетной записи Windows для олицетворения учетной записи Windows. Например, приложению ASP.NET может требоваться действовать от лица разных пользователей в разное время. Ваше приложение может принять токен, представляющий администратора, из служб IIS, выполнить олицетворение этого пользователя, выполнить операцию и вернуться к предыдущему удостоверению. Далее он может принять токен из служб IIS, который представляет пользователя с меньшим набором прав, выполнить некую операцию и снова вернуться.  
  
 В ситуациях, когда приложение должно олицетворять учетную запись Windows, не подключенную к текущему потоку службами IIS, необходимо получить токен для этой учетной записи и с его помощью активировать эту учетную запись. Это можно сделать, выполнив следующие задачи.  
  
1. Получите токен учетной записи для конкретного пользователя путем вызова неуправляемого метода **LogonUser**. Этот метод отсутствует в библиотеке базовых классов .NET, но находится в неуправляемой **advapi32.dll**. Доступ к методам в неуправляемом коде является сложной операцией и выходит за рамки данного обсуждения. Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../framework/interop/index.md). Дополнительные сведения о методе **LogonUser** и библиотеке **advapi32.dll** см. в документации Platform SDK.  
  
2. Создайте новый экземпляр класса **WindowsIdentity**, передав токен. Следующий код демонстрирует этот вызов, где `hToken` представляет токен Windows.  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. Начните олицетворение, создав новый экземпляр класса <xref:System.Security.Principal.WindowsImpersonationContext> и инициализировав его с помощью метода <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> инициализации класса, как показано в следующем коде.  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. Если это олицетворение больше не требуется, вызовите метод <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> для отмены олицетворения, как показано в следующем коде.  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 Если доверенный код уже подключил <xref:System.Security.Principal.WindowsPrincipal> объект к потоку, можно вызвать метод экземпляра **impersonate**, который не принимает маркер учетной записи. Обратите внимание, что это целесообразно только в том случае, если объект **WindowsPrincipal** в потоке представляет пользователя, отличного от того, под которым выполняется процесс. Например, такая ситуация может возникнуть при использовании ASP.NET с включенной проверкой подлинности Windows и отключенным олицетворением. В этом случае процесс выполняется под учетной записью, настроенной в IIS, тогда как текущий участник представляет пользователя Windows, который обращается к странице.  
  
 Обратите внимание, что ни **олицетворение** , ни **Отмена** изменений не изменяет объект **Principal** ( <xref:System.Security.Principal.IPrincipal> ), связанный с текущим контекстом вызова. Вместо этого при олицетворении и возврате изменяется маркер, связанный с текущим процессом операционной системы.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [Объекты Principal и Identity](principal-and-identity-objects.md)
- [Взаимодействие с неуправляемым кодом](../../framework/interop/index.md)
- [Безопасность ASP.NET Core](/aspnet/core/security/)
