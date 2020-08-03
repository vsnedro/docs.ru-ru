---
title: Практическое руководство. Возобновление работы службы Windows (Visual Basic)
description: Узнайте, как использовать компонент ServiceController для возобновления работы службы Windows (например, службы администрирования IIS) на локальном компьютере с Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: 2a04e330ea7dc37552053b2a7915909c011727f8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925791"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="ed6ad-103">Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed6ad-103">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="ed6ad-104">В этом примере для возобновления работы службы администрирования IIS на локальном компьютере используется компонент <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed6ad-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ed6ad-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="ed6ad-106">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ed6ad-107">В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Службы Windows**.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="ed6ad-108">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="ed6ad-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ed6ad-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ed6ad-109">Compiling the Code</span></span>  
 <span data-ttu-id="ed6ad-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ed6ad-110">This example requires:</span></span>  
  
- <span data-ttu-id="ed6ad-111">Ссылка в проекте на System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="ed6ad-112">Доступ к членам пространства имен <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="ed6ad-113">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="ed6ad-114">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="ed6ad-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ed6ad-115">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ed6ad-115">Robust Programming</span></span>  
 <span data-ttu-id="ed6ad-116">Свойство <xref:System.ServiceProcess.ServiceController.MachineName%2A> класса <xref:System.ServiceProcess.ServiceController> — это по умолчанию локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="ed6ad-117">Чтобы указать ссылку на службы Windows на другом компьютере, укажите в свойстве <xref:System.ServiceProcess.ServiceController.MachineName%2A> имя другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="ed6ad-118">Пока контроллер службы находится в состоянии <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, вызывать для службы метод <xref:System.ServiceProcess.ServiceController.Continue%2A> нельзя.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-118">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="ed6ad-119">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="ed6ad-119">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ed6ad-120">Не удалось возобновить работу службы.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-120">The service cannot be resumed.</span></span> <span data-ttu-id="ed6ad-121">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="ed6ad-121">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="ed6ad-122">Произошла ошибка при обращении к API-интерфейсу системы.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-122">An error occurred when accessing a system API.</span></span> <span data-ttu-id="ed6ad-123">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="ed6ad-123">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ed6ad-124">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed6ad-124">.NET Framework Security</span></span>  
 <span data-ttu-id="ed6ad-125">Чтобы ограничить управление службами на компьютере, с помощью перечисления <xref:System.ServiceProcess.ServiceControllerPermissionAccess> настройте в классе <xref:System.ServiceProcess.ServiceControllerPermission> необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-125">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="ed6ad-126">Чтобы ограничить доступ к сведениям о службе, с помощью перечисления <xref:System.Security.Permissions.PermissionState> настройте в классе <xref:System.Security.Permissions.SecurityPermission> необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="ed6ad-126">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6ad-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ed6ad-127">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="ed6ad-128">Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed6ad-128">How to: Pause a Windows Service (Visual Basic)</span></span>](how-to-pause-a-windows-service-visual-basic.md)
