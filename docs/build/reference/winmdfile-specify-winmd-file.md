---
title: /WINMDFILE(winmd 파일 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: 5d24d1d1aad8442f549dcb1aa4bd6414070c282c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316485"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE(winmd 파일 지정)

생성 되는 Windows 런타임 메타 데이터 (.winmd) 출력 파일의 파일 이름을 지정 합니다 [/WINMD](winmd-generate-windows-metadata.md) 링커 옵션입니다.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>설명

`filename`에 지정된 값을 사용해서 기본 .winmd 파일 이름(`binaryname`.winmd)을 재정의합니다. ".Winmd"를 추가 하지 마십시오 확인 `filename`합니다.  여러 값에 나열 되 면 합니다 **/WINMDFILE** 명령줄 마지막이 우선 적용 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **링커** 폴더입니다.

1. 선택 된 **Windows 메타 데이터** 속성 페이지.

1. 에 **Windows 메타 데이터 파일** 상자 파일 위치를 입력 합니다.

## <a name="see-also"></a>참고자료

[/WINMD(Windows 메타데이터 생성)](winmd-generate-windows-metadata.md)<br/>
[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
