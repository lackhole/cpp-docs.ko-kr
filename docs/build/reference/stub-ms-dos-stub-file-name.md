---
title: /STUB(MS-DOS 스텁 파일 이름)
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 7150d4ff8f35b00d96caa21fd5ea3754fec76030
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317876"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB(MS-DOS 스텁 파일 이름)

```
/STUB:filename
```

## <a name="arguments"></a>인수

*filename*<br/>
MS-DOS 응용 프로그램입니다.

## <a name="remarks"></a>설명

/STUB 옵션을 Win32 프로그램 MS-DOS 스텁 프로그램을 연결합니다.

스텁 프로그램 파일 MS-DOS에서 실행 되는 경우 호출 됩니다. 일반적으로 적절 한 메시지를; 표시 그러나 모든 유효한 MS-DOS 응용 프로그램에 스텁 프로그램을 수 있습니다.

지정 된 *filename* 스텁 프로그램 명령줄에 콜론 (:)에 대 한 합니다. 링커 검사 *filename* 및 파일을 실행할 수 없는 경우 오류 메시지를 발생 시킵니다. 프로그램은.exe 파일; 이어야 합니다. .com 파일 스텁 프로그램에 대해 올바르지 않습니다.

이 옵션을 사용 하지 않으면 링커 다음 메시지를 발급 하는 기본 스텁 프로그램을 연결 합니다.

```
This program cannot be run in MS-DOS mode.
```

가상 장치 드라이버를 빌드하면 *filename* (WINNT에 정의 된 IMAGE_DOS_HEADER 구조를 포함 하는 파일 이름을 지정 하면. H) 데 사용할 기본 헤더가 아닌 VXD 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. 에 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
