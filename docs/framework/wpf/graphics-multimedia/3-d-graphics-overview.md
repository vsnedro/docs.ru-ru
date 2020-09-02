---
title: Обзор трехмерной графики
description: Познакомьтесь с трехмерной графикой в Windows Presentation Foundation (WPF), чтобы рисовать, преобразовывать и анимировать трехмерную графику как в разметке, так и в процедурном коде.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: aa4f45ac426c59b829b6be9e63e8f0ed50512661
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358925"
---
# <a name="3d-graphics-overview"></a>Обзор трехмерной графики
<a name="introduction"></a> Трехмерные функции в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяют разработчикам рисовать, преобразовывать и анимировать трехмерную графику как в разметке, так и в процедурном коде. Разработчики могут комбинировать 2D-и трехмерные графики для создания насыщенных элементов управления, представления сложных иллюстраций данных или улучшения взаимодействия с пользователем интерфейса приложения. Трехмерная поддержка в не [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предназначена для предоставления полнофункциональной платформы для разработки игр. В этом разделе представлен обзор трехмерных функций в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графической системе.  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>Трехмерный в двухмерном контейнере  
 содержимое трехмерной графики в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] инкапсулируется в элемент, <xref:System.Windows.Controls.Viewport3D> который может участвовать в структуре двумерного элемента. Графическая система обрабатывает <xref:System.Windows.Controls.Viewport3D> как двумерный визуальный элемент, как и многие другие в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . <xref:System.Windows.Controls.Viewport3D> функции в виде окна — окна просмотра — трехмерной сцены. Точнее, это поверхность, на которой проецируется трехмерная сцена.  
  
 В традиционном двухмерном приложении используйте, <xref:System.Windows.Controls.Viewport3D> как и другой элемент контейнера, например Grid или Canvas.  Несмотря на то, что можно использовать <xref:System.Windows.Controls.Viewport3D> с другими 2D-объектами на одном графе сцены, нельзя сочетать 2D-и трехмерные объекты в <xref:System.Windows.Controls.Viewport3D> .  В этом разделе основное внимание уделяется рисованию трехмерной графики внутри <xref:System.Windows.Controls.Viewport3D> .  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>Трехмерное пространство координат  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Система координат для двухмерной графики находит источник в левом верхнем углу области отрисовки (обычно это экран). В двухмерной системе положительные значения оси x продолжаются вправо, а положительные значения оси y — сверху вниз.  Однако в трехмерной системе координат источник располагается в центре области отрисовки, при этом положительные значения оси x перемещаются вправо, но положительные значения оси y продолжаются вверх, а положительные значения оси z перемещаются наружу из источника в сторону средства просмотра.  
  
 ![Системы координат](./media/coordsystem-1.png "Курдсистем-1")  
Стандартные двумерные и трехмерные системные представления координат  
  
 Пространство, определяемое этими осями, является стационарной рамкой ссылки для трехмерных объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . При построении моделей в этом пространстве и создании источников света и камер для их отображения необходимо отличать стационарную систему отсчета координат ("мировую систему координат") от локальной системы отсчета, которая создается для каждой модели при применении к ней преобразований. Помните, что в зависимости от освещения и настроек камеры объекты в мировой системе координат могут выглядеть различным образом или быть полностью невидимыми. При этом положение камеры не изменяет расположения объектов в мировой системе координат.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>Камеры и проекции  
 Разработчики, работающие в 2D, привыкли к размещению примитивов рисования на двухмерном экране. При создании трехмерной сцены важно помнить, что фактически создается 2D-представление трехмерных объектов. Так как трехмерная сцена выглядит по-разному в зависимости от точки зрения наблюдатель, необходимо указать эту точку представления. <xref:System.Windows.Media.Media3D.Camera>Класс позволяет указать эту точку представления для трехмерной сцены.  
  
 Другим способом понять, как трехмерная сцена представлена на двумерной плоскости, является описание сцены в качестве проекции на поверхность просмотра. <xref:System.Windows.Media.Media3D.ProjectionCamera>Позволяет указать различные проекции и их свойства для изменения того, как наблюдатель видит трехмерные модели. <xref:System.Windows.Media.Media3D.PerspectiveCamera>Указывает проекцию, форешортенс сцену.  Иными словами, объект <xref:System.Windows.Media.Media3D.PerspectiveCamera> предоставляет перспективу точки исчезновения.  Можно указать положение камеры в пространстве координат сцены, направление и поле зрения камеры и вектор, определяющий направление "вверх" в сцене. На следующей схеме показана <xref:System.Windows.Media.Media3D.PerspectiveCamera> проекция.  
  
 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>Свойства и <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera> ограничивают диапазон проекции камеры. Поскольку камеры могут быть расположены в любом месте сцены, фактически можно расположить камеру внутри модели или очень близко от нее, что усложняет правильное распознавание объекта.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> позволяет указать минимальное расстояние от камеры, после которого объекты не будут нарисованы.  И наоборот, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> позволяет указать расстояние от камеры, за которой объекты не будут нарисованы, что гарантирует, что объекты, которые не удается распознать, не будут включаться в сцену.  
  
 ![Настройка камеры](./media/coordsystem-6.png "Курдсистем-6")  
Позиция камеры  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> Задает ортогональную проекцию трехмерной модели для двухмерной визуальной поверхности. Подобно другим камерам, она указывает позицию, направление просмотра и направление "вверх". Однако, в отличие от <xref:System.Windows.Media.Media3D.PerspectiveCamera> , <xref:System.Windows.Media.Media3D.OrthographicCamera> описывает проекцию, которая не включает перспективу ракурс. Иными словами, <xref:System.Windows.Media.Media3D.OrthographicCamera> описывает окно просмотра, стороны которого параллельны, а не один, стороны которого соответствуют точке на камере. На следующем рисунке показана та же модель, которая просматривается с помощью <xref:System.Windows.Media.Media3D.PerspectiveCamera> и <xref:System.Windows.Media.Media3D.OrthographicCamera> .  
  
 ![Ортогональная и перспективная проекции](./media/camera-projections4.png "Camera_projections4")  
Перспективная и ортогональная проекции  
  
 В следующем коде показано несколько обычных параметров камеры.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>Примитивы модели и сетки  
  
 <xref:System.Windows.Media.Media3D.Model3D> является абстрактным базовым классом, представляющим универсальный трехмерный объект. Для создания трехмерной сцены необходимы некоторые объекты для просмотра, а объекты, составляющие граф сцены, являются производными от <xref:System.Windows.Media.Media3D.Model3D> . В настоящее время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает геометрические модели с помощью <xref:System.Windows.Media.Media3D.GeometryModel3D> . <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>Свойство этой модели принимает примитив сетки.  
  
 Начните построение модели с создания примитива, или сетки. Трехмерный примитив — это коллекция вершин, которые формируют одну трехмерную фигуру. Большинство трехмерных систем предоставляют примитивы, смоделированные на самой простой замкнутой фигуре: треугольник, определяемый тремя вершинами.  Поскольку три точки треугольника лежат в одной плоскости, можно добавлять треугольники для моделирования более сложных фигур, называемых сетками.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] настоящее время трехмерная система предоставляет <xref:System.Windows.Media.Media3D.MeshGeometry3D> класс, который позволяет указать любую геометрию; в настоящее время он не поддерживает стандартные трехмерные примитивы, такие как шарик и кубические формы. Начните создание <xref:System.Windows.Media.Media3D.MeshGeometry3D> , указав список вершин треугольника в качестве его <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Свойства. Каждая вершина указана как <xref:System.Windows.Media.Media3D.Point3D> .  (В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] укажите это свойство в виде списка чисел, сгруппированных по трем, представляющих координаты каждой вершины.) В зависимости от геометрии ваша сеть может состоять из многих треугольников, некоторые из которых используют одни и те же углы (вершины). Чтобы нарисовать сетку правильно, приложению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] необходимы сведения о том, какие вершины треугольников являются общими. Вы предоставляете эти сведения, указывая список индексов треугольника со <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> свойством. Этот список определяет порядок, в котором точки, указанные в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> списке, определяют треугольник.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 В предыдущем примере <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> список указывает восемь вершин для определения сетки в форме куба. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>Свойство указывает список двенадцати групп из трех индексов.  Каждое число в списке ссылается на смещение в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> списке.  Например, первые три вершины, указанные в списке, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> — это (1, 1, 0), (0, 1, 0) и (0, 0, 0). Первыми тремя индексами, указанными в <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> списке, являются 0, 2 и 1, которые соответствуют первой, третьей и второй точкам в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> списке. В результате первый треугольник, формирующий модель куба, будет составлен из вершин (1, 1, 0), (0, 1, 0) и (0, 0, 0), а оставшиеся одиннадцать треугольников будут определяться аналогичным образом.  
  
 Можно продолжить определение модели, указав значения для <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> свойств и.  Для отображения поверхности модели графической системе требуются данные о том, какое направление поверхности является лицевым для любого данного треугольника. Система использует эти сведения для вычислений освещения модели: поверхности, обращенные к источнику освещения, отображаются ярче, чем поверхности, расположенные под углом к освещению. Хотя приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может определить векторы нормали по умолчанию, используя координаты позиции, можно также задавать различные векторы нормали для аппроксимации вида кривых поверхностей.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>Свойство задает коллекцию объектов <xref:System.Windows.Point> , которые сообщают графической системе о том, как сопоставлять координаты, определяющие, как текстура рисуется на вершинах сетки. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> указываются как значения от 0 до 1 включительно.  Как и в <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> случае со свойством, графическая система может вычислить координаты текстуры по умолчанию, но вы можете задать различные координаты текстуры для управления сопоставлением текстуры, которая включает в себя часть повторяющегося шаблона, например. Дополнительные сведения о координатах текстуры можно найти в последующих разделах или в пакете Managed Direct3D SDK.  
  
 В следующем примере показано создание одной грани модели куба в процедурном коде. Весь куб можно нарисовать как один GeometryModel3D. в этом примере грань куба выводится как отдельная модель для применения отдельных текстур в дальнейшем.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>Применение материалов к модели  
  
 Чтобы сетка выглядела как объект в трехмерном пространстве, к ней необходимо применить текстуру, которая покрывает поверхность, определенную ее вершинами и треугольниками. В этом случае можно осветить эту поверхность и создать ее проекцию с помощью камеры. В двухмерном <xref:System.Windows.Media.Brush> классе класс используется для применения цветов, узоров, градиентов или другого визуального содержимого к областям экрана.  Однако внешний вид трехмерных объектов — это функция модели освещения, а не только цвет или применяемый к ним шаблон. Реальные объекты отражают свет неодинаково, в зависимости от качества поверхностей: гладкие и глянцевые поверхности выглядят иначе, чем неровные и матовые, также одни объекты поглощают свет, в то время как другие — отражают. К трехмерным объектам можно применить все те же кисти, которые можно применить к 2D-объектам, но нельзя напрямую применить их.  
  
 Чтобы определить характеристики поверхности модели, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует <xref:System.Windows.Media.Media3D.Material> абстрактный класс. Конкретные подклассы класса Material определяют некоторые характеристики внешнего вида поверхности модели, и каждый из них предоставляет свойство Brush, которому можно передать значение SolidColorBrush, TileBrush или VisualBrush.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial> Указывает, что кисть будет применена к модели, как будто модель была освещена диффузией. Использование DiffuseMaterial наиболее похоже на использование кистей непосредственно в двумерных моделях; поверхности модели не отображают освещение, как будто блестящие.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial> Указывает, что кисть будет применена к модели, как будто поверхность модели была жесткой или блестящий, способная отражать основные характеристики. Можно задать степень, до которой текстура предложит это отражающее качество, или «тонкое», указав значение для <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> Свойства.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial> позволяет указать, что текстура будет применяться, как если бы модель была выделена относительно цвета кисти. Это не делает модель светящейся; однако это иначе влияет на затенение, чем если бы текстура была создана с помощью класса DiffuseMaterial или SpecularMaterial.  
  
 Для повышения производительности <xref:System.Windows.Media.Media3D.GeometryModel3D> обратные стороны (те, которые находятся вне представления, поскольку они находятся на противоположной стороне модели от камеры) исключаются из сцены.  Чтобы указать объект, <xref:System.Windows.Media.Media3D.Material> применяемый к лицевой стороне модели, такой как плоскость, установите <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> свойство модели.  
  
 Для достижения некоторых свойств поверхности, таких как свечение или эффект отражения, можно последовательно применить к модели несколько различных кистей. Вы можете применять и повторно использовать несколько материалов с помощью <xref:System.Windows.Media.Media3D.MaterialGroup> класса. Дочерние элементы класса MaterialGroup применяются от первого к последнему в нескольких проходах отрисовки.  
  
 В следующих примерах кода показано, как использовать сплошной цвет и рисунок в качестве кистей для трехмерных моделей.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
 [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]  
 [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>Освещение сцены  
 Источники света трехмерной графики делают свет в реальном мире: они делают поверхности видимыми. Более того, источники света определяют, какая часть сцены будет включена в проекцию. Объекты источников света в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создают различные эффекты света и тени. Они смоделированы на основе поведения различных реальных источников света. Включите по меньшей мере один источник освещения в сцену, иначе никакие модели не будут видны.  
  
 Следующие источники света являются производными от базового класса <xref:System.Windows.Media.Media3D.Light> :  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Обеспечивает внешнее освещение, которое освещает все объекты единообразно независимо от их расположения или ориентации.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Освещение аналогично удаленному источнику освещения.  Направленный свет имеет определенный объект <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> Vector3D, но не имеет указанного расположения.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Освещение, похожее на ближайший источник освещения. Источники света PointLights занимают определенное положение и испускают свет из этого положения. Объекты на сцене освещаются в зависимости от их положения и расстояния относительно источника света. <xref:System.Windows.Media.Media3D.PointLightBase> предоставляет <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> свойство, которое определяет расстояние, за пределами которого модели не будут освещены светом. PointLight также предоставляет свойства ослабления, которые определяют, как интенсивность освещения уменьшает расстояние. Можно указать константу, линейную или квадратичную интерполяцию затухания источника света.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Наследует от <xref:System.Windows.Media.Media3D.PointLight> . Источники света Spotlight освещают сцену подобно источникам света и также имеют расположение и направление. Они задают освещение в области, заданной в виде конуса, <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> и <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> свойства, указанные в градусах.  
  
 Огни — это <xref:System.Windows.Media.Media3D.Model3D> объекты, поэтому можно преобразовывать и анимировать свойства освещения, включая расположение, цвет, направление и диапазон.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>Преобразование моделей  
 При создании моделей в сцене им задается определенное местоположение. Для поворота моделей, изменения их размера или перемещения внутри сцены не следует изменять вершины, определяющие сами модели.  Вместо этого, как и в 2D, к моделям применяются преобразования.  
  
 Каждый объект модели имеет <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> свойство, с помощью которого можно перемещать, переориентировать или изменять размер модели.  При применении преобразования все точки модели фактически смещаются с помощью определенного вектора или значения, заданного преобразованием. Другими словами, выполняется преобразование координатного пространства, в котором определена модель ("пространство модели"), при этом значения, составляющие геометрию модели в системе координат всей сцены ("мировое пространство"), не изменяются.  
  
 Дополнительные сведения о преобразовании моделей см. в разделе [Общие сведения об трехмерных преобразованиях](3-d-transformations-overview.md).  
  
<a name="animations"></a>
## <a name="animating-models"></a>Анимация моделей  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Трехмерная реализация участвует в той же системе анимации и времени, что и 2D-графика. Иными словами, для анимации трехмерной сцены необходимо анимировать свойства ее моделей. Можно непосредственно анимировать свойства примитивов, но обычно проще анимировать преобразования, изменяющие позицию или внешний вид моделей. Так как преобразования могут применяться к <xref:System.Windows.Media.Media3D.Model3DGroup> объектам, а также к отдельным моделям, можно применить один набор анимаций к дочернему элементу Model3DGroup и другому набору анимаций для группы дочерних объектов. Также можно добиться разнообразных визуальных эффектов, анимируя свойства элементов освещения сцены. Наконец, можно анимировать саму проекцию, изменяя положение камеры или поле зрения. Дополнительные сведения о системе времени и анимации в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделах [Общие сведения об эффектах анимации](animation-overview.md), [Общие сведения о Storyboard](storyboards-overview.md) и [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Для анимации объекта в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создайте временную шкалу, определите анимацию (которая изменяет значение некоторого свойства во времени) и укажите свойство, к которому применяется анимация. Так как все объекты в трехмерной сцене являются дочерними элементами <xref:System.Windows.Controls.Viewport3D> , свойствам объекта Viewport3D, которые необходимо применить к сцене, являются свойства, представленные в элементе «элемент и анимация».  
  
 Предположим, требуется создать качающуюся на месте модель. Вы можете применить <xref:System.Windows.Media.Media3D.RotateTransform3D> к модели и анимировать ось вращения от одного вектора к другому. В следующем примере кода демонстрируется применение Vector3DAnimation к свойству Axis преобразования элемента Rotation3D, при условии что RotateTransform3D будет одним из нескольких преобразований, применяемых к модели с TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>Добавление трехмерного содержимого в окно  
 Для отрисовки сцены добавьте модели и источники света в <xref:System.Windows.Media.Media3D.Model3DGroup> , а затем установите в <xref:System.Windows.Media.Media3D.Model3DGroup> качестве <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> объекта <xref:System.Windows.Media.Media3D.ModelVisual3D> . Добавьте в <xref:System.Windows.Media.Media3D.ModelVisual3D> <xref:System.Windows.Controls.Viewport3D.Children%2A> коллекцию <xref:System.Windows.Controls.Viewport3D> . Добавьте камеры в, <xref:System.Windows.Controls.Viewport3D> установив его <xref:System.Windows.Controls.Viewport3D.Camera%2A> свойство.  
  
 Наконец, добавьте в <xref:System.Windows.Controls.Viewport3D> окно. Если объект <xref:System.Windows.Controls.Viewport3D> включен в качестве содержимого элемента макета, например Canvas, укажите размер Viewport3D, задав его <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> Свойства и (наследуемые от <xref:System.Windows.FrameworkElement> ).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Общие сведения о трехмерных преобразованиях](3-d-transformations-overview.md)
- [Достижение максимальной производительности WPF 3D](maximize-wpf-3d-performance.md)
- [Инструкции](3-d-graphics-how-to-topics.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Рисование с помощью объектов Image, Drawing и Visual](painting-with-images-drawings-and-visuals.md)
