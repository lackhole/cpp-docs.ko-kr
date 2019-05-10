---
title: /DEFAULTLIB(기본 라이브러리 지정)
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 0b7d4569c7be70bd97094ebbe09a7ae462331983
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293864"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB(기본 라이브러리 지정)

외부 참조를 확인 하기 위해 검색할 기본 라이브러리를 지정 합니다.

## <a name="syntax"></a>구문

> **/DEFAULTLIB**:_library_

### <a name="arguments"></a>인수

*library*<br/>
외부 참조를 확인할 때 검색할 라이브러리의 이름입니다.

## <a name="remarks"></a>설명

합니다 **/DEFAULTLIB** 옵션에는 추가 *라이브러리* 링크 참조를 확인할 때 검색 하는 라이브러리 목록에 있습니다. 지정 된 라이브러리 **/DEFAULTLIB** .obj 파일에 지정 된 기본 라이브러리 전과 명령줄에서 명시적으로 지정 하는 라이브러리 후 검색 됩니다.

인수 없이 사용 하는 경우는 [/NODEFAULTLIB (모든 기본 라이브러리 무시)](nodefaultlib-ignore-libraries.md) 옵션을 모두 무시 **/DEFAULTLIB**:*라이브러리* 옵션입니다. 합니다 **/NODEFAULTLIB**:*라이브러리* 재정의 옵션 **/DEFAULTLIB**:*라이브러리* 때 동일한 *라이브러리*둘 다에 이름을 지정 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. **추가 옵션**를 입력 한 **/DEFAULTLIB**:*라이브러리* 검색할 각 라이브러리에 대 한 옵션입니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
