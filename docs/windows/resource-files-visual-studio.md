---
title: 리소스 파일(C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- resources [C++]
- .rc files [C++]
- resource files [C++]
- resource script files [C++]
- resource script files [C++], Win-32 based applications
- resource script files [C++], files updated when editing resources
- resources [C++], types of resource files
- rct files [C++]
- rc files [C++]
- resource files [C++], types of
- .rct files [C++]
- resource script files [C++], unsupported types
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
ms.openlocfilehash: 45db6d0139cfa3aa8a2eaa8fe6d18158cb6646ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387918"
---
# <a name="resource-files-c"></a>리소스 파일(C++)

> [!NOTE]
> .NET 프로그래밍 언어의 프로젝트는 리소스 스크립트 파일을 사용하지 않으므로 **솔루션 탐색기**에서 리소스를 열어야 합니다. 사용 하 여는 [이미지 편집기](../windows/image-editor-for-icons.md) 하며 [바이너리 편집기](binary-editor.md) 관리 프로젝트에서 리소스 파일로 작업 하 합니다.
>
> 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.

용어 *리소스 파일* 같은 여러 파일 형식 참조할 수 있습니다.

- 프로그램의 리소스 스크립트(.rc) 파일

- 리소스 템플릿(.rct) 파일

- 기존 독립 실행형 파일로 개별 리소스입니다. 이 유형은.rc 파일에서 참조 하는 비트맵, 아이콘 또는 커서 파일을 포함 합니다.

- 개발 환경에서 생성 되는 헤더 파일입니다. 이러한 유형에 `Resource.h`,.rc 파일에서 참조 하 합니다.

.Exe,.dll 및.res 파일과 라고와 같은 다른 파일 형식에서 리소스를 확인할 *리소스*합니다.

작업할 수 있습니다 *리소스 파일* 하 고 *리소스* 에서 프로젝트 내에서. 현재 프로젝트의 일부가 아닌 또는 Visual Studio 개발 환경 외부에서 만든를 사용 하 여 작업할 수 있습니다. 예를 들어 다음 작업을 할 수 있습니다.

- 중첩되어 조건부로 포함된 리소스 파일에 대한 작업

- 기존 리소스를 업데이트 하거나 시각적 개체에 변환 C++입니다.

- 현재 리소스 파일에서 그래픽 리소스 가져오기 또는 내보내기

- 개발 환경에서 수정할 수 없는 공유 또는 읽기 전용 식별자(기호) 포함

- 편집 필요 하지 않습니다 (또는 편집할 수 없습니다), 여러 프로젝트 간에 공유 리소스와 같은 실행 파일 (.exe) 파일에서 리소스를 포함 합니다.

- 개발 환경에서 지원하지 않는 리소스 형식 포함

리소스에 대 한 자세한 내용은 참조 하는 방법 [리소스 만들기](../windows/how-to-create-a-resource-script-file.md), [리소스 관리](../windows/how-to-copy-resources.md), 및 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)합니다.

## <a name="editable-resources"></a>편집 가능한 리소스

포함 하는 리소스를 편집 하려면 다음 형식의 파일을 열 수 있습니다.

| 파일 이름 | 설명 |
|---|---|
| .rc | 리소스 스크립트 파일 |
| .rct | 리소스 템플릿 파일 |
| .res | 리소스 파일 |
| .resx | 관리 되는 리소스 파일 |
| .exe | 실행 파일 |
| .dll | 동적 연결 라이브러리 파일 |
| .bmp, .ico, .dib, .cur | 비트맵, 아이콘, 도구 모음 및 커서 파일 |

리소스를 편집할 때 Visual Studio 환경 사용 하며 다음 파일에 영향을 줍니다.

| 파일 이름 | 설명 |
|---|---|
| Resource.h | 기호 정의 포함 하는 개발 환경에서 생성 된 헤더 파일입니다.<br/><br/>소스 제어에이 파일을 포함 합니다. |
| Filename.aps | 빠른 로드에 사용 되는 현재 리소스 스크립트 파일의 이진 버전입니다.<br /><br /> 리소스 편집기에서.rc 또는 resource.h 파일을 읽을 직접 하지. 리소스 컴파일러 리소스 편집기에서 사용 되는.aps 파일로 컴파일합니다. 이 파일은 컴파일 단계이며 기호화된 데이터만 저장합니다.<br/><br/>일반적인 컴파일 프로세스를 따라 없는 주석 처리 같은 기호화 된 정보에는 컴파일 프로세스 중 삭제 됩니다.<br/><br/>.Aps 파일이.rc 파일과 동기화 되 면 때마다.rc 파일이 다시 생성 됩니다. 예를 들어 경우 있습니다 **저장할**, 리소스 편집기에서는.rc 파일 및 resource.h 파일을 덮어씁니다. 리소스 자체는 변경 내용을 통합.rc 파일에 남지만 주석을 항상 손실 됩니다 후.rc 파일을 덮어씁니다. 주석을 유지 하는 방법에 대 한 자세한 내용은 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)합니다.<br/><br/>일반적으로 소스 제어에는.aps 파일이 포함 하지 않아야 합니다. |
| .rc | 현재 프로젝트의 리소스에 대한 스크립트가 포함된 리소스 스크립트 파일입니다. 저장할 때마다 .aps 파일이 이 파일을 덮어씁니다.<br/><br/>소스 제어에이 파일을 포함 합니다. |

## <a name="manifest-resources"></a>매니페스트 리소스

C++ 데스크톱 프로젝트 매니페스트 리소스는 응용 프로그램에서 사용 하는 종속성을 설명 하는 XML 파일입니다. 예를 들어이 MFC Visual Studio에서 마법사에서 생성 된 매니페스트 파일은 정의 응용 프로그램에서 사용 해야 Windows 공용 컨트롤 Dll 버전:

```xml
<description>Your app description here</description>
<dependency>
    <dependentAssembly>
        <assemblyIdentity
            type="win32"
            name="Microsoft.Windows.Common-Controls"
            version="6.0.0.0"
            processorArchitecture="X86"
            publicKeyToken="6595b64144ccf1df"
            language="*"
        />
    </dependentAssembly>
</dependency>
```

Windows XP 또는 Windows Vista 응용 프로그램의 경우 매니페스트 리소스의 Windows 공용 컨트롤을 사용 하 여 응용 프로그램에 대 한 최신 버전을 지정 해야 합니다. 위의 예제에서는 버전 `6.0.0.0`를 지 원하는 합니다 [Syslink 컨트롤](/windows/desktop/Controls/syslink-overview)합니다.

> [!NOTE]
> 모듈별로 매니페스트 리소스를 하나만 사용할 수 있습니다.

버전을 보려면 매니페스트 리소스에 포함 된 정보를 입력을 XML 뷰어 또는 Visual Studio 텍스트 편집기에서 파일을 엽니다. [리소스 뷰](../windows/resource-view-window.md)에서 매니페스트 리소스를 열면 리소스가 이진 형식으로 열립니다.

### <a name="to-open-a-manifest-resource"></a>매니페스트 리소스를 열려면

1. Visual Studio에서 프로젝트를 열고 이동할 **솔루션 탐색기**합니다.

1. 확장 된 **리소스 파일** 다음 폴더:

   - 텍스트 편집기를 열려면 두 번 클릭 합니다 *.manifest* 파일입니다.

   - 다른 편집기를 열려면 마우스 오른쪽 단추로 클릭 합니다 *.manifest* 파일을 선택 **사용 하 여 열고**합니다. 편집기를 사용 하 여 선택한 지정할 **열려**합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[리소스 파일 작업](../windows/working-with-resource-files.md)<br/>
[리소스 식별자(기호)](../windows/symbols-resource-identifiers.md)<br/>
[리소스 편집기](../windows/resource-editors.md)<br/>