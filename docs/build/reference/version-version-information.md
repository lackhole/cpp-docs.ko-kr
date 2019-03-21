---
title: /VERSION(버전 정보)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 626461fc7a9fc6dd7b6578e836733d154a66862a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807600"
---
# <a name="version-version-information"></a>/VERSION(버전 정보)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>인수

*주요* 고 *부*<br/>
.Exe 또는.dll 파일의 헤더에 버전 번호입니다.

## <a name="remarks"></a>설명

/VERSION 옵션을.exe 또는.dll 파일의 헤더에 버전 번호를 삽입 하도록 링커에 지시 합니다. DUMPBIN을 사용 하 여 [/HEADERS](headers.md) /VERSION의 결과 보려는 OPTIONAL HEADER VALUES의 이미지 버전 필드를 표시 합니다.

합니다 *주요* 하 고 *부* 인수는 0 ~ 65535 범위의 10 진수입니다. 기본값은 0.0 버전입니다.

/VERSION으로 지정된 정보는 파일 탐색기에서 해당 속성을 볼 때 응용 프로그램에 대해 표시되는 버전 정보에 영향을 주지 않습니다. 응용 프로그램을 빌드하는 데 사용 하는 리소스 파일에서 해당 버전 정보가 제공 됩니다. 참조 [버전 정보 편집기](../../windows/version-information-editor.md) 자세한 내용은 합니다.

버전 번호를 삽입 하는 또 다른 방법은 된 합니다 [버전](version-c-cpp.md) 모듈 정의 문의 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **일반** 속성 페이지.

1. 수정 된 **버전** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
