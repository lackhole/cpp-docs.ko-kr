---
title: 파일 처리 및 I-o (C + + /cli CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- .NET Framework [C++], file handling
- files [C++], .NET Framework and
- I/O [C++], .NET Framework applications
- .NET Framework [C++], I/O
- files [C++], listing files
- directories [C++], listing files
- monitoring file system events
- FileSystemWatcher class, examples
- examples [C++], monitoring file system changes
- events [C++], monitoring
- file system events [C++]
- files [C++], binary
- binary files, reading in C++
- reading text files
- text files, reading
- files [C++], retrieving information about
- FileInfo class
- binary files, writing in C++
- files [C++], binary
- files [C++], text
- text files, writing in C++
ms.assetid: 3296fd59-a83a-40d4-bd4a-6096cc13101b
ms.openlocfilehash: 7009c0b017c403c3f0108aa84b8ddb25a1d1564f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749375"
---
# <a name="file-handling-and-io-ccli"></a>파일 처리 및 I/O(C++/CLI)

.NET Framework를 사용 하 여 다양 한 파일 작업 방법을 보여 줍니다.

다음 항목에 정의 된 클래스의 사용을 보여 줍니다.는 <xref:System.IO> 파일 작업을 수행 하는 다양 한 네임 스페이스입니다.

## <a name="enumerate"></a> 디렉터리의 파일 열거

다음 코드 예제에서는 디렉터리의 파일 목록을 검색 하는 방법에 설명 합니다. 또한 하위 디렉터리 열거 됩니다. 다음 코드 예제에서는 합니다 <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetFiles%2A> 고 <xref:System.IO.Directory.GetDirectories%2A> C:\Windows 디렉터리의 내용을 표시 하는 방법입니다.

### <a name="example"></a>예제

```cpp
// enum_files.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   String^ folder = "C:\\";
   array<String^>^ dir = Directory::GetDirectories( folder );
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);
   for (int i=0; i<dir->Length; i++)
      Console::WriteLine(dir[i]);

   array<String^>^ file = Directory::GetFiles( folder );
   Console::WriteLine("--== Files inside '{0}' ==--", folder);
   for (int i=0; i<file->Length; i++)
      Console::WriteLine(file[i]);

   return 0;
}
```

## <a name="monitor"></a> 파일 시스템 변경 사항 모니터링

다음 코드 예제에서는 <xref:System.IO.FileSystemWatcher> 생성, 변경, 삭제 또는 이름이 바뀐 파일에 해당 하는 이벤트에 대 한 등록 합니다. 파일 변경에 대 한 디렉터리를 주기적으로 폴링 대신 사용할 수 있습니다는 <xref:System.IO.FileSystemWatcher> 변경이 감지 될 때 이벤트를 발생 시키는 클래스입니다.

### <a name="example"></a>예제

```cpp
// monitor_fs.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::IO;

ref class FSEventHandler
{
public:
    void OnChanged (Object^ source, FileSystemEventArgs^ e)
    {
        Console::WriteLine("File: {0} {1}",
               e->FullPath, e->ChangeType);
    }
    void OnRenamed(Object^ source, RenamedEventArgs^ e)
    {
        Console::WriteLine("File: {0} renamed to {1}",
                e->OldFullPath, e->FullPath);
    }
};

int main()
{
   array<String^>^ args = Environment::GetCommandLineArgs();

   if(args->Length < 2)
   {
      Console::WriteLine("Usage: Watcher.exe <directory>");
      return -1;
   }

   FileSystemWatcher^ fsWatcher = gcnew FileSystemWatcher( );
   fsWatcher->Path = args[1];
   fsWatcher->NotifyFilter = static_cast<NotifyFilters>
              (NotifyFilters::FileName |
               NotifyFilters::Attributes |
               NotifyFilters::LastAccess |
               NotifyFilters::LastWrite |
               NotifyFilters::Security |
               NotifyFilters::Size );

    FSEventHandler^ handler = gcnew FSEventHandler();
    fsWatcher->Changed += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Created += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Deleted += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Renamed += gcnew RenamedEventHandler(
            handler, &FSEventHandler::OnRenamed);

    fsWatcher->EnableRaisingEvents = true;

    Console::WriteLine("Press Enter to quit the sample.");
    Console::ReadLine( );
}
```

## <a name="read_binary"></a> 이진 파일 읽기

다음 코드 예제에서 두 개의 클래스를 사용 하 여 파일에서 이진 데이터를 읽는 방법을 합니다 <xref:System.IO?displayProperty=fullName> 네임 스페이스: <xref:System.IO.FileStream> 고 <xref:System.IO.BinaryReader>입니다. <xref:System.IO.FileStream> 실제 파일을 나타냅니다. <xref:System.IO.BinaryReader> 스트림에 이진 액세스를 허용 하는 인터페이스를 제공 합니다.

코드 예제에서는 이름이 data.bin이 고 이진 형식의 정수를에서 포함 하는 파일을 읽습니다. 이런이 종류의 파일에 대 한 정보를 참조 하세요. [방법: 이진 파일 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md)합니다.

### <a name="example"></a>예제

```cpp
// binary_read.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "data.bin";
   try
   {
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);
      BinaryReader^ br = gcnew BinaryReader(fs);

      Console::WriteLine("contents of {0}:", fileName);
      while (br->BaseStream->Position < br->BaseStream->Length)
         Console::WriteLine(br->ReadInt32().ToString());

      fs->Close( );
   }
   catch (Exception^ e)
   {
      if (dynamic_cast<FileNotFoundException^>(e))
         Console::WriteLine("File '{0}' not found", fileName);
      else
         Console::WriteLine("Exception: ({0})", e);
      return -1;
   }
   return 0;
}
```

## <a name="read_text"></a> 텍스트 파일 읽기

다음 코드 예제에서는 열고 사용 하 여 한 번에 텍스트 파일을 한 줄씩 읽는 방법을 보여 줍니다.는 <xref:System.IO.StreamReader> 에 정의 된 클래스는 <xref:System.IO?displayProperty=fullName> 네임 스페이스입니다. 이 클래스 인스턴스의 텍스트 파일을 여는 고 된 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> 메서드 사용은 각 줄.

이 코드 예제에서는 텍스트가 포함 된 textfile.txt 라는 파일을 읽습니다. 이런이 종류의 파일에 대 한 정보를 참조 하세요. [방법: 텍스트 파일 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md)합니다.

### <a name="example"></a>예제

```cpp
// text_read.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "textfile.txt";
   try
   {
      Console::WriteLine("trying to open file {0}...", fileName);
      StreamReader^ din = File::OpenText(fileName);

      String^ str;
      int count = 0;
      while ((str = din->ReadLine()) != nullptr)
      {
         count++;
         Console::WriteLine("line {0}: {1}", count, str );
      }
   }
   catch (Exception^ e)
   {
      if (dynamic_cast<FileNotFoundException^>(e))
         Console::WriteLine("file '{0}' not found", fileName);
      else
         Console::WriteLine("problem reading file '{0}'", fileName);
   }

   return 0;
}
```

## <a name="retrieve"></a> 파일 정보 검색

다음 코드 예제는 <xref:System.IO.FileInfo> 클래스입니다. 파일 이름의 경우, 생성 및 마지막으로 수정한 파일 크기, directory, 전체 이름 및 날짜 및 시간과 같은 파일에 대 한 정보를 검색할이 클래스를 사용할 수 있습니다.

이 코드는 Notepad.exe 파일 정보를 검색 합니다.

### <a name="example"></a>예제

```cpp
// file_info.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   array<String^>^ args = Environment::GetCommandLineArgs();
   if (args->Length < 2)
   {
      Console::WriteLine("\nUSAGE : file_info <filename>\n\n");
      return -1;
   }

   FileInfo^ fi = gcnew FileInfo( args[1] );

   Console::WriteLine("file size: {0}", fi->Length );

   Console::Write("File creation date:  ");
   Console::Write(fi->CreationTime.Month.ToString());
   Console::Write(".{0}", fi->CreationTime.Day.ToString());
   Console::WriteLine(".{0}", fi->CreationTime.Year.ToString());

   Console::Write("Last access date:  ");
   Console::Write(fi->LastAccessTime.Month.ToString());
   Console::Write(".{0}", fi->LastAccessTime.Day.ToString());
   Console::WriteLine(".{0}", fi->LastAccessTime.Year.ToString());

   return 0;
}
```

## <a name="write_binary"></a> 이진 파일 쓰기

다음 코드 예제에서는 이진 데이터를 파일로 작성 하는 방법을 보여 줍니다. 두 개의 클래스를 <xref:System.IO> 되는 네임 스페이스: <xref:System.IO.FileStream> 및 <xref:System.IO.BinaryWriter>합니다. <xref:System.IO.FileStream> 실제 파일을 나타내는 동안 <xref:System.IO.BinaryWriter> 스트림에 이진 액세스를 허용 하는 인터페이스를 제공 합니다.

다음 코드 예제에서는 이진 형식의 정수를에서 포함 하는 파일을 씁니다. 이 파일의 코드를 읽을 수 있는 [방법: 이진 파일 읽기 (C + + /cli CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md)합니다.

### <a name="example"></a>예제

```cpp
// binary_write.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   array<Int32>^ data = {1, 2, 3, 10000};

   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);
   BinaryWriter^ w = gcnew BinaryWriter(fs);

   try
   {
      Console::WriteLine("writing data to file:");
      for (int i=0; i<data->Length; i++)
      {
         Console::WriteLine(data[i]);
         w->Write(data[i]);
      }
   }
   catch (Exception^)
   {
     Console::WriteLine("data could not be written");
     fs->Close();
     return -1;
   }

   fs->Close();
   return 0;
}
```

## <a name="write_text"></a> 텍스트 파일 쓰기

다음 코드 예제에서는 텍스트 파일을 만들고 사용 하 여 텍스트를 작성 하는 방법을 보여 줍니다 합니다 <xref:System.IO.StreamWriter> 클래스에 정의 되어 있는 <xref:System.IO> 네임 스페이스입니다. <xref:System.IO.StreamWriter> 생성자 만들려는 파일의 이름입니다. 파일이 있으면 덮어씁니다 (두 번째 True를 전달 하지 않으면 <xref:System.IO.StringWriter> 생성자 인수).

파일을 사용 하 여 제출 후은 <xref:System.IO.StreamWriter.Write%2A> 및 <xref:System.IO.TextWriter.WriteLine%2A> 함수입니다.

### <a name="example"></a>예제

```cpp
// text_write.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "textfile.txt";

   StreamWriter^ sw = gcnew StreamWriter(fileName);
   sw->WriteLine("A text file is born!");
   sw->Write("You can use WriteLine");
   sw->WriteLine("...or just Write");
   sw->WriteLine("and do {0} output too.", "formatted");
   sw->WriteLine("You can also send non-text objects:");
   sw->WriteLine(DateTime::Now);
   sw->Close();
   Console::WriteLine("a new file ('{0}') has been written", fileName);

   return 0;
}
```

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[파일 및 스트림 I/O](/dotnet/standard/io/index)<br/>
[System.IO 네임 스페이스](/dotnet/api/system.io)
