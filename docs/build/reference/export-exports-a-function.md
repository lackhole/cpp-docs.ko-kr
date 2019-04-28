---
title: /EXPORT(함수 내보내기)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
ms.openlocfilehash: 7c4f4621bbccd4285bcf4eca07d2544d53d14f6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271361"
---
# <a name="export-exports-a-function"></a>/EXPORT(함수 내보내기)

프로그램에서 함수 이름 또는 서 수 데이터를 내보냅니다.

## <a name="syntax"></a>구문

> **/EXPORT:**<em>entryname</em>[**,\@**<em>ordinal</em>[**,NONAME**]][**,DATA**]

## <a name="remarks"></a>설명

합니다 **/내보내기** 옵션에는 다른 프로그램 함수를 호출 하거나 데이터를 사용할 수 있도록 프로그램에서 내보낼 함수 또는 데이터 항목을 지정 합니다. 내보내기는 일반적으로 DLL에 정의 됩니다.

합니다 *entryname* 호출 프로그램에서 사용 하는 것은 함수 또는 데이터 항목의 이름입니다. *서 수* 지정 하지 않으면 경우는 범위는 1부터 65535의 내보내기 테이블에 인덱스를 지정 합니다 *서*, 링크 값을 할당 합니다. 합니다 **NONAME** 키워드는 서 수로만 없이 함수를 내보냅니다는 *entryname*합니다.

합니다 **데이터** 키워드 내보낸된 항목이 데이터 항목 임을 지정 합니다. 사용 하 여 클라이언트 프로그램에서 데이터 항목을 선언 해야 합니다 **extern __declspec (dllimport)** 합니다.

사용 하 여 권장 되는 순서 대로 나열 된 정의 내보내는 데는 다음과 같은 네 가지가 있습니다.

1. [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드

1. [내보내기를](exports.md) .def 파일에서 문

1. LINK 명령에는 /EXPORT 사양

1. A [주석](../../preprocessor/comment-c-cpp.md) 폼의 소스 코드에 지시문 `#pragma comment(linker, "/export: definition ")`합니다.

동일한 프로그램에서 이러한 모든 메서드를 사용할 수 있습니다. 링크 내보내기를 포함 하는 프로그램을 빌드할 때 문제가 빌드에서.exp 파일을 사용 하지 않으면 가져오기 라이브러리도를 만듭니다.

LINK 사용 하 여 데코 레이트 형식의 식별자입니다. .Obj 파일을 만들 때 컴파일러에서 식별자를 데코레이팅합니다. 하는 경우 *entryname* 해당 데코 레이트 되지 않은 링커 지정 됩니다 (소스 코드에 표시) 된 대로 양식의 링크 이름 일치 시 키 려 합니다. 고유한 일치를 찾을 수 없으면 링크는 오류 메시지를 발급 합니다. 사용 하 여는 [DUMPBIN](dumpbin-reference.md) 가져올 도구는 [데코 레이트 된 이름](decorated-names.md) 을 링커에 지정 해야 할 때 식별자의 형식입니다.

> [!NOTE]
> 데코 레이트 된 형식의 선언 된 C 식별자를 지정 하지 마세요 `__cdecl` 또는 `__stdcall`합니다.

데코 레이트 되지 않은 함수 이름을 내보내고에 빌드 구성에 따라 다른 내보내기 (예를 들어 32 비트 또는 64 비트 빌드) 해야 할 경우에 각 구성에 대 한 다른 DEF 파일을 사용할 수 있습니다. (조건부 전처리기 지시문 DEF 파일에는 허용 되지 않습니다.) 사용할 수 있습니다는 `#pragma comment` 는 여기에 표시 된 함수 선언 전에 지시문 `PlainFuncName` 데코 레이트 되지 않은 이름 및 `_PlainFuncName@4` 함수의 트 데코 레이 된 이름:

```cpp
#pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
BOOL CALLBACK PlainFuncName( Things * lpParams)
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 대 한 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
