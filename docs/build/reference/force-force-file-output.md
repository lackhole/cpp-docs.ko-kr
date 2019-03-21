---
title: /FORCE(파일 출력 강제)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: af7962a4b3b5805e7e0c4d59752254c8ade17f7b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814308"
---
# <a name="force-force-file-output"></a>/FORCE(파일 출력 강제)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>설명

/FORCE 옵션을 올바른.exe 파일을 만들도록 링커에 지시 또는 DLL 기호가 아닌 참조 하는 경우에 정의 또는 여러 번 정의 되어 있습니다.

/FORCE 옵션은 선택적 인수를 사용할 수 있습니다.

- /FORCE:MULTIPLE를 사용 하 여 링크 기호에 대 한 정의 둘 이상 발견 여부 또는 출력 파일을 만듭니다.

- /FORCE를 사용 하 여: UNRESOLVED를 링크 정의 되지 않은 기호를 찾습니다 여부 출력 파일을 만듭니다. / 강제: 확인 되지 않은 진입점 기호 해결 되지 않으면 무시 됩니다.

/ FORCE 인수 없이 모두 여러 의미 및 확인 되지 않은 합니다.

이 옵션을 사용 하 여 만든 파일에는 예상 대로 실행 되지 않습니다. /FORCE 옵션을 지정 하는 경우 링커는 증분 방식으로 연결 되지 않습니다.

모듈을 사용 하 여 컴파일된 경우 **/clr**하십시오 **/force** 이미지를 만들지 것입니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. 에 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
