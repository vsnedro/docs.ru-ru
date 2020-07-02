---
ms.openlocfilehash: 3eab96149be1e40d528cfd552bbe05ca766cf4e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620594"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="190c5-101">Метод System.Threading.Tasks.Task больше не создает исключение ObjectDisposedException после удаления объекта</span><span class="sxs-lookup"><span data-stu-id="190c5-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="190c5-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="190c5-102">Details</span></span>

<span data-ttu-id="190c5-103">За исключением <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> методы <xref:System.Threading.Tasks.Task?displayProperty=fullName> больше не вызывают исключение <xref:System.ObjectDisposedException?displayProperty=fullName> после удаления объекта. Это изменение поддерживает использование кэшированных задач.</span><span class="sxs-lookup"><span data-stu-id="190c5-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="190c5-104">Например, метод может возвратить кэшированную задачу для представления уже выполненной операции вместо выделения новой задачи.</span><span class="sxs-lookup"><span data-stu-id="190c5-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="190c5-105">В предыдущих версиях платформы .NET Framework это было невозможно, поскольку любой потребитель задачи мог удалить ее, что делало ее непригодной для использования.</span><span class="sxs-lookup"><span data-stu-id="190c5-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="190c5-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="190c5-106">Suggestion</span></span>

<span data-ttu-id="190c5-107">Имейте в виду, что методы Task больше не могут создавать исключения <xref:System.ObjectDisposedException?displayProperty=fullName> при удалении объекта.</span><span class="sxs-lookup"><span data-stu-id="190c5-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="190c5-108">Если приложение зависело от этого исключения, чтобы знать, что задача была удалена, его необходимо обновить, чтобы явно проверять состояние задачи с помощью <xref:System.Threading.Tasks.Task.Status>.</span><span class="sxs-lookup"><span data-stu-id="190c5-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="190c5-109">name</span><span class="sxs-lookup"><span data-stu-id="190c5-109">Name</span></span>    | <span data-ttu-id="190c5-110">Значение</span><span class="sxs-lookup"><span data-stu-id="190c5-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="190c5-111">Область</span><span class="sxs-lookup"><span data-stu-id="190c5-111">Scope</span></span>   |<span data-ttu-id="190c5-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="190c5-112">Minor</span></span>|
|<span data-ttu-id="190c5-113">Version</span><span class="sxs-lookup"><span data-stu-id="190c5-113">Version</span></span>|<span data-ttu-id="190c5-114">4.5</span><span class="sxs-lookup"><span data-stu-id="190c5-114">4.5</span></span>|
|<span data-ttu-id="190c5-115">Type</span><span class="sxs-lookup"><span data-stu-id="190c5-115">Type</span></span>|<span data-ttu-id="190c5-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="190c5-116">Runtime</span></span>|
