---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293992"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="a4a58-102">Привязки WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="a4a58-102">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="a4a58-103">В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.</span><span class="sxs-lookup"><span data-stu-id="a4a58-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="a4a58-104">Привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a4a58-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="a4a58-105">Имя привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a4a58-105">Default Binding Name</span></span>|<span data-ttu-id="a4a58-106">Создание привязки</span><span class="sxs-lookup"><span data-stu-id="a4a58-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="a4a58-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a4a58-107">mexHttpBinding</span></span>|<span data-ttu-id="a4a58-108">Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="a4a58-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="a4a58-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="a4a58-109">mexHttpsBinding</span></span>|<span data-ttu-id="a4a58-110">Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="a4a58-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="a4a58-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="a4a58-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="a4a58-112">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4a58-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="a4a58-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="a4a58-113">mexTcpBinding</span></span>|<span data-ttu-id="a4a58-114">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4a58-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
