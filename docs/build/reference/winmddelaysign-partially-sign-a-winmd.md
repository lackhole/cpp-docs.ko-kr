---
title: /WINMDDELAYSIGN(winmd에 부분적으로 서명)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 5e6eab3fbc40543b634f03da826d3bd3477b9623
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316602"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN(winmd에 부분적으로 서명)

파일에 공개 키를 입력하여 Windows 런타임 메타데이터(.winmd) 파일의 일부 서명을 활성화합니다.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>설명

와 유사 합니다 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) .winmd 파일에 적용 되는 링커 옵션입니다. 사용 하 여 **지정 하려면 /WINMDDELAYSIGN** .winmd 파일에 공개 키만 배치 하려는 경우. 기본적으로 링커는 역할 처럼 **/winmddelaysign: no** 에 지정 했습니다; 즉, winmd 파일을 서명 하지 않습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **링커** 폴더입니다.

1. 선택 된 **Windows 메타 데이터** 속성 페이지.

1. 에 **Windows 메타 데이터 지연 서명** 드롭다운 목록 상자에서 원하는 옵션을 선택 합니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
