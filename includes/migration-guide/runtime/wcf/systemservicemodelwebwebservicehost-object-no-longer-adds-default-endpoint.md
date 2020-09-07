---
ms.openlocfilehash: 0c3876d30a80501a89f3a37ce24e2f71122c1b44
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496165"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="6ead3-101">Объект System.ServiceModel.Web.WebServiceHost больше не добавляет конечную точку по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6ead3-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="6ead3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6ead3-102">Details</span></span>

<span data-ttu-id="6ead3-103">Объект <xref:System.ServiceModel.Web.WebServiceHost> теперь не добавляет конечную точку по умолчанию, если в коде приложения явным образом добавлена конечная точка.</span><span class="sxs-lookup"><span data-stu-id="6ead3-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6ead3-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="6ead3-104">Suggestion</span></span>

<span data-ttu-id="6ead3-105">Если пользователи хотят иметь возможность подключаться к конечной точке по умолчанию и другие явные конечные точки были добавлены в <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, конечные точки по умолчанию необходимо также добавить явным образом (с помощью <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="6ead3-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="6ead3-106">name</span><span class="sxs-lookup"><span data-stu-id="6ead3-106">Name</span></span>    | <span data-ttu-id="6ead3-107">Значение</span><span class="sxs-lookup"><span data-stu-id="6ead3-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6ead3-108">Область</span><span class="sxs-lookup"><span data-stu-id="6ead3-108">Scope</span></span>   |<span data-ttu-id="6ead3-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="6ead3-109">Minor</span></span>|
|<span data-ttu-id="6ead3-110">Version</span><span class="sxs-lookup"><span data-stu-id="6ead3-110">Version</span></span>|<span data-ttu-id="6ead3-111">4.5</span><span class="sxs-lookup"><span data-stu-id="6ead3-111">4.5</span></span>|
|<span data-ttu-id="6ead3-112">Type</span><span class="sxs-lookup"><span data-stu-id="6ead3-112">Type</span></span>|<span data-ttu-id="6ead3-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6ead3-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6ead3-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6ead3-114">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`

-->
