---
title: Расширяемость каналов
ms.date: 03/30/2017
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
ms.openlocfilehash: 1a734c305e2a6f2fc759647ab5bdf380f7c7eeee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253846"
---
# <a name="channels-extensibility"></a><span data-ttu-id="d29c7-102">Расширяемость каналов</span><span class="sxs-lookup"><span data-stu-id="d29c7-102">Channels Extensibility</span></span>

<span data-ttu-id="d29c7-103">В этом разделе содержатся образцы, демонстрирующие пользовательские каналы.</span><span class="sxs-lookup"><span data-stu-id="d29c7-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d29c7-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d29c7-104">In This Section</span></span>  

 [<span data-ttu-id="d29c7-105">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="d29c7-105">Local Channel</span></span>](local-channel.md)  
 <span data-ttu-id="d29c7-106">Демонстрирует локальный канал, канал транспорта WCF, который используется для связи в пределах одного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d29c7-106">Demonstrates the local channel, a WCF transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="d29c7-107">Надежный защищенный профиль</span><span class="sxs-lookup"><span data-stu-id="d29c7-107">Reliable Secure Profile</span></span>](reliable-secure-profile.md)  
 <span data-ttu-id="d29c7-108">Демонстрирует, как создать WCF и надежный защищенный профиль (RSP).</span><span class="sxs-lookup"><span data-stu-id="d29c7-108">Demonstrates how to compose WCF and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="d29c7-109">Настраиваемый диспетчер каналов</span><span class="sxs-lookup"><span data-stu-id="d29c7-109">Custom Channel Dispatcher</span></span>](custom-channel-dispatcher.md)  
 <span data-ttu-id="d29c7-110">Демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла.</span><span class="sxs-lookup"><span data-stu-id="d29c7-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="d29c7-111">Фрагментирование канала</span><span class="sxs-lookup"><span data-stu-id="d29c7-111">Chunking Channel</span></span>](chunking-channel.md)  
 <span data-ttu-id="d29c7-112">Показывает, как ограничить объем памяти, используемой для буферизации больших сообщений, отправляемых с помощью WCF.</span><span class="sxs-lookup"><span data-stu-id="d29c7-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using WCF.</span></span>
  
 [<span data-ttu-id="d29c7-113">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="d29c7-113">HttpCookieSession</span></span>](httpcookiesession.md)  
 <span data-ttu-id="d29c7-114">Демонстрирует, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="d29c7-114">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="d29c7-115">Пользовательский перехватчик сообщений</span><span class="sxs-lookup"><span data-stu-id="d29c7-115">Custom Message Interceptor</span></span>](custom-message-interceptor.md)  
 <span data-ttu-id="d29c7-116">Показано, как реализовать пользовательский элемент привязки, который создает фабрики и прослушиватели каналов для перехвата всех входящих и исходящих сообщений в определенной точке стека времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="d29c7-116">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
