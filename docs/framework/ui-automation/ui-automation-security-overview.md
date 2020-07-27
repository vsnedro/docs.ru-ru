---
title: Общие сведения о безопасности модели автоматизации пользовательского интерфейса
description: Ознакомьтесь с обзором модели безопасности для службы автоматизации пользовательского интерфейса Майкрософт. Общие сведения об управлении учетными записями пользователей, задачах, требующих более высоких привилегий, и файлах манифеста.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: d483f282db8ce8e5653d6d83361fa44df05f63f5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163150"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="9795f-104">Общие сведения о безопасности модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9795f-104">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="9795f-105">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="9795f-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9795f-106">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="9795f-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="9795f-107">В этом обзоре описывается модель безопасности [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="9795f-107">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="9795f-108">контроль учетных записей</span><span class="sxs-lookup"><span data-stu-id="9795f-108">User Account Control</span></span>

<span data-ttu-id="9795f-109">Безопасность является важным аспектом Windows Vista, и в других нововведениях пользователи могут работать как стандартные пользователи (без прав администратора), не требуя от них блокирования запуска приложений и служб, которым требуются более высокие привилегии.</span><span class="sxs-lookup"><span data-stu-id="9795f-109">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="9795f-110">В Windows Vista большинство приложений предоставляются с помощью стандартного или административного маркера.</span><span class="sxs-lookup"><span data-stu-id="9795f-110">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="9795f-111">Если приложение не идентифицировано как административное приложение, оно запускается в качестве стандартного приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9795f-111">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="9795f-112">Перед запуском приложения, идентифицированного как административное, Windows Vista запрашивает у пользователя разрешение на запуск приложения с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="9795f-112">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="9795f-113">Запрос на продолжение отображается по умолчанию, даже если пользователь является членом локальной группы администраторов, так как администраторы выполняют запуск как обычные пользователи, пока приложение или системный компонент, которому требуются административные учетные данные, не запросит разрешение на запуск.</span><span class="sxs-lookup"><span data-stu-id="9795f-113">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="9795f-114">Задачи, требующие повышенных привилегий</span><span class="sxs-lookup"><span data-stu-id="9795f-114">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="9795f-115">Когда пользователь пытается выполнить задачу, для которой требуются права администратора, в Windows Vista появится диалоговое окно с запросом на продолжение.</span><span class="sxs-lookup"><span data-stu-id="9795f-115">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="9795f-116">Это диалоговое окно защищено от межпроцессного взаимодействия, чтобы вредоносные программы не могли имитировать ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="9795f-116">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="9795f-117">Аналогичным образом экран входа в систему обычно недоступен для других процессов.</span><span class="sxs-lookup"><span data-stu-id="9795f-117">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="9795f-118">Клиенты автоматизации пользовательского интерфейса должны взаимодействовать с другими процессами, а некоторые из них могут запускаться с повышенным уровнем привилегий.</span><span class="sxs-lookup"><span data-stu-id="9795f-118">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="9795f-119">Клиентам также может требоваться доступ к диалоговым окнам системы, которые обычно невидимы для других процессов.</span><span class="sxs-lookup"><span data-stu-id="9795f-119">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="9795f-120">Таким образом, клиенты [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны быть доверенными для системы и должны запускаться со специальными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="9795f-120">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="9795f-121">Чтобы быть доверенными для взаимодействия с приложениями, работающими на более высоком уровне привилегий, приложения должны быть подписаны.</span><span class="sxs-lookup"><span data-stu-id="9795f-121">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="9795f-122">Файлы манифеста</span><span class="sxs-lookup"><span data-stu-id="9795f-122">Manifest Files</span></span>

<span data-ttu-id="9795f-123">Чтобы получить доступ к защищенному системному ИНТЕРФЕЙСу, приложения должны быть построены с помощью файла манифеста, который включает `uiAccess` атрибут в `requestedExecutionLevel` тег следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9795f-123">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="9795f-124">Значение атрибута `level` в этом коде приводится только для примера.</span><span class="sxs-lookup"><span data-stu-id="9795f-124">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="9795f-125">`uiAccess`по умолчанию имеет значение false; Это значит, что если атрибут не указан или для сборки нет манифеста, приложение не сможет получить доступ к защищенному пользовательскому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="9795f-125">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
