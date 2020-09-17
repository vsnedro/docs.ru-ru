---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065111"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a><span data-ttu-id="59e6d-101">CryptoStream.Dispose преобразует окончательный блок только при записи</span><span class="sxs-lookup"><span data-stu-id="59e6d-101">CryptoStream.Dispose transforms final block only when writing</span></span>

<span data-ttu-id="59e6d-102">Метод <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>, который используется для завершения операций `CryptoStream`, больше не пытается преобразовать окончательный блок при чтении.</span><span class="sxs-lookup"><span data-stu-id="59e6d-102">The <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> method, which is used to finish `CryptoStream` operations, no longer attempts to transform the final block when reading.</span></span>

#### <a name="change-description"></a><span data-ttu-id="59e6d-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="59e6d-103">Change description</span></span>

<span data-ttu-id="59e6d-104">В предыдущих версиях .NET, если пользователь выполнил неполное чтение при использовании <xref:System.Security.Cryptography.CryptoStream> в режиме <xref:System.Security.Cryptography.CryptoStreamMode.Read>, метод <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> может вызвать исключение (например, при использовании AES с заполнением).</span><span class="sxs-lookup"><span data-stu-id="59e6d-104">In previous .NET versions, if a user performed an incomplete read when using <xref:System.Security.Cryptography.CryptoStream> in <xref:System.Security.Cryptography.CryptoStreamMode.Read> mode, the <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> method could throw an exception (for example, when using AES with padding).</span></span> <span data-ttu-id="59e6d-105">Возникло исключение, так как предпринята попытка преобразования последнего блока, но данные были неполными.</span><span class="sxs-lookup"><span data-stu-id="59e6d-105">The exception was thrown because the final block was attempted to be transformed but the data was incomplete.</span></span>

<span data-ttu-id="59e6d-106">В .NET Core 3.0 и более поздних версиях <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> больше не пытается преобразовать окончательный блок при чтении, что позволяет выполнять неполные операции чтения.</span><span class="sxs-lookup"><span data-stu-id="59e6d-106">In .NET Core 3.0 and later versions, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no longer tries to transform the final block when reading, which allows for incomplete reads.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="59e6d-107">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="59e6d-107">Reason for change</span></span>

<span data-ttu-id="59e6d-108">Это изменение включает неполные операции чтения из потока шифрования при отмене сетевой операции без необходимости перехватывать исключение.</span><span class="sxs-lookup"><span data-stu-id="59e6d-108">This change enables incomplete reads from the crypto stream when a network operation is cancelled, without the need to catch an exception.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="59e6d-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59e6d-109">Version introduced</span></span>

<span data-ttu-id="59e6d-110">3.0</span><span class="sxs-lookup"><span data-stu-id="59e6d-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="59e6d-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="59e6d-111">Recommended action</span></span>

<span data-ttu-id="59e6d-112">Это изменение не затрагивает большинство приложений.</span><span class="sxs-lookup"><span data-stu-id="59e6d-112">Most apps should not be affected by this change.</span></span>

<span data-ttu-id="59e6d-113">Если приложение ранее перехватило исключение в случае неполного чтения, этот блок `catch` можно удалить.</span><span class="sxs-lookup"><span data-stu-id="59e6d-113">If your application previously caught an exception in case of an incomplete read, you can delete that `catch` block.</span></span>
<span data-ttu-id="59e6d-114">Если приложение использовало преобразование окончательного блока в сценариях хэширования, перед уничтожением может потребоваться считать весь поток.</span><span class="sxs-lookup"><span data-stu-id="59e6d-114">If your app used transforming of the final block in hashing scenarios, you might need to ensure that the entire stream is read before it's disposed.</span></span>

#### <a name="category"></a><span data-ttu-id="59e6d-115">Категория</span><span class="sxs-lookup"><span data-stu-id="59e6d-115">Category</span></span>

<span data-ttu-id="59e6d-116">Шифрование</span><span class="sxs-lookup"><span data-stu-id="59e6d-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="59e6d-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="59e6d-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
