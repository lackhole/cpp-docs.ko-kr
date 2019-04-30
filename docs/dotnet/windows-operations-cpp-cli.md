---
title: Windows 작업(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows [C++], Windows-specific tasks
- .NET Framework [C++], Windows operations
- Visual C++, Windows operations
- Windows operations [C++]
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
- Visual C++, user interactive state
- user interactive state
- Visual C++, reading from Windows Registry
- registry, reading
- performance counters
- performance counters, reading Windows performance counters
- performance monitoring, Windows performance counters
- performance, counters
- counters, reading Windows performance counters
- performance
- performance monitoring
- text, retrieving from Clipboard
- Clipboard, retrieving text
- current user names
- user names, retrieving
- UserName string
- .NET Framework, version
- Version property, retrieving .NET Framework version
- computer name, retrieving
- machine name, retrieving
- computer name
- Windows [C++], version
- Windows [C++], retrieving version using Visual C++
- time, elapsed since startup
- counters, elapsed time
- startup, time elapsed since
- tick counts
- startup
- text, storing in Clipboard
- Clipboard, storing text
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: b9a75cb4-0589-4d5b-92cb-5e8be42b4ac0
ms.openlocfilehash: 413ccc3b66d76f8779861d4d65eb262ee8640725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384377"
---
# <a name="windows-operations-ccli"></a>Windows 작업(C++/CLI)

Windows SDK를 사용 하 여 다양 한 Windows 관련 작업을 보여 줍니다.

다음 항목에서는 시각적 개체를 사용 하 여 Windows SDK를 사용 하 여 수행 하는 다양 한 Windows 작업 설명 C++입니다.

## <a name="determine_shutdown"></a> 종료 프로세스 시작 확인

다음 코드 예제에서는 응용 프로그램 또는.NET Framework는 현재 종료 여부를 결정 하는 방법에 설명 합니다. 종료 하는 동안 이러한 구문은 시스템에 의해 종료 되 고 안정적으로 사용할 수 없습니다 때문에.NET Framework의 정적 요소에 액세스 하기 위한 유용 합니다. 확인 하 여는 <xref:System.Environment.HasShutdownStarted%2A> 속성 먼저 이러한 요소에 액세스 하지 하 여 잠재적인 오류를 방지할 수 있습니다.

### <a name="example"></a>예제

```cpp
// check_shutdown.cpp
// compile with: /clr
using namespace System;
int main()
{
   if (Environment::HasShutdownStarted)
      Console::WriteLine("Shutting down.");
   else
      Console::WriteLine("Not shutting down.");
   return 0;
}
```

## <a name="determine_user"></a> 사용자 대화형 상태 확인

다음 코드 예제에는 코드는 대화형 사용자 컨텍스트에서 실행 되는지 여부를 확인 하는 방법을 보여 줍니다. 경우 <xref:System.Environment.UserInteractive%2A> 가 false 이면 서비스 프로세스로 실행 중인 코드 또는에서 웹 응용 프로그램을 내부 경우 해서는 사용자와 상호 작용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// user_interactive.cpp
// compile with: /clr
using namespace System;

int main()
{
   if ( Environment::UserInteractive )
      Console::WriteLine("User interactive");
   else
      Console::WriteLine("Noninteractive");
   return 0;
}
```

## <a name="read_registry"></a> Windows 레지스트리에서 데이터 읽기

다음 코드 예제에서는 <xref:Microsoft.Win32.Registry.CurrentUser> Windows 레지스트리에서 데이터 읽기에 대 한 키입니다. 먼저 하위 키를 사용 하 여 열거 됩니다는 <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> 메서드를 Identities 하위 키를 사용 하 여을 열릴는 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> 메서드. 각 하위 키가 나타내는 루트 키와 마찬가지로 <xref:Microsoft.Win32.RegistryKey> 클래스입니다. 마지막으로, 새 <xref:Microsoft.Win32.RegistryKey> 개체의 키/값 쌍을 열거 하는 데 사용 됩니다.

### <a name="example"></a>예제

```cpp
// registry_read.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main( )
{
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );

   Console::WriteLine("Subkeys within CurrentUser root key:");
   for (int i=0; i<key->Length; i++)
   {
      Console::WriteLine("   {0}", key[i]);
   }

   Console::WriteLine("Opening subkey 'Identities'...");
   RegistryKey^ rk = nullptr;
   rk = Registry::CurrentUser->OpenSubKey("Identities");
   if (rk==nullptr)
   {
      Console::WriteLine("Registry key not found - aborting");
      return -1;
   }

   Console::WriteLine("Key/value pairs within 'Identities' key:");
   array<String^>^ name = rk->GetValueNames( );
   for (int i=0; i<name->Length; i++)
   {
      String^ value = rk->GetValue(name[i])->ToString();
      Console::WriteLine("   {0} = {1}", name[i], value);
   }

   return 0;
}
```

### <a name="remarks"></a>설명

합니다 <xref:Microsoft.Win32.Registry> 클래스는 정적 인스턴스의 컨테이너 단순히 <xref:Microsoft.Win32.RegistryKey>합니다. 각 인스턴스는 루트 레지스트리 노드를 나타냅니다. 인스턴스가 <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>합니다 <xref:Microsoft.Win32.Registry.LocalMachine>, 및 <xref:Microsoft.Win32.Registry.Users>합니다.

또한으로 정적 내의 개체는 <xref:Microsoft.Win32.Registry> 클래스는 읽기 전용입니다. 또한 인스턴스의 <xref:Microsoft.Win32.RegistryKey> 레지스트리의 내용에 액세스 하기 위해 만든 클래스 개체도 읽기 전용입니다. 이 동작을 재정의 하는 방법의 예제를 참조 하세요. [방법: Windows 레지스트리에 데이터 쓰기 (C++/CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)합니다.

두 가지 추가 개체에는 <xref:Microsoft.Win32.Registry> 클래스: <xref:Microsoft.Win32.Registry.DynData> 고 <xref:Microsoft.Win32.Registry.PerformanceData>입니다. 둘 다의 인스턴스는 <xref:Microsoft.Win32.RegistryKey> 클래스입니다. <xref:Microsoft.Win32.Registry.DynData> Windows 98 및 me. Windows 에서만 지원 되는 동적 레지스트리 정보를 포함 하는 개체 <xref:Microsoft.Win32.Registry.PerformanceData> Windows 성능 모니터링 시스템을 사용 하는 응용 프로그램에 대 한 성능 카운터 정보에 액세스 하려면 개체를 사용할 수 있습니다. <xref:Microsoft.Win32.Registry.PerformanceData> 노드는 실제로 레지스트리에 저장 되지 않으며 따라서 볼 수 없습니다 Regedit.exe를 사용 하는 정보를 나타냅니다.

## <a name="read_performance"></a> Windows 성능 카운터 읽기

일부 응용 프로그램 및 Windows 하위 시스템에는 Windows 성능 시스템을 통해 성능 데이터를 노출합니다. 이러한 카운터를 사용 하 여 액세스할 수 있습니다 합니다 <xref:System.Diagnostics.PerformanceCounterCategory> 및 <xref:System.Diagnostics.PerformanceCounter> 에 상주 하는 클래스에는 <xref:System.Diagnostics?displayProperty=fullName> 네임 스페이스입니다.

다음 코드 예제에서는 이러한 클래스를 사용 하 여 검색 하 고 프로세서를 사용 하는 시간의 백분율을 나타내기 위해 Windows에서 업데이트 되는 카운터를 표시 합니다.

> [!NOTE]
>  이 예제를 Windows Vista에서 실행하려면 관리 권한이 필요합니다.

### <a name="example"></a>예제

```cpp
// processor_timer.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Diagnostics;
using namespace System::Timers;

ref struct TimerObject
{
public:
   static String^ m_instanceName;
   static PerformanceCounter^ m_theCounter;

public:
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)
   {
      try
      {
         Console::WriteLine("CPU time used: {0,6} ",
          m_theCounter->NextValue( ).ToString("f"));
      }
      catch(Exception^ e)
      {
         if (dynamic_cast<InvalidOperationException^>(e))
         {
            Console::WriteLine("Instance '{0}' does not exist",
                  m_instanceName);
            return;
         }
         else
         {
            Console::WriteLine("Unknown exception... ('q' to quit)");
            return;
         }
      }
   }
};

int main()
{
   String^ objectName = "Processor";
   String^ counterName = "% Processor Time";
   String^ instanceName = "_Total";

   try
   {
      if ( !PerformanceCounterCategory::Exists(objectName) )
      {
         Console::WriteLine("Object {0} does not exist", objectName);
         return -1;
      }
   }
   catch (UnauthorizedAccessException ^ex)
   {
      Console::WriteLine("You are not authorized to access this information.");
      Console::Write("If you are using Windows Vista, run the application with ");
      Console::WriteLine("administrative privileges.");
      Console::WriteLine(ex->Message);
      return -1;
   }

   if ( !PerformanceCounterCategory::CounterExists(
          counterName, objectName) )
   {
      Console::WriteLine("Counter {0} does not exist", counterName);
      return -1;
   }

   TimerObject::m_instanceName = instanceName;
   TimerObject::m_theCounter = gcnew PerformanceCounter(
          objectName, counterName, instanceName);

   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);
   aTimer->Interval = 1000;
   aTimer->Enabled = true;
   aTimer->AutoReset = true;

   Console::WriteLine("reporting CPU usage for the next 10 seconds");
   Thread::Sleep(10000);
   return 0;
}
```

## <a name="retrieve_text"></a> 클립보드에서 텍스트 검색

다음 코드 예제에서는 합니다 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 멤버 함수에 대 한 포인터를 반환 하는 <xref:System.Windows.Forms.IDataObject> 인터페이스입니다. 이 인터페이스 데이터 형식에 대 한 쿼리 고 실제 데이터를 검색 하는 데 사용 될 수 있습니다.

### <a name="example"></a>예제

```cpp
// read_clipboard.cpp
// compile with: /clr
#using <system.dll>
#using <system.Drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main( )
{
   IDataObject^ data = Clipboard::GetDataObject( );

   if (data)
   {
      if (data->GetDataPresent(DataFormats::Text))
      {
         String^ text = static_cast<String^>
           (data->GetData(DataFormats::Text));
         Console::WriteLine(text);
      }
      else
         Console::WriteLine("Nontext data is in the Clipboard.");
   }
   else
   {
      Console::WriteLine("No data was found in the Clipboard.");
   }

   return 0;
}
```

## <a name="retrieve_current"></a> 현재 사용자 이름 검색

다음 코드 예제에서는 현재 사용자 이름 (Windows 로그인 사용자 이름)를 검색 하는 방법을 보여 줍니다. 이름에 저장 됩니다는 <xref:System.Environment.UserName%2A> 에 정의 되어 있는 문자열을 <xref:System.Environment> 네임 스페이스입니다.

### <a name="example"></a>예제

```cpp
// username.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);
   return 0;
}
```

## <a name="retrieve_dotnet"></a> .NET Framework 버전 검색

다음 코드 예제에 사용 하 여 현재 설치 된.NET Framework의 버전을 확인 하는 방법을 보여 줍니다.는 <xref:System.Environment.Version%2A> 속성에 대 한 포인터에는 <xref:System.Version> 버전 정보를 포함 하는 개체입니다.

### <a name="example"></a>예제

```cpp
// dotnet_ver.cpp
// compile with: /clr
using namespace System;
int main()
{
   Version^ version = Environment::Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write(".NET Framework version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
            build, major, minor, revision);
   }
   return 0;
}
```

## <a name="retrieve_local"></a> 로컬 컴퓨터 이름 검색

다음 코드 예제에서는 로컬 컴퓨터 이름 검색 (네트워크에서 표시 되는 컴퓨터의 이름). 가져와서이 수행할 수 있습니다는 <xref:System.Environment.MachineName%2A> 에 정의 되어 있는 문자열을 <xref:System.Environment> 네임 스페이스입니다.

### <a name="example"></a>예제

```cpp
// machine_name.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);
   return 0;
}
```

## <a name="retrieve_version"></a> Windows 버전 검색

다음 코드 예제에서는 현재 운영 체제의 플랫폼 및 버전 정보를 검색 하는 방법에 설명 합니다. 이 정보에 저장 됩니다는 <xref:System.Environment.OSVersion%2A?displayProperty=fullName> 속성 넓은 의미에서 Windows의 버전을 설명 하는 열거형으로 구성 됩니다 및 <xref:System.Environment.Version%2A> 운영 체제의 정확한 빌드를 포함 하는 개체입니다.

### <a name="example"></a>예제

```cpp
// os_ver.cpp
// compile with: /clr
using namespace System;

int main()
{
   OperatingSystem^ osv = Environment::OSVersion;
   PlatformID id = osv->Platform;
   Console::Write("Operating system: ");

   if (id == PlatformID::Win32NT)
      Console::WriteLine("Win32NT");
   else if (id == PlatformID::Win32S)
      Console::WriteLine("Win32S");
   else if (id == PlatformID::Win32Windows)
      Console::WriteLine("Win32Windows");
   else
      Console::WriteLine("WinCE");

   Version^ version = osv->Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write("OS Version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
                   build, major, minor, revision);
   }

   return 0;
}
```

## <a name="retrieve_time"></a> 시작 후 경과한 시간 검색

다음 코드 예제에는 틱 수를 결정 하는 방법을 보여 줍니다. 또는 Windows 이후 경과 된 시간 (밀리초) 시작 되었습니다. 이 값은 <xref:System.Environment.TickCount%2A?displayProperty=fullName> 멤버는 32 비트 값 이기 때문에 0으로 다시 설정은 및입니다.

### <a name="example"></a>예제

```cpp
// startup_time.cpp
// compile with: /clr
using namespace System;

int main( )
{
   Int32 tc = Environment::TickCount;
   Int32 seconds = tc / 1000;
   Int32 minutes = seconds / 60;
   float hours = static_cast<float>(minutes) / 60;
   float days = hours / 24;

   Console::WriteLine("Milliseconds since startup: {0}", tc);
   Console::WriteLine("Seconds since startup: {0}", seconds);
   Console::WriteLine("Minutes since startup: {0}", minutes);
   Console::WriteLine("Hours since startup: {0}", hours);
   Console::WriteLine("Days since startup: {0}", days);

   return 0;
}
```

## <a name="store_text"></a> 클립보드에 텍스트 저장

다음 코드 예제에서는 합니다 <xref:System.Windows.Forms.Clipboard> 에 정의 된 개체는 <xref:System.Windows.Forms> 네임 스페이스 문자열을 저장 합니다. 이 개체는 두 멤버 함수를 제공 합니다. <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 고 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>입니다. 데이터에서 파생 된 개체를 전송 하 여 클립보드에 저장 됩니다 <xref:System.Object> 에 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>입니다.

### <a name="example"></a>예제

```cpp
// store_clipboard.cpp
// compile with: /clr
#using <System.dll>
#using <System.Drawing.dll>
#using <System.Windows.Forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main()
{
   String^ str = "This text is copied into the Clipboard.";

   // Use 'true' as the second argument if
   // the data is to remain in the clipboard
   // after the program terminates.
   Clipboard::SetDataObject(str, true);

   Console::WriteLine("Added text to the Clipboard.");

   return 0;
}
```

## <a name="write_data"></a> Windows 레지스트리에 데이터 쓰기

다음 코드 예제에서는 합니다 <xref:Microsoft.Win32.Registry.CurrentUser> 의 쓰기 가능한 인스턴스를 만드는 키를 <xref:Microsoft.Win32.RegistryKey> 클래스에 해당 하는 **소프트웨어** 키입니다. <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> 메서드는 다음 새 키 만들기 및 키/값 쌍으로 추가 하는 데 사용 됩니다.

### <a name="example"></a>예제

```cpp
// registry_write.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main()
{
   // The second OpenSubKey argument indicates that
   // the subkey should be writable.
   RegistryKey^ rk;
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);
   if (!rk)
   {
      Console::WriteLine("Failed to open CurrentUser/Software key");
      return -1;
   }

   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");
   if (!nk)
   {
      Console::WriteLine("Failed to create 'NewRegKey'");
      return -1;
   }

   String^ newValue = "NewValue";
   try
   {
      nk->SetValue("NewKey", newValue);
      nk->SetValue("NewKey2", 44);
   }
   catch (Exception^)
   {
      Console::WriteLine("Failed to set new values in 'NewRegKey'");
      return -1;
   }

   Console::WriteLine("New key created.");
   Console::Write("Use REGEDIT.EXE to verify ");
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");
   return 0;
}
```

### <a name="remarks"></a>설명

.NET Framework를 사용 하 여 사용 하 여 레지스트리에 액세스 하는 <xref:Microsoft.Win32.Registry> 및 <xref:Microsoft.Win32.RegistryKey> 둘 다를 수 있는 클래스에 정의 <xref:Microsoft.Win32> 네임 스페이스입니다. 합니다 **레지스트리** 클래스의 정적 인스턴스에 대 한 컨테이너인는 <xref:Microsoft.Win32.RegistryKey> 클래스입니다. 각 인스턴스는 루트 레지스트리 노드를 나타냅니다. 인스턴스가 <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>합니다 <xref:Microsoft.Win32.Registry.LocalMachine>, 및 <xref:Microsoft.Win32.Registry.Users>합니다.

## <a name="related-sections"></a>관련 단원

<xref:System.Environment>

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
