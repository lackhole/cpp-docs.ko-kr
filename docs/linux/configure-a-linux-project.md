---
title: Visual Studio에서 C++ Linux 프로젝트 구성
ms.date: 11/12/2018
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
ms.openlocfilehash: 84b9242ad5af79ed48d716fb5a35db56428e9a98
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57808367"
---
# <a name="configure-a-linux-project"></a>Linux 프로젝트 구성

이 토픽에서는 Visual Studio에서 Linux 프로젝트 템플릿을 기반으로 하는 C++ Linux 프로젝트를 구성하는 방법을 설명합니다. Visual Studio에서 CMake Linux 프로젝트에 대한 자세한 내용은 [Linux CMake 프로젝트 구성](cmake-linux-project.md)을 참조하세요.

## <a name="general-settings"></a>일반 설정

Visual Studio를 사용하여 Linux 프로젝트에 대해 다양한 옵션을 구성할 수 있습니다.  이러한 옵션을 보려면 **프로젝트 > 속성** 메뉴를 선택하거나 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **속성**을 선택합니다. **일반 설정**이 나타납니다.

![일반 구성](media/settings_general.png)

기본적으로는 실행 파일(.out)은 도구를 사용하여 빌드됩니다.  정적 또는 동적 라이브러리를 빌드하거나 기존 메이크파일을 사용하려면 **구성 형식** 선택을 사용합니다.

속성 페이지의 옵션에 대한 자세한 내용은 [Linux 프로젝트 속성 페이지 참조](prop-pages-linux.md)를 참조하세요.

## <a name="remote-settings"></a>원격 설정

원격 Linux 컴퓨터와 관련된 설정을 변경하려면 [일반](prop-pages/general-linux.md) 설정에 표시되는 원격 옵션을 구성합니다.

- 대상 Linux 컴퓨터를 변경하려면 **원격 빌드 컴퓨터** 항목을 사용합니다.  이렇게 하면 이전에 만든 연결 중 하나를 선택할 수 있습니다.  새 항목을 만들려면 [Connecting to Your Remote Linux Computer](connect-to-your-remote-linux-computer.md)(원격 Linux 컴퓨터에 연결) 섹션을 참조하세요.

- **원격 빌드 루트 디렉터리**는 프로젝트가 원격 Linux 컴퓨터에서 빌드되는 루트 위치를 결정합니다.  달리 변경하지 않은 경우 기본값은 **~/projects**로 설정됩니다.

- **원격 빌드 프로젝트 디렉터리**는 원격 Linux 컴퓨터에서 이 특정 프로젝트가 빌드되는 위치입니다.  기본값은 **$(RemoteRootDir)/$(ProjectName)** 이며, 위에 설정된 루트 디렉터리 아래의 현재 프로젝트를 따라 명명된 디렉터리로 확장됩니다.

> [!NOTE]
> 프로젝트를 빌드하는 데 사용되는 기본 C 및 C++ 컴파일러 또는 링커 및 보관기를 변경하려면 **C/C++ > 일반** 섹션 및 **링커 > 일반** 섹션에서 적절한 항목을 사용합니다.  예를 들어 이러한 항목은 GCC 또는 Clang 컴파일러의 특정 버전을 사용하여 설정할 수 있습니다. 자세한 내용은 [C/C++ 속성(Linux C++)](prop-pages/c-cpp-linux.md) 및 [링커 속성(Linux C++)](prop-pages/linker-linux.md)을 참조하세요.

## <a name="include-directories-and-intellisense-support"></a>디렉터리 및 IntelliSense 지원 포함

**Visual Studio 2017 버전 15.6 이하**:<br/>
기본적으로 Visual Studio에는 Linux 컴퓨터의 모든 시스템 수준 포함 파일이 포함되지 않습니다.  예를 들어 **/usr/include** 디렉터리의 항목은 Visual Studio에 없습니다.
완전한 [IntelliSense](/visualstudio/ide/using-intellisense) 지원을 위해서는, 개발 컴퓨터의 일부 위치로 해당 파일을 복사하고 Visual Studio에 이 위치를 가리켜야 합니다.  한 가지 방법은 scp(보안 복사)를 사용하여 파일을 복사합니다.  Windows 10에서 [Bash on Windows](https://msdn.microsoft.com/commandline/wsl/about)(Windows의 Bash)를 사용하여 scp를 실행할 수 있습니다.  이전 버전의 Windows에서는 [PSCP(PuTTY 보안 복사)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)와 같은 방법을 사용할 수 있습니다.

다음과 비슷한 명령을 사용하여 파일을 복사할 수 있습니다.

`scp -r linux_username@remote_host:/usr/include .`

물론, 위의 **linux_username** 및 **remote_host** 값을 자신의 환경에 적절한 값으로 바꾸세요.

파일이 복사되면 프로젝트 속성의 **VC++ 디렉터리** 항목을 사용하여 Visual Studio에 방금 복사된 추가 포함 파일을 찾을 수 있는 위치를 알려줍니다.

![VC++ 디렉터리](media/settings_directories.png)

**Visual Studio 2017 버전 15.7 이상:**<br/>
[IntelliSense에 대한 원격 헤더 관리](#remote_intellisense)를 참조하세요.

## <a name="copy-sources"></a>소스 복사

빌드할 때 개발 PC의 소스 파일이 Linux 컴퓨터에 복사되어 해당 컴퓨터에서 컴파일됩니다.  기본적으로 Visual Studio 프로젝트의 모든 소스가 위의 설정에 지정된 위치에 복사됩니다.  그러나 추가 소스가 목록에 추가되거나, 소스 복사가 완전히 꺼질 수 있습니다(메이크파일 프로젝트에 대한 기본값).

- **복사할 소스**가 원격 컴퓨터에 복사되는 소스를 결정합니다.  기본적으로 **\@(SourcesToCopyRemotely)** 는 프로젝트의 모든 소스 코드 파일로 설정되지만 이미지와 같은 자산/리소스 파일은 포함하지 않습니다.

- **소스 복사**는 원격 컴퓨터에 소스 파일 복사를 사용하거나 사용하지 않기 위해 켜거나 끌 수 있습니다.

- **복사할 추가 소스**를 통해 원격 시스템에 복사되는 추가 소스 파일을 추가할 수 있습니다.  세미콜론으로 구분된 목록을 지정하거나 **:=** 구문으로 사용할 로컬 및 원격 이름을 지정할 수 있습니다.

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>빌드 이벤트

원격 컴퓨터에서 모든 컴파일이 수행된 후 몇 가지 추가 빌드 이벤트가 프로젝트 속성의 빌드 이벤트 섹션에 추가되었습니다.  이들은 **원격 빌드 전 이벤트**, **원격 링크 전 이벤트** 및 **빌드 후 이벤트 제거**이며, 프로세스의 개별 단계 전 또는 후에 원격 컴퓨터에서 발생합니다.

![빌드 이벤트](media/settings_buildevents.png)

## <a name="remote_intellisense"></a> 원격 헤더용 IntelliSense(Visual Studio 2017 버전 15.7 이상)

**연결 관리자**에서 새 연결을 추가하면 Visual Studio는 원격 시스템의 컴파일러용 포함 디렉터리를 자동으로 검색합니다. 그런 다음, Visual Studio는 해당 파일을 압축하여 로컬 Windows 컴퓨터의 디렉터리에 복사합니다. 그러면 Visual Studio 또는 CMake 프로젝트에서 해당 연결을 사용할 때마다 해당 디렉터리의 헤더가 IntelliSense를 제공하는 데 사용됩니다.

이 기능은 zip이 설치된 Linux 컴퓨터에 따라 다릅니다. 이 apt-get 명령을 사용하여 zip을 설치할 수 있습니다.

```cmd
apt install zip
```

헤더 캐시를 관리하려면 **도구 > 옵션, 플랫폼 간 > 연결 관리자> 원격 헤더 IntelliSense 관리자**로 이동합니다. Linux 컴퓨터에서 변경한 후 헤더 캐시를 업데이트하려면 원격 연결을 선택한 후 **업데이트**를 선택합니다. 연결 자체를 삭제하지 않고 헤더를 제거하려면 **삭제**를 선택합니다. **탐색**을 선택하여 **파일 탐색기**에서 로컬 디렉터리를 엽니다. 이 폴더를 읽기 전용으로 취급합니다. 15.3 이전 버전에서 작성된 기존 연결의 헤더를 다운로드하려면 연결을 선택한 후 **다운로드**를 선택합니다.

![원격 헤더 IntelliSense](media/remote-header-intellisense.png)

## <a name="see-also"></a>참고 항목

[컴파일러 설정 및 빌드 속성](../build/working-with-project-properties.md)<br/>
[C++ 일반 속성(Linux C++)](../linux/prop-pages/general-linux.md)<br/>
[VC++ 디렉터리(Linux C++)](../linux/prop-pages/directories-linux.md)<br/>
[소스 복사 프로젝트 속성(Linux C++)](../linux/prop-pages/copy-sources-project.md)<br/>
[빌드 이벤트 속성(Linux C++)](../linux/prop-pages/build-events-linux.md)
