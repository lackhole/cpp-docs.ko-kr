---
title: /WINMDKEYCONTAINER(키 컨테이너 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 0b6cb42fc391d94634ae90e5a4cc17e69a14ff09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316517"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER(키 컨테이너 지정)

Windows 메타데이터(.winmd) 파일을 서명하기 위한 키 컨테이너를 지정합니다.

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>설명

와 유사 합니다 [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md) (.winmd) 파일에 적용 되는 링커 옵션입니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **링커** 폴더입니다.

1. 선택 된 **Windows 메타 데이터** 속성 페이지.

1. 에 **Windows 메타 데이터 키 컨테이너** 상자 위치를 입력 합니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
