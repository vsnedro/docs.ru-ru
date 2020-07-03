---
title: проверка подлинности NTLM и Kerberos
description: Узнайте, как работает стандартная проверка подлинности NTLM и проверка подлинности Kerberos для приложения .NET Framework,а также и нестандартной проверке подлинности NTLM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
ms.openlocfilehash: d91ebca084d84acd4eb8facb82ff08679ec35cd0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502240"
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="1fff8-103">проверка подлинности NTLM и Kerberos</span><span class="sxs-lookup"><span data-stu-id="1fff8-103">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="1fff8-104">При проверке подлинности NTLM и Kerberos по умолчанию используются учетные данные пользователя Microsoft Windows NT, связанные с вызывающим приложением, для проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="1fff8-104">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="1fff8-105">Если используется отличная от установленной по умолчанию проверка подлинности NTLM, приложение устанавливает тип проверки подлинности NTLM и использует объект <xref:System.Net.NetworkCredential> для передачи имени пользователя, пароля и домена узлу, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1fff8-105">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 <span data-ttu-id="1fff8-106">Приложения, которым требуется подключение к службам Интернета с использованием учетных данных пользователя приложения, могут использовать для этого учетные данные пользователя по умолчанию, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1fff8-106">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 <span data-ttu-id="1fff8-107">Модуль проверки подлинности с согласованием определяет, использует ли удаленный сервер проверку подлинности NTLM или Kerberos, после чего отправляет соответствующий ответ.</span><span class="sxs-lookup"><span data-stu-id="1fff8-107">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fff8-108">Проверка подлинности NTLM не работает через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="1fff8-108">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fff8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1fff8-109">See also</span></span>

- [<span data-ttu-id="1fff8-110">Обычная и дайджест-проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="1fff8-110">Basic and Digest Authentication</span></span>](basic-and-digest-authentication.md)
- [<span data-ttu-id="1fff8-111">Проверка подлинности в Интернете</span><span class="sxs-lookup"><span data-stu-id="1fff8-111">Internet Authentication</span></span>](internet-authentication.md)
