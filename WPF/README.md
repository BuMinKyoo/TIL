###### Top

- [WPF class hierarchy](https://github.com/BuMinKyoo/TIL/blob/main/WPF/WPF%20class%20hierarchy.png)



- [WPF로의시작...](#wpf의-시작)



- <details>
  <summary>Application</summary>  
  <div markdown="1">
    
    - [Application](#application)
      - [ShutdownMode](#shutdownmode)
      - [Event(Startup, Activated, Deactivated, Exit)](#eventstartup-activated-deactivated-exit)

  </div>
  </details>



- <details>
  <summary>Window</summary>
  <div markdown="1">

    - [Window](#window)
      - [xmlns](#xmlns)
      - [ResizeMode](#resizemode)
      - [SizeToContent](#sizetocontent)
      - [Window이벤트(Activated, Deactivated, Closing)](#window이벤트activated-deactivated-closing)
  
  </div>
  </details>



- <details>
  <summary>다양한 참조법</summary>
  <div markdown="1">

    - [다양한 참조법](#다양한-참조법)
    - [xaml.cs에 있는 Class를 xaml안에 객체로 불러오기](#xamlcs에-있는-class를-xaml안에-객체로-불러오기)
    - [같은 프로젝트 cs에 있는 Class를 xaml안에 객체로 불러오기](#같은-프로젝트-cs에-있는-class를-xaml안에-객체로-불러오기)
    - [같은 프로젝트에서 '리소스 사전' 불러오기](#같은-프로젝트에서-리소스-사전-불러오기)
    - [같은 프로젝트에서 '리소스 사전' 불러오기(2) NewFolder라는 폴더 안에 들어 있는 경우](#같은-프로젝트에서-리소스-사전-불러오기2-newfolder라는-폴더-안에-들어-있는-경우)
    - [같은 프로젝트에서 'UserControl(사용자 정의 컨트롤)' 불러오기](#같은-프로젝트에서-usercontrol사용자-정의-컨트롤-불러오기)
    - [다른 프로젝트의 네임스페이스 참조하기](#다른-프로젝트의-네임스페이스-참조하기)
    - [다른 프로젝트에서 '리소스사전' 참조하기](#다른-프로젝트에서-리소스사전-참조하기)
    
  </div>
  </details>

***
***

- <details>
  <summary>Object - DispatcherObject</summary>
  <div markdown="1">

    - [Style](#style)
      - [Style의 key값으로 각각의 컨트롤에 Style을 적용](#style의-key값으로-각각의-컨트롤에-style을-적용)
        - Style x:Key="(사용할 name)" TargetType="(적용시킬 컨트롤)"
      - [TargetType속성으로 적용시킬 컨트롤 지정](#targettype속성으로-적용시킬-컨트롤-지정)
        - Style TargetType="{x:Type 적용시킬 컨트롤}"
      - [각각의 자식 컨트롤에 Style 적용하기](#각각의-자식-컨트롤에-style-적용하기)
      - [BasedOn을 이용한 Style상속](#basedon을-이용한-style상속)

  </div>
  </details>
  
  
- <details>
  <summary>Object - DispatcherObject - DependencyObject - Visual - UIElement</summary>
  <div markdown="1">
    
    - FrameworkElement
      - [Decorator](#decorator)
        - [Border](#border)
      - [TextBlock](#textblock)
        - [Run](#run)
      - [Popup](#popup)
        - [Placement, HorizontalOffset, VerticalOffset, AllowsTransparency, IsOpen](#placement-horizontaloffset-verticaloffset-allowstransparency-isopen)
        - [AllowsTransparency(False일때)](#allowstransparencyfalse일때)
        - [AllowsTransparency(True일때)](#allowstransparencytrue일때)
      - [Panel](#panel)
        - [Grid](#grid)
          - [다양한 요소안에 Grid를 만들기](#다양한-요소안에-grid를-만들기)
          - [IsSharedSizeScope속성을 이용해 Grid의 폭과 넓이 맟주기](#issharedsizescope속성을-이용해-grid의-폭과-넓이-맟주기)
        - [Canvas](#canvas)
        - [DockPanel](#dockpanel)
        - [StackPanel](#stackpanel)
          - [Orientation="Horizontal"](#orientationhorizontal)
        - [WrapPanel](#wrappanel)
          - [Orientation="Vertical"](#orientationvertical)
        - [Viewbox](#viewbox)
          - [Stretch](#stretch)
          - [StretchDirection](#stretchdirection)
        - [UniformGrid](#uniformgrid)
          - [Columns,Rows지정](#columnsrows지정)
          - [ClipToBounds](#cliptobounds)
          - [FirstColumn](#firstcolumn)
          - [FlowDirection](#flowdirection)
      - [Control](#control)
        - [Separator](#separator)
        - [PasswordBox](#passwordbox)
        - [Thumb](#thumb)
          - [GridSplitter](#gridsplitter)
            - [DragStarted. DragCompleted, DragDelta, IsDragging, CancelDrag](#dragstarted-dragcompleted-dragdelta-isdragging-canceldrag)
        - [RangeBase](#rangebase)
          - [ProgressBar](#progressbar)
            - [IsIndeterminate](#isindeterminate)
          - [Slider](#slider)
            - [ValueChanged이벤트로 R,G,B값 표현하기](#valuechanged이벤트로-rgb값-표현하기)
            - [ValueChanged이벤트로 R,G,B,A값 표현하기](#valuechanged이벤트로-rgba값-표현하기)
            - [Orientation속성](#orientation속성)
            - [TickPlacement속성(눈금표시)](#tickplacement속성눈금표시)
        - [TextBoxBase](#textboxbase)
          - [TextBox](#textbox)
            - [AcceptsReturn, AcceptsTab, VerticalScrollBarVisibility, MaxLength, CharacterCasing](#acceptsreturn-acceptstab-verticalscrollbarvisibility-maxlength-charactercasing)
            - [TextChanged이벤트, SelectionChanged이벤트](#textchanged이벤트-selectionchanged이벤트)
            - [SelectedText, CaretIndex, SelectionStart, SelectionLength, Select(1,4), SelectAllAll()](#selectedtext-caretindex-selectionstart-selectionlength-select14-selectallall)
        - [ContentControl](#contentcontrol)
          - [ScrollViewer](#ScrollViewer)
            - [FrameworkElement를 이용해 ScrollViewer의 시스템 whith사이즈를 불러오기](#frameworkelement를-이용해-scrollviewer의-시스템-whith사이즈를-불러오기)
            - [HorizontalScrollBarVisibility, VerticalScrollBarVisibility(visible, Hidden, Auto, Disabled)](#horizontalscrollbarvisibility-verticalscrollbarvisibilityvisible-hidden-auto-disabled)
          - [ToolTip](#tooltip)
          - [ButtonBase](#ButtonBase)
            - [RepeatButton](#RepeatButton)
          - [HeaderedContentControl](#HeaderedContentControl)
            - [Expander](#Expander)
            - [GroupBox](#GroupBox)
        - [ItemsControl](#ItemsControl)
          - [MenuBase](#MenuBase)
            - [Menu](#Menu)
            - [ContextMenu](#ContextMenu)
          - [Selector](#Selector)
            - [TabControl](#TabControl)
            - [ComboBox](#ComboBox)
            - [ListBox](#ListBox)
              - [ListView](#ListView)

    
  </div>
  </details>
  
  
  
- <details>
  <summary>자주 활용하는 Class, Interface</summary>
  <div markdown="1">  

    - ObservableCollection
    - INotifyPropertyChanged
    
  </div>
  </details>



- <details>
  <summary>Binding</summary>
  <div markdown="1">  

    - Button + Command
    - ItemsSource
    - Workspace를 통한 UserControl끼리의 값 전달
    - ContentControl을 활용한 UserControl끼리의 값 전달
    
  </div>
  </details>



- JsonParsing

- <details>
  <summary>Try..</summary>
  <div markdown="1">  

    - [공공API 내용을 xml파일로 불러와서 ComboBox와 List로 뿌려주기(Public-API)]_Repository링크(https://github.com/BuMinKyoo/Public-API_XML)
    - [공공API 내용을 json파일로 불러와서 ComboBox와 List로 뿌려주기(Public-API)]_Repository링크(https://github.com/BuMinKyoo/Public-API_JSON)
    - [화면에 있는 color값을 추출하는 color-picker]_Repository링크(https://github.com/BuMinKyoo/ColorPicker_WPF)
    
  </div>
  </details>


- etc...

***
***

<br/>

## WPF의 시작...

<br/>

#Mainwindow.xaml.cs
~~~c#
using System.Windows;
using System;

namespace WpfApp4
{
    public class Test
    {
        [STAThread]
        static void Main()
        {
            Application app = new Application();

            //윈도우 화면 띄우기
            Window win = new Window();
            win.Title = "MyfirstTile";
            win.Show();

            //Application실행
            app.Run();

            
        }
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/154697172-f29df162-3c9e-4c45-b83d-c256ce2cb204.png">

<br/>

  - 가장 기본적인 형태로 WPF창을 띄워 보았다. 이처럼 WPF의 네임 스페이스 들은 System.Windows.Controls, System.Windows.Input등 System.Windows로 시작된다.
  - 윈폼(Windows Forms)관련 네임 스페이스도 이와 같이 System.Windows.Forms로 부터 시작된다.

  - WPF를 사용 하기 위해서는 STAThread(Single Threaded Apartmennt)여야 한다. 이는 COM형식을 이용하는 경우에 해당 응용 프로그램이 STAThread(Single Threaded Apartmennt)모델로 설정 되어야 하기 때문이다.(즉 COM이라는 객체를 사용하기 위해서 STAThread(Single Threaded Apartmennt)모델로 설정하는것)
    - 그럼 COM이란 무엇인가? : COM(Component Object Model)은 마이크로소프트가 개발한 소프트웨어 구성 요소들의 응용 프로그램 이진 인터페이스 표준이다.
    - 내가 이해한 대로 설명해 보자면, COM은 객체로써 어떤 기능을 가지고 있는데, COM과 COM을 어떤 약속한 표준대로 만들어서, 공유하고 통합해서 사용한다. 이는, 개발을 할때도 COM을 
사용 하지 않는 다면 한명의 개발자가 개발을 할때, 그것을 바턴 터치 처럼 이어 받아야 하는 상황이 생기지만, COM을 사용 한다면 누구는 저 기능 , 누구는 저 기능으로 나누어 개발한 후에
그것을 통합해서 개발해 나갈 수 있다는것. 다른 비유로 보자면 각각의 다른 회사에서 만든 CD플레이어, 라디오, 비디오 플레이어를 하나의 기계에 통합한다는 느낌...?
    - 그래서 아무튼 WPF는 COM을 사용하여 개발했기 때문에(?)(이게 맞나..?) STAThread(Single Threaded Apartmennt)에서 실행해야 한다는것
    
<br/><br/>

여기서 의문은, WPF프로젝트를 시작하면 Main()함수도 없는 데다가, STAThread도 보이지 않는다...  
  - 모든 파일 표시 클릭 - obj - Debug - net6.0-windows 로 가면 App.g.i.cs가 보인다

<img src="https://user-images.githubusercontent.com/39178978/154711833-721f6d5e-aa7c-4230-b2aa-1c5ed14ecf0c.png">

<br/>

  - 프로젝트를 실행하면 App.g.cs가 생기는 것을 볼 수 있다.

<img src="https://user-images.githubusercontent.com/39178978/154712179-8fbe35dc-802f-4b4c-9006-9ce9cf61ff77.png">

그 클래스 파일을 열면, 아래쪽에

~~~c#
[System.STAThreadAttribute()]
[System.Diagnostics.DebuggerNonUserCodeAttribute()]
[System.CodeDom.Compiler.GeneratedCodeAttribute("PresentationBuildTasks", "6.0.2.0")]
public static void Main() {
    WpfApp5.App app = new WpfApp5.App();
    app.InitializeComponent();
    app.Run();
}
~~~

이것을 볼 수 있다. [System.STAThreadAttribute()], 그리고 Main()

###### [WPF로의시작...](#wpf의-시작)
###### [Top](#top)

<br/>

***

<br/>

# Application

## ShutdownMode
  - ShutdownMode="OnExplicitShutdown" : 종료를 아예 말해야함
  - ShutdownMode="OnLastWindowClose" : 위도우창을 전부 종료해야함
  - ShutdownMode="OnMainWindowClose" : 메인 윈도우 창을 종료하면 됨

<br/>

  - Application.Current : Application을 시작하는 메인Window는 한개 뿐이기 때문에, 어디서든 메인Window에 접근하기 위해서 사용 할 수 있다.

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

<br/>

  - ShutdownMode="OnExplicitShutdown"

#App.xaml
~~~c#
<Application x:Class="WpfApp5.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:local="clr-namespace:WpfApp5"
             StartupUri="MainWindow.xaml" ShutdownMode="OnExplicitShutdown">
    <Application.Resources>
         
    </Application.Resources>
</Application>
~~~

<br/>

#MainWindow.xaml
~~~c#
<Grid>
    <Button x:Name="Exit_btn" Width="100" Height="30" Content="종료" Click="Exit_btn_Click"/>
</Grid>
~~~

<br/>

#MainWindow.xaml.cs
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    private void Exit_btn_Click(object sender, RoutedEventArgs e)
    {
        Application.Current.Shutdown();
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/152976639-38a061b5-0c32-4703-ba91-5ac121fbaeff.png">
일반적으로는 window창을 닫는 것만으로 WPF가 종료 되지만, ShutdownMode="OnExplicitShutdown"로 해놓으면 종료 되지 않음. 종료 커멘드를 실행 해야 종료가됨. 버튼에
연결된 Application.Current.Shutdown();을 실행 함으로써 종료가 된다.

<br/>

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

<br/>

  - ShutdownMode="OnLastWindowClose"

#App.xaml
~~~c#
<Application x:Class="WpfApp5.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:local="clr-namespace:WpfApp5"
             StartupUri="MainWindow.xaml" ShutdownMode="OnLastWindowClose">
    <Application.Resources>
         
    </Application.Resources>
</Application>
~~~

<br/>

#MainWindow.xaml
~~~c#
<Grid>
    <Button x:Name="Window_add_btn" Width="100" Height="30" Content="화면생성" Click="Window_add_btn_Click"/>
</Grid>
~~~

<br/>

#MainWindow.xaml.cs
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    int winNum = 0;
    private void Window_add_btn_Click(object sender, RoutedEventArgs e)
    {
        Window win = new Window();
        winNum++;
        win.Title = winNum.ToString();
        win.Width = Application.Current.MainWindow.Width;
        win.Height = Application.Current.MainWindow.Height;
        win.Show();

    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/152978551-af346a46-9b48-45a9-a9c4-55c80134d53c.png">
여러window창을 만들었을 경우 전부다 끄지 않는 이상 Application이 종료되지 않는다.

<br/>

여기서 ShutdownMode="OnMainWindowClose"모드로 한다면, 여러 Window창을 만들었어도, 메인Window창을 끄게 되면 Application이 종료가 된다.

###### [Application](#application)
###### [Top](#top)

<br/>
<br/>

## Event(Startup, Activated, Deactivated, Exit)
  - Startup : Application이 시작하면서 이벤트 발생, 보통 UI진입전에 로그인을 해야 하는 경유에 적합 하다고 함
  - Activated : Application이 가지고 있는 어떤 Window라도 포커스 될 경우에 발생
  - Deactivated : Application이 가지고 있는 어떤 Window라도 포커스 잃으면 발생
  - Exit : Application종료시 발생

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

<br/>

#App.xaml
~~~c#
<Application x:Class="WpfApp20.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             StartupUri="MainWindow.xaml"
             Startup="Application_Startup"
             Activated="Application_Activated"
             Deactivated="Application_Deactivated"
             Exit="Application_Exit"
             ShutdownMode="OnLastWindowClose">
    <Application.Resources>
         
    </Application.Resources>
</Application>
~~~

<br/>

#App.cs
~~~c#
public partial class App : Application
{
    private void Application_Startup(object sender, StartupEventArgs e)
    {
        Debug.WriteLine("Startup");
    }

    private void Application_Activated(object sender, EventArgs e)
    {
        Debug.WriteLine("Activated");
    }

    private void Application_Deactivated(object sender, EventArgs e)
    {
        Debug.WriteLine("Deactivated");
    }

    private void Application_Exit(object sender, ExitEventArgs e)
    {
        Debug.WriteLine("Exit");
    }
}
~~~

<br/>

#Debug창
~~~
Startup
Activated
Deactivated
Exit
~~~

###### [Application](#application)
###### [Top](#top)

<br/>

***

<br/>

# Window

## xmlns
##### - 내부적인 부분에 대한 상세한 설명은 아직 공부가 더 필요한듯하다..단순하게만 적고 넘어가자.
  - xmlns는 xml namespace의 줄임말이고, URI로 네임스페이스 이름을 정의한 형태이다.

- xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
사용자 인터페이스를 만드는데 WPF의 모든 클래스 들이 들어 있고, 네임 스페이스 접두사가 없기 때문에 문서 전체에 적용되는 네임 스페이스

- xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
XAML의 네임 스페이스이고, 다양한 XAML유틸리티 기능을 포함하고 있는 네임 스페이스 이다. 접두사는 X로 매핑된다.

###### [Window](#window)
###### [Top](#top)

<br/>
<br/>

## ResizeMode
##### - ResizeMode="NoResize"를 사용하면 Window창의 가로,세로 길이를 임의로 조절할 수 없게 만든다.

#MainWindow.XAML
~~~
Title="MainWindow" ResizeMode="NoResize"
~~~

###### [Window](#window)
###### [Top](#top)

<br/>
<br/>

## SizeToContent
##### - SizeToContent="WidthAndHeight"를 사용하면 윈도우창을 컨텐트 내용대로 자동으로 조절해 준다.

#MainWindow.XAML
~~~
Title="MainWindow" SizeToContent="WidthAndHeight"
~~~

시작전 윈도우 크기 창  
<img src="https://user-images.githubusercontent.com/39178978/151296985-e28ec50f-68fc-4a0e-8223-fc34891b3c44.png">

실행시 윈도우 창을 자동으로 맞게 조절해준다  
<img src="https://user-images.githubusercontent.com/39178978/151297018-36f45f0d-3283-42df-96a8-c6133b93d9e0.png">

###### [Window](#window)
###### [Top](#top)

<br/>
<br/>

## Window이벤트(Activated, Deactivated, Closing)
  - Activated : 메인 윈도우가 포커스 되었을때 발생
  - Deactivated : 메인 윈도우가 포커스 되지 않았을 때 발생
  - Closing : 메인 윈도우를 닫을때 이벤트 발생

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

<br/>

#MainWindow.XAML
~~~c#
<Window x:Class="WpfApp20.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="MainWindow" Height="300" Width="300" Activated="Window_Activated"
        Deactivated="Window_Deactivated"
        Closing="Window_Closing">
    <Grid>
        
    </Grid>
</Window>
~~~

<br/>

#MainWindow.XAML.cs
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    private void Window_Activated(object sender, EventArgs e)
    {
        Debug.WriteLine("Activated");
    }

    private void Window_Closing(object sender, System.ComponentModel.CancelEventArgs e)
    {
        if (MessageBox.Show("정말로 종료하시겠습니까?", "종료확인", MessageBoxButton.YesNo) == MessageBoxResult.No)
        {
            e.Cancel = true;
        }
    }

    private void Window_Deactivated(object sender, EventArgs e)
    {
        Debug.WriteLine("Deactivated");
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/153856831-97c5f65f-b0be-43d6-a5cc-ac26fe8bbe1e.png">

<br/>

실행시 X를 눌러 종료시 메세지 박스가 뜨고. 아니요를 누르면 종료가 되지 않음.

###### [Window](#window)
###### [Top](#top)

<br/>

***

<br/>

# 다양한 참조법
  - Class를 참조할 경우 일반적으로 클래스 라이브 러리의 .NET Standard 프레임 워크를 이용하여 참조한다(이유 : .NET Framework, .NET Core, Xamarin 전부 호환 되기 때문에)

## xaml.cs에 있는 Class를 xaml안에 객체로 불러오기
  - xmlns:(접두사)="clr-namespace:(namespace명)"를 사용하여 매핑하기

#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp16.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:WpfApp16"
        Title="MainWindow" Height="300" Width="300">
    <Window.Resources>
        <local:Car x:Key="car"/>
    </Window.Resources>
    <Grid>
        <Button Width="100" Height="30" Content="{StaticResource car}"/>
    </Grid>
</Window>
~~~

<br/>

#MainWindow.xaml.cs
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }
}

public class Car
{

}
~~~

<img src="https://user-images.githubusercontent.com/39178978/153410392-b60f0b35-9235-41f1-a58d-aa738a8d9496.png">

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>
<br/>

## 같은 프로젝트 cs에 있는 Class를 xaml안에 객체로 불러오기
  - xmlns:(접두사)="clr-namespace:(namespace명)"를 사용하여 매핑하기

#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp16.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:WpfApp16"
        Title="MainWindow" Height="300" Width="300">
    <Window.Resources>
        <local:Car x:Key="car"/>
    </Window.Resources>
    <Grid>
        <Button Width="100" Height="30" Content="{StaticResource car}"/>
    </Grid>
</Window>
~~~

<br/>

#Class1.cs
~~~c#
public class Car
{
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/153411052-c2b6b3af-8b33-4e01-a021-5e314a16d363.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153410392-b60f0b35-9235-41f1-a58d-aa738a8d9496.png">

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>
<br/>

## 같은 프로젝트에서 '리소스 사전' 불러오기

~~~c#
<ResourceDictionary>
    <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="(경로/리소스사전명)"/>
    </ResourceDictionary.MergedDictionaries>
</ResourceDictionary>
~~~

을 이용하여 리소스 사전을 불러올 수 있음

<br/>

#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp16.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="MainWindow" Height="300" Width="300">
    <Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="Dictionary1.xaml"/>
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Window.Resources>
    <Grid>
        <Button Width="100" Height="30" Style="{StaticResource buttonMade}"/>
    </Grid>
</Window>
~~~

<br/>

#Dictionary1.xaml
~~~c#
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

    <Style x:Key="buttonMade" TargetType="Button">
        <Setter Property="Background" Value="Green"/>
    </Style>
</ResourceDictionary>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153413299-1734d355-5add-48a2-9a08-86d3c9916d19.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153413366-74222a7b-96e6-45f3-b9de-bcfd0b7aae86.png">

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>
<br/>

## 같은 프로젝트에서 '리소스 사전' 불러오기(2) NewFolder라는 폴더 안에 들어 있는 경우
  - 위에 것으로 부터 이어 참고해서 보면, "Dictionary1.xaml" => "NewFolder/Dictionary1.xaml"이렇게 참조 했음을 알 수 있다.

#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp16.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="MainWindow" Height="300" Width="300">
    <Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="NewFolder/Dictionary1.xaml"/>
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Window.Resources>
    <Grid>
        <Button Width="100" Height="30" Style="{StaticResource buttonMade}"/>
    </Grid>
</Window>
~~~
로 이용 하면 된다.

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>
<br/>

## 같은 프로젝트에서 'UserControl(사용자 정의 컨트롤)' 불러오기

<br/>

#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp27.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:WpfApp27"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <local:UserControl1/>
    </Grid>
</Window>
~~~

<br/>

#UserControl1.xaml
~~~c#
<UserControl x:Class="WpfApp27.UserControl1"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             Height="200" Width="200">
    <Grid>
        <Rectangle Width="100" Height="100" Fill="red"/>
    </Grid>
</UserControl>
~~~

<img src="https://user-images.githubusercontent.com/39178978/154071023-dc86e23e-7446-4666-b22b-5640a0088549.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/154070852-06c0695f-deae-435b-be8f-961da99fe395.png">

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>
<br/>

## 다른 프로젝트의 네임스페이스 참조하기
  - CLR네임 스페이스 참조
  - XML네임 스페이스 참조
 
 <br>
 
   - 사전준비로 종속성, 참조 연결을 먼저 해준다.
     - .NET 6.0에서는 '종속성'에서 마우스 우클릭 -> 프로젝트 참조 추가
     - .NET Framework 4.7.2에서는 '참조'에서 마우스 우클릭 -> 참조 추가
<img src="https://user-images.githubusercontent.com/39178978/153415481-826baaf5-1446-4596-a8cf-be1d3d81fca6.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153415583-7f5efdb4-3ce4-4a3a-8585-56646de09225.png">

<br/>

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153415865-36d0e705-c45c-40fb-8fb8-5a7037140a5b.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153415903-f7ed0b43-d9ea-4e59-a1d5-5262ac3c1665.png">

그 후에는 뒤를 따르면 된다.
 
<br/>

  - CLR네임 스페이스 참조
    - xmlns:reference_project="clr-namespace:Reference_project;assembly=Reference_project" 이용한다
    - xmlns:(접두사)="clr-namespace:(참조namespace명.경로);assembly=(namespace명)"
    - 가령, NewFolder라는 폴더 안에 .cs의 class를 불러오려면, xmlns:reference_project="clr-namespace:Reference_project.NewFolder;assembly=Reference_project" 를 사용해야함


#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp16.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:reference_project="clr-namespace:Reference_project;assembly=Reference_project"
        Title="MainWindow" Height="300" Width="300">
    <Window.Resources>
        <reference_project:Car x:Key="reference_project_car"/>
    </Window.Resources>
    <Grid>
        <Button Width="100" Height="30" Content="{StaticResource reference_project_car}"/>
    </Grid>
</Window>
~~~

<br/>

#Reference_project.xaml.cs
~~~c#
public class Car
{

}
~~~

<img src="https://user-images.githubusercontent.com/39178978/153417714-d042ca1b-9720-4e59-bac5-a613fc233078.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153417813-68f3e880-56c2-45d9-beb3-76a4d105ee7b.png">

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>
<br/>

## 다른 프로젝트에서 '리소스사전' 참조하기
 
<br/>

~~~c#
<ResourceDictionary>
  <ResourceDictionary.MergedDictionaries>
      <ResourceDictionary Source="pack://application:,,,/(참조namespace명);component/(경로/리소스사전명)"/>
  </ResourceDictionary.MergedDictionaries>
</ResourceDictionary>
~~~
을 이용하면 된다

<br/>

#MainWindow.xaml
~~~c#
<Window x:Class="WpfApp16.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="MainWindow" Height="300" Width="300">
    <Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="pack://application:,,,/Reference_project;component/Dictionary1.xaml"/>
            </ResourceDictionary.MergedDictionaries>
            </ResourceDictionary>
    </Window.Resources>
    <Grid>
        <Button Width="100" Height="30" Content="{StaticResource buttonMade}"/>
    </Grid>
</Window>
~~~

<br/>

#Reference_project의 Dictionary1.xaml
~~~c#
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

    <Style x:Key="buttonMade" TargetType="Button">
        <Setter Property="Background" Value="Green"/>
    </Style>
    
</ResourceDictionary>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153421493-311a3664-f837-4c2d-82c6-3b2d6ca82b89.png">

<br/>

<img src="https://user-images.githubusercontent.com/39178978/153421558-3042dbb3-c101-4a40-b134-7c8852b86186.png">

###### [다양한 참조법](#다양한-참조법)
###### [Top](#top)

<br/>

***

<br/>

# Style
  - 상속 : Object - DispatcherObject - Style
  - Style : 컨트롤 요소들을 미리 정의해 놓고, 사용하는 방법

##### - Style적용 방식
  - 정적바인딩 : StaticResource이용 : 코드를 통해서 리소스가 변경되었을 때 참조 항목에 실시간 반영되지 않음(성능면에서는 뛰어남)
  - 동적바인딩 : DynamicResource이용 : 코드를 통해서 리소스가 변경되었을 때 참조 항목에 실시간 반영됨(성능떨어짐)

###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

 ## Style의 key값으로 각각의 컨트롤에 Style을 적용
  - Style x:Key="(사용할 name)" TargetType="(적용시킬 컨트롤)" : Style의 key값으로 각각의 컨트롤에 Style을 적용 시킨다. Style에서 지정한 '적용시킬 컨트롤'요소에 맞게 넣지 않는다면 예외가 발생한다

<br/>

#MainWindow.xaml
~~~c#
<Window.Resources>
    <Style x:Key="buttonMade" TargetType="Button">
        <Setter Property="Background" Value="Green"/>
    </Style>
</Window.Resources>
<Grid>
    <Button Width="100" Height="30" Content="버튼" Style="{StaticResource buttonMade}"/>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153520278-e0b5509a-6be5-4c02-8952-480d1c4e8751.png">

<br/>
<br/>

###### [Style](#style)
###### [Top](#top)

## TargetType속성으로 적용시킬 컨트롤 지정
  - Style TargetType="{x:Type 적용시킬 컨트롤}" : Style에서 지정한 '적용시킬 컨트롤'에 합당한 컨트롤이 자동으로 Style이 지정된다.

#MainWindow.xaml
~~~c#
<Window.Resources>
    <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="Green"/>
    </Style>
</Window.Resources>
<Grid>
    <Button Width="100" Height="30" Content="버튼"/>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153520278-e0b5509a-6be5-4c02-8952-480d1c4e8751.png">

<br/>
<br/>

###### [Style](#style)
###### [Top](#top)

## 각각의 자식 컨트롤에 Style 적용하기
  - 각각의 컨트롤 안쪽에만 적용하기 위해서는, 적용시킬 컨트롤을 포함하고 있는 상위 컨트롤에 Resources로 적용시키면됨

#MainWindow.xaml
~~~c#
<StackPanel>
    <Button Width="100" Height="30" Content="버튼1"/>
    <Button Width="100" Height="30" Content="버튼2"/>
    <StackPanel>
        <StackPanel.Resources>
            <Style TargetType="{x:Type Button}">
                <Setter Property="Background" Value="Green"/>
            </Style>
        </StackPanel.Resources>
        <Button Width="100" Height="30" Content="버튼3"/>
        <Button Width="100" Height="30" Content="버튼4"/>
    </StackPanel>
</StackPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153521272-6ced1d45-fe90-44fa-aa44-453a75d3bb7a.png">

<br/>
<br/>

###### [Style](#style)
###### [Top](#top)

## BasedOn을 이용한 Style상속

#MainWindow.xaml
~~~c#
<Window.Resources>
    <Style x:Key="buttonMade_basedon" TargetType="Button">
        <Setter Property="Background" Value="Green"/>
    </Style>

    <Style x:Key="buttonMade" TargetType="Button" BasedOn="{StaticResource buttonMade_basedon}">
        <Setter Property="Foreground" Value="White"/>
    </Style>
</Window.Resources>
    
<StackPanel>
    <Button Width="100" Height="30" Content="버튼1" Style="{StaticResource buttonMade}"/>
    <Button Width="100" Height="30" Content="버튼2" Style="{StaticResource buttonMade_basedon}"/>
</StackPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153522477-2d98af56-993f-4ec3-9b60-0a369f38903a.png">

###### [Style](#style)
###### [Top](#top)

<br/>
<br/>

# FrameworkElement

###### [Top](#top)

<br/>

***

<br/>

# Decorator
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement

###### [FrameworkElement](#frameworkelement)
###### [Top](#top)

# Border
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Decorator
  - 모서리를 동그랗게 만들어줌

<br/>

- BorderBrush : 테두리 컬러 지정
- BorderThickness : 테두리 두계 설정("2 2 2 2" 이런 형태로 왼쪽,위쪽,오른쪽,아래로 각각 설정도 가능)
- CornerRadius : 모서리를 얼마나 동그랗게 만들껀지("2 2 2 2"이런식으로 모서리 별로 설정 가능)

~~~
<Grid>
    <Border Width="100" Height="100" CornerRadius="10 2 2 2" BorderBrush="Coral" BorderThickness="2 2 2 10">
    </Border>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/151305860-78bd39a9-da06-4e70-8daf-318e54a4640f.png">

###### [Decorator](#decorator)
###### [Top](#top)

<br/>

***

<br/>

# TextBlock
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement
  - [Run](#run)

<br/>

#MainWindow.xaml
~~~c#
<Grid>
    <Border BorderBrush="Black" BorderThickness="1" Width="100" Height="100">
        <TextBlock Width="100" Height="100">11111<LineBreak/>22222</TextBlock>
    </Border>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/151999032-9aa3f1e3-a989-4739-b5a4-fa33f103aedb.png">


###### [FrameworkElement](#frameworkelement)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ


## Run
  - Text내용을 자체 텍스트 컨트롤로 취급할 수 있게 해준다.

#MainWindow.xaml
~~~c#
<Grid>
    <Border BorderBrush="Black" BorderThickness="1" Width="100" Height="100">
        <TextBlock Width="100" Height="100">
            <Run>[</Run>
            <Run Text="{Binding tb1}"></Run>
            <Run>,</Run>
            <Run Text="{Binding tb2}"></Run>
            <Run>]</Run>
        </TextBlock>
    </Border>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/151999752-67c9fc8f-b853-430b-9d50-1f94e4139aa9.png">

###### [TextBlock](#textblock)
###### [Top](#top)

<br/>

***

<br/>

# Popup
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement
  - [Placement, HorizontalOffset, VerticalOffset, AllowsTransparency, IsOpen](#placement-horizontaloffset-verticaloffset-allowstransparency-isopen)
  - [AllowsTransparency(False일때)](#allowstransparencyfalse일때)
  - [AllowsTransparency(True일때)](#allowstransparencytrue일때)

<br/>

  - Placement : 어디서 팝업창이 뜰지 알려줌
  - HorizontalOffset : 팝업 위치를 옮길 수 있음
  - VerticalOffset : 팝업 위치를 옮길 수 있음
  - AllowsTransparency : 팝업창의 배경을 투명으로 할 수 있음
  - IsOpen : 팝업을 띄워주고 닫아줌 

###### [FrameworkElement](#frameworkelement)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## Placement, HorizontalOffset, VerticalOffset, AllowsTransparency, IsOpen

#MainWindow.xaml
~~~c#
<Grid>
    <Button Width="100" Height="25" Content="Popuptest" Click="Button_Click"/>
    <Popup Name="Pop"
        Placement="Top"
        HorizontalOffset="-100"
        VerticalOffset="0"
        AllowsTransparency="True">
        <Menu>
            <StackPanel Orientation="Vertical">
                <MenuItem Header="사과"/>
                <MenuItem Header="포도"/>
                <MenuItem Header="귤"/>
                <MenuItem Header="배"/>
            </StackPanel>
        </Menu>
    </Popup>
</Grid>
~~~

<br/>

#MainWindow.xaml.cs
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    private void Button_Click(object sender, RoutedEventArgs e)
    {
        Pop.IsOpen = !(Pop.IsOpen);
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/152073966-9993fda4-80c5-4aec-b2e2-7d0b6df20db6.png">

###### [Popup](#popup)
###### [Top](#top)

<br/>
<br/>

## AllowsTransparency(False일때)
  - False 일때, Ellipse주변에 검정색 Background가 남아 있다

#MainWindow.xaml
~~~c#
<Grid>
    <Button Width="100" Height="25" Content="Popuptest" Click="Button_Click"/>
    <Popup Name="Pop"
    Placement="Top"
    HorizontalOffset="-100"
    VerticalOffset="0"
    AllowsTransparency="False">
        <Ellipse Width="200" Height="200" Fill="Bisque"/>
    </Popup>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152074233-11a3764f-b8a7-4724-ac7c-27b3dcaede9e.png">

###### [Popup](#popup)
###### [Top](#top)

<br/>
<br/>

## AllowsTransparency(True일때)
  - True 일때, Ellipse주변에 검정색 Background가 없어 진다

#MainWindow.xaml
~~~
<Grid>
    <Button Width="100" Height="25" Content="Popuptest" Click="Button_Click"/>
    <Popup Name="Pop"
    Placement="Top"
    HorizontalOffset="-100"
    VerticalOffset="0"
    AllowsTransparency="True">
        <Ellipse Width="200" Height="200" Fill="Bisque"/>
    </Popup>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152074570-a17fe31b-78ef-4f8f-873d-0474d8229dbc.png">

###### [Popup](#popup)
###### [Top](#top)

<br/>

***

<br/>

# Panel
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement

<br/>

  - [Grid](#grid)
  - [Canvas](#canvas)
  - [DockPanel](#dockpanel)
  - [StackPanel](#stackpanel)
  - [WrapPanel](#wrappanel)
  - [Viewbox](#viewbox)
  - [UniformGrid](#uniformgrid)

###### [FrameworkElement](#frameworkelement)
###### [Top](#top)

<br/>

***

<br/>

# Grid
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel

<br/>

  - [다양한 요소안에 Grid를 만들기](#다양한-요소안에-grid를-만들기)
  - [IsSharedSizeScope속성을 이용해 Grid의 폭과 넓이 맟주기](#issharedsizescope속성을-이용해-grid의-폭과-넓이-맟주기)

<br/>

  - number : number만큼의 크기를 설정(화면크기를 임의로 늘려도 요소가 늘어나지X)
  - Auto : Grid가 가지고 있는 하위 content의 크기만큼의 크기를 가짐
  - number* : 남은 공간을 등분하여 크기를 가짐 ex) 2* 과 1* : 남은 크기를 2:1비율로 가져감(화면크기를 임의로 늘리면 요소가 늘어남)  

#MainWindow.xaml
~~~c#
    <Grid> 
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="100"/>
            <RowDefinition Height="100"/>
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="100"/>
            <ColumnDefinition Width="2*"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        
        <Button Grid.Column="0" Grid.Row="0" Content="버튼1"/>
        <Button Grid.Column="1" Grid.Row="0" Content="버튼2"/>
        <Button Grid.Column="2" Grid.Row="0" Content="버튼3"/>
        <Button Grid.Column="0" Grid.Row="1" Content="버튼4"/>
        <Button Grid.Column="1" Grid.Row="1" Content="버튼5"/>
        <Button Grid.Column="2" Grid.Row="1" Content="버튼6"/>
        <Button Grid.Column="0" Grid.Row="2" Content="버튼7"/>
        <Button Grid.Column="1" Grid.Row="2" Content="버튼8"/>
        <Button Grid.Column="2" Grid.Row="3" Content="버튼9"/>
    </Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/147874900-2aab4125-8b19-4c41-9804-d39d12ac353b.png">

###### [Panel](#panel)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## 다양한 요소안에 Grid를 만들기

#MainWindow.xaml
~~~c#
<Button Grid.Column="2" Height="150" Width="150">
    <Grid Width="150" Height="150">
        <Grid.RowDefinitions>
            <RowDefinition Height="7*"/>
            <RowDefinition Height="3*"/>
        </Grid.RowDefinitions>
        <Image Source="사진" Grid.Row="0"/>
    </Grid>
</Button>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148070083-3a53e213-6cbc-43dd-88b6-81cba330675f.png">

###### [Grid](#grid)
###### [Top](#top)

<br/>
<br/>

## IsSharedSizeScope속성을 이용해 Grid의 폭과 넓이 맟주기

#MainWindow.xaml
~~~c#
<Grid Grid.IsSharedSizeScope="True">
    <Grid.RowDefinitions>
        <RowDefinition/>
        <RowDefinition/>
    </Grid.RowDefinitions>

    <Grid Grid.Row="0">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="100" SharedSizeGroup="FirstLine"/>
            <ColumnDefinition Width="Auto" SharedSizeGroup="SecondLine"/>
            <ColumnDefinition Width="Auto" SharedSizeGroup="ThedLine"/>
            <ColumnDefinition Width="Auto" SharedSizeGroup="ForeLine"/>
        </Grid.ColumnDefinitions>

        <Border  Grid.Column="0" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock Text="사과" FontSize="30"/>
        </Border>
        <Border Grid.Column="1" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock Text="포도" FontSize="30"/>
        </Border>
        <Border Grid.Column="2" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock Text="바나나" FontSize="30"/>
        </Border>
        <Border Grid.Column="3" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock  Text="파인애플" FontSize="30"/>
        </Border>
    </Grid>

    <Grid Grid.Row="1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" SharedSizeGroup="FirstLine"/>
            <ColumnDefinition Width="Auto" SharedSizeGroup="SecondLine"/>
            <ColumnDefinition Width="Auto" SharedSizeGroup="ThedLine"/>
            <ColumnDefinition Width="Auto" SharedSizeGroup="ForeLine"/>
        </Grid.ColumnDefinitions>

        <Border  Grid.Column="0" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock Text="asdfasdf" FontSize="30"/>
        </Border>
        <Border Grid.Column="1" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock Text="23123" FontSize="30"/>
        </Border>
        <Border Grid.Column="2" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock Text="cbnvmhikt" FontSize="30"/>
        </Border>
        <Border Grid.Column="3" Background="#dfdfdf" BorderBrush="#adadad" BorderThickness="3">
            <TextBlock  Text="sekfj0384kjlsadfif" FontSize="30"/>
        </Border>
    </Grid>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148079616-5703ff5f-5acd-4e5a-b50f-35f8e8008ad7.png">

###### [Grid](#grid)
###### [Top](#top)

<br/>

***

<br/>

# Canvas
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel
  - 위치를 고정으로 정할때 사용함. 임의로 화면을 늘려도 상,하,좌,우 를 기준으로 고정된 지점에 요소가 놓아짐

<br/>

#MainWindow.xaml
~~~c#
<Canvas Name="canvas">
    <TextBlock Name="txtBlock" Canvas.Left="10" TextWrapping="Wrap" Text="캔버스" Canvas.Top="80"/>
    <Button Name="btn" Content="Button" Canvas.Left="172" Canvas.Top="30" Width="75"/>
    <Image Name="image2"
            Source="https://user-images.githubusercontent.com/39178978/148183688-8de89977-ca68-4450-87e7-6febcff80fd4.png"
            Canvas.Left="10" Canvas.Top="150"/>
</Canvas>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148184087-350a7029-8e58-48b7-8297-5127d51825f7.png">

###### [Panel](#panel)
###### [Top](#top)

<br/>

***

<br/>

# DockPanel
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel
  - 자식요소를 기준으로 가로 또는 세로로 정렬 할 수 있는 영역을 정의

#MainWindow.xaml
~~~c#
<DockPanel Name="dp1">
    <Border DockPanel.Dock="Top" Background="Yellow" Height="20" BorderBrush="Red" BorderThickness="2">
        <TextBlock Text="Dock=top"/>
    </Border>
    <Border DockPanel.Dock="Bottom" Background="Aqua" BorderBrush="Blue" BorderThickness="5">
        <TextBlock Text="Dock=bottom"/>
    </Border>
    <Border DockPanel.Dock="Left" Background="DarkBlue" Width="100" BorderBrush="Bisque" BorderThickness="10">
        <TextBlock Text="Left" Foreground="Wheat"/>
    </Border>
    <Border Background="Brown" BorderBrush="Azure" BorderThickness="10">
        <TextBlock Text="All"/>
    </Border>
</DockPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148200531-fbd1db72-a493-4b85-820a-ca096662102f.png">

###### [Panel](#panel)
###### [Top](#top)

<br/>

***

<br/>

# StackPanel
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel
  - 자식 요소들을 행이나 열로 나열

<br/>

  - [Orientation="Horizontal"](#orientationhorizontal)

###### [Panel](#panel)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## Orientation="Horizontal"
 - 정렬 방향을 수평으로 바꿀 수 있음

#MainWindow.xaml
~~~c#
<Grid>
    <StackPanel Name="sp1" Width="90" Height="150" HorizontalAlignment="Left" VerticalAlignment="Top">
        <Button Name="btn1" Width="70" Height="25" Content="버튼1"/>
        <Button Name="btn2" Width="70" Height="25" Content="버튼2"/>
        <Button Name="btn3" Width="70" Height="25" Content="버튼3"/>
        <Button Name="btn4" Width="70" Height="25" Content="버튼4"/>
        <Button Name="btn5" Width="70" Height="55" Content="버튼5"/>
    </StackPanel>
    <StackPanel Name="sp2" Width="250" Margin="50 10 10 10" Orientation="Horizontal">
        <Rectangle Height="50" Width="50" Stroke="Black" Fill="AntiqueWhite"/>
        <Rectangle Height="50" Width="50" Stroke="Black" Fill="SaddleBrown"/>
        <Rectangle Height="50" Width="50" Stroke="Black" Fill="Black"/>
    </StackPanel>
</Grid>
~~~

<br/>

<img src="https://user-images.githubusercontent.com/39178978/148635073-d7d3a64d-81c6-48a3-b9d0-4f370a1d124c.png">

###### [StackPanel](#stackpanel)
###### [Top](#top)

<br/>

***

<br/>

# WrapPanel
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel
  - 자신의 영역보다 작은 자식요소들이 있는 경우에 stackPanel과 같은 기능, 반대로 자식요소들의 사이즈가 더 큰 경우에는 다음줄로 배치됨
  - WrapPanel은 stackpanel과는 다르게 창을 줄였을 경우 요소들이 공간을 초과하면 밑으로 내려간다

<br/>

  - [Orientation="Vertical"](#orientationvertical)

#MainWindow.xaml
~~~c#
<WrapPanel Name="wp1" VerticalAlignment="Top">
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="RosyBrown" Name="rec1"/>
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="BurlyWood" Name="rec2"/>
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="SeaShell" Name="rec3"/>
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="DarkSlateGray" Name="rec4"/>
</WrapPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148635573-8d994ef7-8c0f-403d-b535-78f0ab45cb80.png">

<br/>

여기서 창을 줄이면

<br/>

<img src="https://user-images.githubusercontent.com/39178978/148635594-dfe37a6a-08cf-49d8-baf5-a2a6e81e7874.png">

###### [Panel](#panel)
###### [Top](#top)

<br/>
<br/>

## Orientation="Vertical"
  - 수직으로 배치가능하게 함
 
#MainWindow.xaml
~~~c#
<WrapPanel Name="wp1" VerticalAlignment="Top" Orientation="Vertical">
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="RosyBrown" Name="rec1"/>
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="BurlyWood" Name="rec2"/>
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="SeaShell" Name="rec3"/>
    <Rectangle Height="60" Width="50" Stroke="Black" Fill="DarkSlateGray" Name="rec4"/>
</WrapPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148635530-4eef554c-df65-434b-9c70-a9e9bf3b31ec.png">

<br/>

여기서 창을 줄이면

<br/>

<img src="https://user-images.githubusercontent.com/39178978/148635557-b0904ba7-1de7-4d20-8548-d90ddbe79d16.png">

###### [WrapPanel](#wrappanel)
###### [Top](#top)

<br/>

***

<br/>

# Viewbox
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel
  - 화면의 크기를 늘리고 줄였을때 그 안에 요소들을 일정한 비율로 늘리고 줄일 수 있음

<br/>

  - [Stretch](#stretch)
  - [StretchDirection](#stretchdirection)

###### [Panel](#panel)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## Stretch

- None : 자식 컨트롤의 크기가 변경되지 않음.(ViewBox크기에 따라 여백이 생기거나 클리핑)
- Fill : 자식 컨트롤이 ViewBox를 완전히 채우도록 크기가 조절된다.(절대 클리핑되지 않는다) 종횡비율(가로,세로 크기의 비율)이 다를 수 있으므로 ViewBox의 내용이 변형될 수 있다.
- Uniform : ViewBox의 기본 옵션. 자식컨트롤이 가로, 세로 크기에 맞게 균일하게 크기조절
- UniformToFill : ViewBox의 크기를 모두 채우는데,  자식 컨트롤의 가로와 세로의 비율을 동일한 비율로 조정한다.왜곡 현상이 없도록 하기 위해서 자식 컨트롤이 잘리는 현상이 일어날 수 있다.

#MainWindow.xaml
~~~c#
<Grid>
    <Viewbox>
        <StackPanel>
            <Button Width="100" Height="100" Content="1"/>
            <Button Width="100" Height="100" Content="2"/>
            <Button Width="100" Height="100" Content="3"/>
            <Button Width="100" Height="100" Content="4"/>
        </StackPanel>
    </Viewbox>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/148673507-8e1abe94-d180-47ab-8db7-cbaea328c5f1.png">

###### [Viewbox](#viewbox)
###### [Top](#top)

<br/>
<br/>

## StretchDirection

- Both(기본값) : 콘텐츠의 기본 크기에 비례하여 위아래로 크기 조정
- UpOnly : 기본 크기보다 큰 크기에서만 크기조정을 허용
- DownOnly : 기본 크기보다 작은 크기에서만 조절이 가능

###### [Viewbox](#viewbox)
###### [Top](#top)

<br/>

***

<br/>

# UniformGrid
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Panel
  - 모든 열,행을 자동으로 똑같이 맞춰줌, 크기를 조절 불가능함

<br/>

  - [Columns,Rows지정](#columnsrows지정)
  - [ClipToBounds](#cliptobounds)
  - [FirstColumn](#firstcolumn)
  - [FlowDirection](#flowdirection)

#MainWindow.xaml
~~~c#
<UniformGrid>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
</UniformGrid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/149927550-e3de207c-7c2b-4e82-b2ce-9ea0f9b95212.png" width="300" height="300">

###### [Panel](#panel)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## Columns,Rows지정
  - 지정한 열,행을 넘어가면 프로그램을 실행했을때 화면에 표현되지 않고 무시하게 됨

#MainWindow.xaml
~~~c#
<UniformGrid Columns="2" Rows="3">
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
</UniformGrid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/149928111-0ae3e057-d526-4e0a-816f-97a899e85214.png">

<br/>

빨간색 테두리가 실행 화면

<br/>

<img src="https://user-images.githubusercontent.com/39178978/149928370-36e15e1c-c3e7-4e48-b6f5-fcd3c2f9c84a.png">

###### [UniformGrid](#uniformgrid)
###### [Top](#top)

<br/>
<br/>

## ClipToBounds
  - 내 크기를 벗어난 요소들을 사라지게 할 수 있음

#MainWindow.xaml
~~~c#
<UniformGrid Columns="2" Rows="3" ClipToBounds="True">
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
    <Button Content="버튼1"></Button>
</UniformGrid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/149928819-757fbb07-4bc2-475d-9fd7-746c796cc6d4.png">

###### [UniformGrid](#uniformgrid)
###### [Top](#top)

<br/>
<br/>

## FirstColumn
  - 그 순서 부터 시작할 수 있음

#MainWindow.xaml
~~~c#
<UniformGrid Rows="3" Columns="3" FirstColumn="2">
    <Button Content="button1"/>
    <Button Content="button2"/>
    <Button Content="button3"/>
    <Button Content="button4"/>
    <Button Content="button5"/>
    <Button Content="button5"/>
</UniformGrid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/149929403-9ba21762-33f5-4ed1-9982-c61cf276d527.png">

###### [UniformGrid](#uniformgrid)
###### [Top](#top)

<br/>
<br/>

## FlowDirection
  - 방향을 반대로 바꿀 수 있음

#MainWindow.xaml
~~~c#
<UniformGrid Rows="3" Columns="3" FirstColumn="2" FlowDirection="RightToLeft">
    <Button Content="button1"/>
    <Button Content="button2"/>
    <Button Content="button3"/>
    <Button Content="button4"/>
    <Button Content="button5"/>
    <Button Content="button5"/>
</UniformGrid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/149929712-91144101-18c8-41fe-800e-e09e6dab4b03.png">

###### [UniformGrid](#uniformgrid)
###### [Top](#top)

<br/>

***

<br/>

# Control
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement
  - TabIndex(int값) : Tab키를 눌렀을때 이동하는 순서를 나타낸다
  - IsTabStop(boll값) : Tab키를 눌렀을때 지나치게 됨

<br/>

  - [Separator](#separator)
  - [PasswordBox](#passwordbox)
  - [Thumb](#thumb)
  - [RangeBase](#rangebase)
  - [TextBoxBase](#textboxbase)
  - [ContentControl](#contentcontrol)
  - [ItemsControl](#ItemsControl)

###### [FrameworkElement](#frameworkelement)
###### [Top](#top)

<br/>

***

<br/>

# Separator
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control
  - 구분짓는 선을 만들어줌

#MainWindow.xaml
~~~c#
<Grid>
    <StatusBar Height="100" HorizontalAlignment="Center">
        <TextBlock Text="구분"/>
        <Separator/>
        <Button Content="구분"/>
        <Separator/>
        <TextBlock Text="구분"/>
    </StatusBar>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/150148233-147bd185-e175-42e1-9073-375bb2246c0d.png">

###### [Control](#control)
###### [Top](#top)

<br/>

***

<br/>

# PasswordBox
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control
  - TextBox와는 다르게, 비밀번호처럼 감춰지는 형태로 사용할 수 있다
  - 'Text'속성 대신 'Password'속성을 이용하여 글자 입력
  - PasswordChar속성을 이용해서 비밀번호가 감춰질때 의 도형 설정 가능

#MainWindow.xaml
~~~c#
<Grid>
    <PasswordBox Width="100" Password="비밀번호" VerticalAlignment="Center"/>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/153541148-8bd20629-0fd4-4fed-a57e-2e193201a6ef.png">

###### [Control](#control)
###### [Top](#top)

<br/>

***

<br/>

# Thumb
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control
  - Thumb클래스 안에는 끌기와 관련된 것들을 제공하는것이 있음
    - DragStarted 이벤트 : 드래그 하기 시작할 때 발생하는 이벤트
    - DragCompleted 이벤트 : 사용자가 드래그를 중지하고 마우스 버튼을 놓았을 때 발생하는 이벤트
    - DragDelta 이벤트 : 마우스를 움직이면 반복적으로 이벤트가 발생한다.
    - IsDragging 속성 : 사용자가 드래그를 하는 동안에는 true, 드래그가 중지되면 false를 리턴한다.
    - CancelDrag 메소드 : 이 메소드를 호출하면 드래그 작업이 즉시 중지된다.

###### [Control](#control)
###### [Top](#top)

# GridSplitter
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control - Thumb
  - 마우스 드래그앤 드랍으로 끌수 있는 선을 만듬
  - ShowsPreview : 마우스로 끌어서 옮길때 미리보기를 할지 안할지 설정

<br/>

  - [DragStarted. DragCompleted, DragDelta, IsDragging, CancelDrag](#dragstarted-dragcompleted-dragdelta-isdragging-canceldrag)

#MainWindow.xaml
~~~c#
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="1*"/>
        <RowDefinition Height="1*"/>
        <RowDefinition Height="1*"/>
    </Grid.RowDefinitions>

    <Grid Grid.Row="0"/>

    <GridSplitter Grid.Row="1" Height="5" Background="red" HorizontalAlignment="Stretch" ShowsPreview="True"/>

    <Grid Grid.Row="2"/>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152299296-11475d66-9c58-438a-adda-bf7f81c905d4.png">

###### [Thumb](#thumb)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## DragStarted. DragCompleted, DragDelta, IsDragging, CancelDrag
  - Thumb클래스에서 상속받아 사용

#MainWindow.xaml
~~~c#
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="1*"/>
        <RowDefinition Height="1*"/>
        <RowDefinition Height="1*"/>
    </Grid.RowDefinitions>

    <Grid Grid.Row="0"/>
    <TextBox x:Name="tb" Grid.Row="0" Width="100" Height="30"/>

    <GridSplitter Grid.Row="1" Height="5" Background="red" HorizontalAlignment="Stretch" ShowsPreview="True" DragStarted="GridSplitter_DragStarted"/>

    <Grid Grid.Row="2"/>
</Grid>
~~~

<br/>

#XAML.cs
~~~
using System.Windows.Controls.Primitives;

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    private void GridSplitter_DragStarted(object sender, DragStartedEventArgs e)
    {
        tb.Text = "드래그 시작";
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/152470717-b07933bd-b3a1-425d-b825-5a5f9af888a0.png">

###### [GridSplitter](#gridsplitter)
###### [Top](#top)

<br/>

***

<br/>

# RangeBase
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control
  - [ProgressBar](#progressbar)
  - [Slider](#slider)

###### [Control](#control)
###### [Top](#top)

<br/>

***

<br/>

# ProgressBar
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control - RangeBase
  - bar형태의 컨트롤 생성
  - Minimum : ProgressBar의 최소값 설정
  - Maximum : ProgressBar의 최대값 설정

<br/>

  - [IsIndeterminate](#isindeterminate)

#MainWindow.xaml
~~~c#
<StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
    <TextBlock Text="로딩중" VerticalAlignment="Center" Margin="0 0 10 0"/>
    <ProgressBar Width="100" Height="30" Value="30"/>
</StackPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152511866-40517ab8-2852-450b-b8a8-ac440eb24a36.png">

###### [RangeBase](#rangebase)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## IsIndeterminate
  - true일 경우

#MainWindow.xaml
~~~c#
<StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
    <TextBlock Text="로딩중" VerticalAlignment="Center" Margin="0 0 10 0"/>
    <ProgressBar Width="100" Height="30" Value="30" IsIndeterminate="True"/>
</StackPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152512413-748e0114-3c63-4fbd-859c-b79482c9efe3.png">

###### [ProgressBar](#progressbar)
###### [Top](#top)

<br/>

***

<br/>

# Slider
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control - RangeBase
  - Minimum 속성 : 최소 작은수 지정
  - Maximum 속성 : 최대 큰 수 지정
  - IsDirectionReversed : 슬라이더의 최대, 최소값의 위치가 바뀜(true이면 최대 최소의 방향이 바뀐다)

<br/>

  - [ValueChanged이벤트로 R,G,B값 표현하기](#valuechanged이벤트로-rgb값-표현하기)
  - [ValueChanged이벤트로 R,G,B,A값 표현하기](#valuechanged이벤트로-rgba값-표현하기)
  - [Orientation속성](#orientation속성)
  - [TickPlacement속성(눈금표시)](#tickplacement속성눈금표시)

###### [RangeBase](#rangebase)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## ValueChanged이벤트로 R,G,B값 표현하기
  - 슬라이더의 Value값의 변경을 감지하면 발생하는 이벤트

#MainWindow.xaml
~~~c#
<StackPanel VerticalAlignment="Center">
    <Slider x:Name="Red_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Slider x:Name="Green_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Slider x:Name="Blue_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Rectangle x:Name="rec" Width="100" Height="100"/>
</StackPanel>
~~~

<br/>

#MainWindow.xaml.cs
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    private void ValueChanged(object sender, RoutedPropertyChangedEventArgs<double> e)
    {
        var colorR = (byte)Red_slider.Value;
        var colorG = (byte)Green_slider.Value;
        var colorB = (byte)Blue_slider.Value;

        var color = Color.FromRgb(colorR, colorG, colorB);

        rec.Fill = new SolidColorBrush(color);
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/156905759-405d0d68-7c25-43ea-a891-056f94ae35e8.png">

###### [Slider](#slider)
###### [Top](#top)

<br/>
<br/>

## ValueChanged이벤트로 R,G,B,A값 표현하기
  - 슬라이더의 Value값의 변경을 감지하면 발생하는 이벤트

#MainWindow.xaml
~~~c#
<StackPanel VerticalAlignment="Center">
    <Slider x:Name="Red_slider" Maximum="255" Minimum="0" Margin="10"
        ValueChanged="ValueChanged"/>
    <Slider x:Name="Green_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Slider x:Name="Blue_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Slider x:Name="A_silder" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Rectangle x:Name="rec" Width="100" Height="100"/>
</StackPanel>
~~~

<br/>

#MainWindow.xaml.CS
~~~c#
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }

    private void ValueChanged(object sender, RoutedPropertyChangedEventArgs<double> e)
    {
        var colorR = (byte)Red_slider.Value;
        var colorG = (byte)Green_slider.Value;
        var colorB = (byte)Blue_slider.Value;
        var colorA = (byte)A_silder.Value;

        var color = Color.FromArgb(colorA, colorR, colorG, colorB);

        rec.Fill = new SolidColorBrush(color);
    }
}
~~~

<img src="https://user-images.githubusercontent.com/39178978/156906074-7f9e7cbb-1f3d-4b19-9e51-94728cc6973c.png">

###### [Slider](#slider)
###### [Top](#top)

<br/>
<br/>

## Orientation속성
  - 가로 및 세로 방향을 지정 가능

#MainWindow.xaml
~~~c#
<StackPanel VerticalAlignment="Center">
    <Slider x:Name="Red_slider" Maximum="255" Minimum="0" Margin="10" Orientation="Vertical"  ValueChanged="ValueChanged"
        Height="100"/>
    <Slider x:Name="Green_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Slider x:Name="Blue_slider" Maximum="255" Minimum="0" Margin="10" ValueChanged="ValueChanged"/>
    <Rectangle x:Name="rec" Width="100" Height="100"/>
</StackPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/156905872-8881619d-6b72-424e-8cf3-4286f49b676b.png">

###### [Slider](#slider)
###### [Top](#top)

<br/>
<br/>

## TickPlacement속성(눈금표시)
  - None : 슬라이더의 기본값으로 눈금이 숨겨져 있는 상태
  - TopLeft : 가로슬라이더는 위쪽에 표시 또는 세로슬라이더는 왼쪽에 표시
  - BottomRight : 가로 슬라이더는 아래쪽에 표시 또는 세로 슬라이더는 오른쪽에 표시
  - Both : 가로 슬라이더는 위아래 표시 또는 세로 슬라이더는 좌우에 표시
  - TickFrequency : 눈금의 갯수를 조절

#MainWindow.xaml
~~~c#
<StackPanel VerticalAlignment="Center">
    <Slider x:Name="Red_slider" Maximum="255" Minimum="0" Margin="10"
        ValueChanged="ValueChanged"
        Height="100"
        TickPlacement="Both"
        TickFrequency="5"/>
</StackPanel>
~~~

<img src="https://user-images.githubusercontent.com/39178978/156905997-b90525ab-d615-42fc-9fdb-933676cab050.png">

###### [Slider](#slider)
###### [Top](#top)

<br/>

***

<br/>

# TextBoxBase
  - 상속 : Object - DispatcherObject - DependencyObject - Visual - UIElement - FrameworkElement - Control

###### [Control](#control)
###### [Top](#top)

# TextBox
  - 사용자가 Box내부에 string을 적을 수 있는 컨텐트
  - [AcceptsReturn, AcceptsTab, VerticalScrollBarVisibility, MaxLength, CharacterCasing](#acceptsreturn-acceptstab-verticalscrollbarvisibility-maxlength-charactercasing)
  - [TextChanged이벤트, SelectionChanged이벤트](#textchanged이벤트-selectionchanged이벤트)
  - [SelectedText, CaretIndex, SelectionStart, SelectionLength, Select(1,4), SelectAllAll()](#selectedtext-caretindex-selectionstart-selectionlength-select14-selectallall)

<br/>

###### [TextBoxBase](#textboxbase)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## AcceptsReturn, AcceptsTab, VerticalScrollBarVisibility, MaxLength, CharacterCasing
  - AcceptsReturn="True" 속성 : 엔터키를 사용 할 수 있게함
  - AcceptsTab="True" 속성 : 텝키를 사용 할 수 있게함
  - VerticalScrollBarVisibility="Auto" 속성 : TextBox안의 공간보다 길이 길어지면 자동으로 wrap해줌
  - MaxLength 속성 : 글자수를 제한해줌
  - CharacterCasing 속성 : 자동으로 대문자 소문자로 입력되게 함

###### [TextBox](#textbox)
###### [Top](#top)

<br/>
<br/>

## TextChanged이벤트, SelectionChanged이벤트
  - TextChanged 이벤트 : 글자가 바뀔 때마다 이벤트를 실행하게함(TextBox안에 글자가 지정되어 있으면 예외가 발생하여 실행이 안됨)
  - SelectionChanged 이벤트 : 선택한 텍스트를 변경하거나 캐럿을 이동할 때 발생하는 이벤트, 마우스나 키보드 등의 입력장치를 사용해서 선택을 조정할 때마다 발생하는 이벤트

###### [TextBox](#textbox)
###### [Top](#top)

<br/>
<br/>

## SelectedText, CaretIndex, SelectionStart, SelectionLength, Select(1,4), SelectAllAll()
  - SelectedText : 마우스 드래그로 선택한 텍스트를 가져옴
  - CaretIndex : 캐럿의 위치를 설정
  - SelectionStart : 선택한 텍스트가 시작되는 위치값(CaretIndex와 같은 값을 리턴)
  - SelectionLength : 선택된 문자 수를 반환, 선택 문자가 없으면 0을 리턴
  - Select(1,4) : 마우스로 드래그 하는 것과 같다, ex)현재 예시는 1이상 4미만의 인덱스를 표시함
  - SelectAllAll() : 마우스로 드래그 하는 것과 같다, 전체 선택

###### [TextBox](#textbox)
###### [Top](#top)

<br/>

***

<br/>

# ContentControl
  - [ScrollViewer](#ScrollViewer)
  - [ToolTip](#tooltip)
  - [ButtonBase](#ButtonBase)
  - [HeaderedContentControl](#HeaderedContentControl)

###### [Control](#control)
###### [Top](#top)

<br/>

***

<br/>

# ScrollViewer
  - ScrollViewer내부에 있는 객체들을 스크롤로 나타내줌
  - 기본적으로, VerticalScrollBarVisibility="Visible"로 되어 있기 때문에 VerticalScrollBarVisibility="Hidden"을 해줘야 수직 스크롤 막대가 없어짐
  - [FrameworkElement를 이용해 ScrollViewer의 시스템 whith사이즈를 불러오기](#frameworkelement를-이용해-scrollviewer의-시스템-whith사이즈를-불러오기)
  - [HorizontalScrollBarVisibility, VerticalScrollBarVisibility(visible, Hidden, Auto, Disabled)](#horizontalscrollbarvisibility-verticalscrollbarvisibilityvisible-hidden-auto-disabled)

###### [ContentControl](#contentcontrol)
###### [Top](#top)

#### ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

## HorizontalScrollBarVisibility, VerticalScrollBarVisibility(visible, Hidden, Auto, Disabled)
  - HorizontalScrollBarVisibility : 수평 스크롤 막대 속성
  - VerticalScrollBarVisibility : 수직 스크롤 막대 속성
    - visible : 스크롤바 막대를 항상 표시, ScrollViewer 크기가 자식 내용보다 작을 경우에는 활성화 상태, 반대로 ScrollViewer크기가 자식 내용보다 클 경우에는 비활성화 상태가 된다.
    - Hidden : 스크롤 막대가 숨겨져 있도록 하는 속성, 자식 내용이 ScrollViewer보다 클 경우에는 내용이 잘리게 된다. 스크롤휠을 내려서 확인 가능하다
    - Auto : 스크롤이 필요 없을 만큼 창크기를 늘려주면 스크롤이 없어짐(필요한 경우에만 표시됨)
    - Disabled : 스크롤이 아예 없어짐, 창 크기를 밑으로 내려야지만 내용이 보임

#Mainwindow.xaml
~~~c#
<ScrollViewer VerticalScrollBarVisibility="Visible">
    <StackPanel>
        <TextBlock Background="red" Text="tb1" Height="50" TextAlignment="Center" FontSize="20"/>
        <TextBlock Background="DarkGray" Text="tb2" Height="50" TextAlignment="Center" FontSize="20"/>
        <TextBlock Background="Cyan" Text="tb3" Height="50" TextAlignment="Center" FontSize="20"/>
        <TextBlock Background="Blue" Text="tb4" Height="50" TextAlignment="Center" FontSize="20"/>
        <TextBlock Background="DarkKhaki" Text="tb5" Height="50" TextAlignment="Center" FontSize="20"/>
        <TextBlock Background="red" Text="tb6" Height="50" TextAlignment="Center" FontSize="20"/>
        <TextBlock Background="DarkGray" Text="tb7" Height="50" TextAlignment="Center" FontSize="20"/>
    </StackPanel>
</ScrollViewer>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152088288-d03304dc-49c9-4aa8-b698-be87473247bd.png">

###### [ScrollViewer](#ScrollViewer)
###### [Top](#top)

<br/>
<br/>

## FrameworkElement를 이용해 ScrollViewer의 시스템 whith사이즈를 불러오기
  - FrameworkElement : 아무것도 없는 공간이라고 생각하면 됨

#Mainwindow.xaml
~~~c#
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition/>
        <ColumnDefinition/>
        <ColumnDefinition Width="Auto"/>
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
        <RowDefinition Height="1*"/>
        <RowDefinition Height="10*"/>
    </Grid.RowDefinitions>

    <Border BorderBrush="Black" BorderThickness="1" Grid.Row="0" Grid.Column="0">
        <TextBlock Text="1" Background="#c1c1c1"/>
    </Border>
    <Border BorderBrush="Black" BorderThickness="1" Grid.Row="0" Grid.Column="1" >
        <TextBlock Text="1" Background="#c1c1c1"/>
    </Border>
    <Border Grid.Row="0" Grid.Column="2" HorizontalAlignment="Right" Background="#c1c1c1">
        <FrameworkElement Grid.Row="0" Grid.Column="2" Width="{DynamicResource {x:Static SystemParameters.VerticalScrollBarWidthKey}}"/>
    </Border>

    <ScrollViewer VerticalScrollBarVisibility="Visible" Grid.Row="1" Grid.Column="0" Grid.ColumnSpan="3">
        <StackPanel>
            <TextBlock Background="red" Text="tb1" Height="50" TextAlignment="Center" FontSize="20"/>
            <TextBlock Background="DarkGray" Text="tb2" Height="50" TextAlignment="Center" FontSize="20"/>
            <TextBlock Background="Cyan" Text="tb3" Height="50" TextAlignment="Center" FontSize="20"/>
            <TextBlock Background="Blue" Text="tb4" Height="50" TextAlignment="Center" FontSize="20"/>
            <TextBlock Background="DarkKhaki" Text="tb5" Height="50" TextAlignment="Center" FontSize="20"/>
            <TextBlock Background="red" Text="tb6" Height="50" TextAlignment="Center" FontSize="20"/>
            <TextBlock Background="DarkGray" Text="tb7" Height="50" TextAlignment="Center" FontSize="20"/>
        </StackPanel>
    </ScrollViewer>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152091900-c7834135-e50c-4e4f-a8d2-722a35cc0d70.png">

###### [ScrollViewer](#ScrollViewer)
###### [Top](#top)

<br/>

***

<br/>

# tooltip
  - ToolTip : 마우스를 올렸을때 나오는 설명창(ToolTip)

#MainWindow.xaml
~~~c#
<Grid>
    <TextBox Width="100" Height="30">
        <TextBox.ToolTip>
            <TextBlock Text="숫자를 입력하세요"/>
        </TextBox.ToolTip>
    </TextBox>
</Grid>
~~~

<img src="https://user-images.githubusercontent.com/39178978/152283585-98284fcf-ae1c-48b8-b6d9-2ba1f978d815.png">

###### [ContentControl](#contentcontrol)
###### [Top](#top)