---
title: Веб-разрешения и разрешения сокетов
description: Узнайте, как классы WebPermission и SocketPermission обеспечивают безопасность в Интернете при использовании пространства имен System.Net в .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: 08ae360e8097f7281631da2a3f9846994dfbf5b6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501902"
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="93a63-103">Веб-разрешения и разрешения сокетов</span><span class="sxs-lookup"><span data-stu-id="93a63-103">Web and Socket Permissions</span></span>
<span data-ttu-id="93a63-104">Безопасность приложений, использующих пространство имен <xref:System.Net>, в Интернете обеспечивается классами <xref:System.Net.WebPermission> и <xref:System.Net.SocketPermission>.</span><span class="sxs-lookup"><span data-stu-id="93a63-104">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="93a63-105">Класс **WebPermission** определяет право приложения на запрос данных из универсального кода ресурса (URI) или предоставления кода URI в Интернете.</span><span class="sxs-lookup"><span data-stu-id="93a63-105">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="93a63-106">Класс **SocketPermission** определяет право приложения на использование <xref:System.Net.Sockets.Socket> для приема данных через локальный порт или на связь с удаленными устройствами с помощью транспортного протокола по другому адресу в соответствии с узлом, номером порта и транспортным протоколом сокета.</span><span class="sxs-lookup"><span data-stu-id="93a63-106">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="93a63-107">Выбор используемого класса разрешений зависит от типа приложения.</span><span class="sxs-lookup"><span data-stu-id="93a63-107">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="93a63-108">Приложения, применяющие класс <xref:System.Net.WebRequest> и его потомки, должны использовать класс **WebPermission** для управления разрешениями.</span><span class="sxs-lookup"><span data-stu-id="93a63-108">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="93a63-109">Приложения, применяющие доступ на уровне сокета, должны использовать класс **SocketPermission** для управления разрешениями.</span><span class="sxs-lookup"><span data-stu-id="93a63-109">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="93a63-110">Классы **WebPermission** и **SocketPermission** определяют два разрешения: на прием и подключение.</span><span class="sxs-lookup"><span data-stu-id="93a63-110">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="93a63-111">Разрешение на прием позволяет приложению отвечать на входящие запросы подключения от другой стороны.</span><span class="sxs-lookup"><span data-stu-id="93a63-111">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="93a63-112">Разрешение на подключение позволяет приложению инициировать соединение с другой стороной.</span><span class="sxs-lookup"><span data-stu-id="93a63-112">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="93a63-113">Для экземпляров **SocketPermission** разрешение на прием означает, что приложение может принимать входящие подключения по локальному адресу транспорта. Разрешение на подключение означает, что приложение может подключаться к определенному удаленному (или локальному) адресу транспорта.</span><span class="sxs-lookup"><span data-stu-id="93a63-113">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="93a63-114">Для экземпляров **WebPermission** разрешение на прием означает, что приложение может экспортировать код URI, контролируемый экземпляром **WebPermission**, во внешнюю сеть. Разрешение на подключение означает, что приложение может получать доступ к этому коду URI (удаленному или локальному).</span><span class="sxs-lookup"><span data-stu-id="93a63-114">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a63-115">См. также</span><span class="sxs-lookup"><span data-stu-id="93a63-115">See also</span></span>

- [<span data-ttu-id="93a63-116">Безопасность</span><span class="sxs-lookup"><span data-stu-id="93a63-116">Security</span></span>](../../standard/security/index.md)
- [<span data-ttu-id="93a63-117">Безопасность в сетевом программировании</span><span class="sxs-lookup"><span data-stu-id="93a63-117">Security in Network Programming</span></span>](security-in-network-programming.md)
