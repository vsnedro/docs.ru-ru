---
title: Раздел конфигурации Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 8a6f13da9bf05d87c45d86a09261d0c7245f5b00
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546912"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="85380-102">Раздел конфигурации Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85380-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="85380-103">Параметры конфигурации Windows Forms позволяют приложению Windows Forms хранить и извлекать сведения о настроенных параметрах приложения, таких как поддержка нескольких мониторов, поддержка высокого разрешения (DPI) и другие предопределенные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="85380-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="85380-104">Параметры конфигурации приложения Windows Forms хранятся в элементе `System.Windows.Forms.ApplicationConfigurationSection` файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="85380-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="85380-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85380-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85380-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="85380-106">Attributes and elements</span></span>

<span data-ttu-id="85380-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85380-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="85380-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85380-108">Attributes</span></span>

<span data-ttu-id="85380-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85380-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="85380-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85380-110">Child elements</span></span>

<span data-ttu-id="85380-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="85380-111">Element</span></span>  |<span data-ttu-id="85380-112">Описание</span><span class="sxs-lookup"><span data-stu-id="85380-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="85380-113">Добавляет ключ параметра конфигурации с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="85380-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="85380-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85380-114">Parent elements</span></span>

<span data-ttu-id="85380-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="85380-115">Element</span></span>  |<span data-ttu-id="85380-116">Описание</span><span class="sxs-lookup"><span data-stu-id="85380-116">Description</span></span> |
---------|---------|
[\<configuration>](../configuration-element.md) | <span data-ttu-id="85380-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="85380-117">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="85380-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="85380-118">Remarks</span></span>

<span data-ttu-id="85380-119">Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85380-119">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="85380-120">`<System.Windows.Forms.ApplicationConfigurationSection>`Элемент может включать один или несколько дочерних [`<add>`](windows-forms-add-configuration-element.md) элементов, каждый из которых определяет конкретный параметр конфигурации.</span><span class="sxs-lookup"><span data-stu-id="85380-120">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="85380-121">См. также</span><span class="sxs-lookup"><span data-stu-id="85380-121">See also</span></span>

- [<span data-ttu-id="85380-122">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="85380-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="85380-123">Поддержка высокого DPI в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85380-123">High DPI Support in Windows Forms</span></span>](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
