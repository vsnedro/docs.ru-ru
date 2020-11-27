---
title: Параметр кодировки экземпляров
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 416394eb346a7c82385da32a89bd54179b255cd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279900"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="ed77e-102">Параметр кодировки экземпляров</span><span class="sxs-lookup"><span data-stu-id="ed77e-102">Instance Encoding Option</span></span>

<span data-ttu-id="ed77e-103">Свойство **параметра кодировки экземпляра** хранилища экземпляров рабочих процессов SQL позволяет указать, следует ли поставщику сохраняемости SQL сжимать сведения о состоянии экземпляра рабочего процесса с помощью алгоритма GZip перед сохранением информации в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="ed77e-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="ed77e-104">Допустимы значения этого свойства GZip и None.</span><span class="sxs-lookup"><span data-stu-id="ed77e-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="ed77e-105">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="ed77e-105">The default value is None.</span></span> <span data-ttu-id="ed77e-106">Эти варианты описаны в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="ed77e-106">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="ed77e-107">**Gzip**.</span><span class="sxs-lookup"><span data-stu-id="ed77e-107">**GZip**.</span></span> <span data-ttu-id="ed77e-108">Поставщик сохраняемости кодирует сведения о состоянии с использованием алгоритма сжатия GZip перед их сохранением в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="ed77e-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="ed77e-109">**Нет**.</span><span class="sxs-lookup"><span data-stu-id="ed77e-109">**None**.</span></span> <span data-ttu-id="ed77e-110">Поставщик сохраняемости не сжимает сведения о состоянии перед их сохранением в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="ed77e-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="ed77e-111">При кодировании и сжатии сведений о состоянии экземпляра рабочего процесса с использованием экземпляра GZip снижается потребление памяти базой данных SQL, а также снижается нагрузка на сеть (в случае если база данных расположена на другом компьютере в сети, а не на компьютере, на котором запущена служба рабочего процесса).</span><span class="sxs-lookup"><span data-stu-id="ed77e-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="ed77e-112">Общее руководство заключается в том, чтобы задать для свойства **параметра кодировки экземпляра** значение **None** , если экземпляр рабочего процесса имеет немалое состояние.</span><span class="sxs-lookup"><span data-stu-id="ed77e-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
