---
ms.openlocfilehash: 7f8f97adcca7e66fa5756212bb977daadd92b8b6
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497380"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="b2c17-101">Теперь метод X509Certificate2.ToString(Boolean) не создает исключение, когда .NET не удается обработать сертификат</span><span class="sxs-lookup"><span data-stu-id="b2c17-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="b2c17-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b2c17-102">Details</span></span>

<span data-ttu-id="b2c17-103">В .NET Framework 4.5.2 и более ранних версиях этот метод создавал исключение, если значение <code>true</code> передавалось в параметр verbose и были установлены сертификаты, не поддерживаемые .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b2c17-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="b2c17-104">Теперь метод будет выполняться успешно и возвращать допустимую строку, в которой пропущены недоступные части сертификата.</span><span class="sxs-lookup"><span data-stu-id="b2c17-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b2c17-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="b2c17-105">Suggestion</span></span>

<span data-ttu-id="b2c17-106">Любой код, зависящий от <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>, следует обновить для ожидания того, что в некоторых случаях, когда ранее API возвращал исключение, в возвращаемой строке могут отсутствовать некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения).</span><span class="sxs-lookup"><span data-stu-id="b2c17-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="b2c17-107">name</span><span class="sxs-lookup"><span data-stu-id="b2c17-107">Name</span></span>    | <span data-ttu-id="b2c17-108">Значение</span><span class="sxs-lookup"><span data-stu-id="b2c17-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b2c17-109">Область</span><span class="sxs-lookup"><span data-stu-id="b2c17-109">Scope</span></span>   |<span data-ttu-id="b2c17-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="b2c17-110">Edge</span></span>|
|<span data-ttu-id="b2c17-111">Version</span><span class="sxs-lookup"><span data-stu-id="b2c17-111">Version</span></span>|<span data-ttu-id="b2c17-112">4.6</span><span class="sxs-lookup"><span data-stu-id="b2c17-112">4.6</span></span>|
|<span data-ttu-id="b2c17-113">Type</span><span class="sxs-lookup"><span data-stu-id="b2c17-113">Type</span></span>|<span data-ttu-id="b2c17-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b2c17-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b2c17-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b2c17-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)`

-->
