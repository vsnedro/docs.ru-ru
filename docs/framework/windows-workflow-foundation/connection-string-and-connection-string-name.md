---
title: Строка соединения и имя строки соединения
ms.date: 03/30/2017
ms.assetid: 473e7a3c-c88a-4a01-914a-bea82ba42866
ms.openlocfilehash: 5352dbac09565e872493581a2809409b156d1300
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248868"
---
# <a name="connection-string-and-connection-string-name"></a><span data-ttu-id="2f626-102">Строка соединения и имя строки соединения</span><span class="sxs-lookup"><span data-stu-id="2f626-102">Connection String and Connection String Name</span></span>

<span data-ttu-id="2f626-103">Свойство **строки подключения** указывает строку подключения, которую хранилище экземпляров рабочих процессов SQL должно использовать для подключения к базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="2f626-103">**Connection String** property specifies the connection string that the SQL Workflow Instance Store should use to connect to a persistence database.</span></span> <span data-ttu-id="2f626-104">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2f626-104">This parameter is an optional parameter.</span></span> <span data-ttu-id="2f626-105">Свойство " **имя строки подключения** " указывает имя именованной строки подключения, которое должно использоваться хранилищем экземпляров рабочих процессов SQL для подключения к базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="2f626-105">**Connection String Name** property specifies the name of the named connection string that the SQL Workflow Instance Store should use to connect to the persistence database.</span></span> <span data-ttu-id="2f626-106">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2f626-106">This parameter is an optional parameter.</span></span> <span data-ttu-id="2f626-107">Если не нужно, чтобы хранилище экземпляров рабочих процессов SQL использовало именованную строку подключения **дефаултсклворкфловинстанцестореконнектионстринг**, необходимо указать значение для свойства имя строки подключения или для свойства строки соединения.</span><span class="sxs-lookup"><span data-stu-id="2f626-107">You should specify a value for the Connection String Name property or the Connection String property if you do not want the SQL Workflow Instance Store to use the default named connection string **DefaultSqlWorkflowInstanceStoreConnectionString**.</span></span>
