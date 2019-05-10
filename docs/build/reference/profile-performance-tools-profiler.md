---
title: /PROFILE(성능 도구 프로파일러)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 23cbccba9a8ec839252d553cc5cbafd37e66bbf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320203"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE(성능 도구 프로파일러)

성능 도구 프로파일러와 함께 사용할 수 있는 출력 파일을 생성합니다.

## <a name="syntax"></a>구문

```
/PROFILE
```

## <a name="remarks"></a>설명

/ 프로필 의미 링커 옵션은 다음과 같습니다.

- [/OPT:REF](opt-optimizations.md)

- /OPT: NOICF

- [/INCREMENTAL:NO](incremental-link-incrementally.md)

- [/FIXED:NO](fixed-fixed-base-address.md)

/ 프로필 사용 하면 링커가 프로그램 이미지에서 재배치 섹션 생성 합니다.  재배치 섹션 프로파일러를 프로필 데이터를 가져올 프로그램 이미지를 변환할 수 있습니다.

**/ 프로필** 만 (팀 개발) 엔터프라이즈 버전 에서만에서 제공 됩니다.  PREfast에 대 한 자세한 내용은 참조 하세요. [C 용 코드 분석 /C++ 개요](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** 노드를 확장합니다.

1. 확장 된 **링커** 노드.

1. 선택 된 **고급** 속성 페이지.

1. 수정 된 **프로필** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>을 참조하세요.

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Visual Studio의 CMake 프로젝트 내에서이 링커 옵션을 설정 하려면

**CMake** 프로젝트에 없는 한 **속성 페이지**, 링커 옵션을 수정 하 여 CMakeLists.txt 설정할 수 있습니다.

1. 프로젝트 루트 디렉터리에서 CMakeLists.txt를 엽니다.

1. 아래 코드를 추가 합니다. 세부 정보를 참조 하세요. [CMake 참조](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. 솔루션을 다시 빌드합니다.

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)

