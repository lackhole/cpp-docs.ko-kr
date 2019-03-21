---
title: / DEPENDENTLOADFLAG (집합 기본 종속 로드가 플래그)
description: /DEPENDENTLOADFLAG 옵션 LoadLibrary를 사용 하 여 로드 된 Dll에 대 한 기본 플래그를 설정 합니다.
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 94998e06f23a7e70524221d3cb75166b5d3f2c44
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815972"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (집합 기본 종속 로드가 플래그)

기본 부하 플래그 집합을 사용할 때 `LoadLibrary` Dll을 로드 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

> **/DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>인수

*loadflags*<br/>
선택적 "C" 스타일 16 비트 정수 값 10 진수, 앞에 0을 사용 하 여 8 진수 또는 16 진수 숫자로 `0x`에 모두 적용 하는 종속 로드가 플래그를 지정 하는 [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) 호출 합니다. 기본값은 0입니다.

## <a name="remarks"></a>설명

이 옵션은 Visual Studio 2017의 새로운 기능 및 Windows 10 RS1 이상에서 실행 되는 앱에만 적용 됩니다. 이 옵션은 앱을 실행 하는 다른 운영 체제에서 무시 됩니다.

지원 되는 운영 체제에서이 옵션은 변경에 대 한 호출의 효과가 `LoadLibrary("dependent.dll")` 의 해당 `LoadLibraryEx("dependent.dll", 0, loadflags)`합니다. 에 대 한 호출 [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) 영향을 받지 않습니다. 이 옵션에는 앱에서 로드 한 Dll을 재귀적으로 적용 되지 않습니다.

이 플래그는 DLL 효과 공격을 방지 하기 위해 사용할 수 있습니다. 예를 들어, 앱을 사용 하는 경우 `LoadLibrary` 종속 DLL을 로드 하려면 공격자 수 공장 동일한 이름의 DLL에서 사용 하는 검색 경로에 `LoadLibrary`, 현재 디렉터리와 같은 확인 될 수 시스템 디렉터리 하기 전에 안전 DLL 검색 모드는 경우 사용할 수 없습니다. 안전 DLL 검색 모드 검색 순서로 나중에 사용자의 현재 디렉터리에 배치 하 고 Windows XP SP2 이상 버전에서 기본적으로 활성화 됩니다. 자세한 내용은 [동적 연결 라이브러리 순서](/windows/desktop/Dlls/dynamic-link-library-search-order)합니다.

링크 옵션을 지정 하면 `/DEPENDENTLOADFLAG:0xA00` (결합 된 플래그의 값 `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), DLL 검색 경로 제한 하는 공격자가 더 어려운 보호 된 디렉터리에는 사용자의 컴퓨터에 안전 하 게 DLL 검색 모드가 해제 되는 경우에 변경 내용입니다. 사용 가능한 플래그에 대 한 정보 및 해당 기호 및 숫자 값에 대 한 참조를 *dwFlags* 에 매개 변수 설명을 [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)합니다.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 DEPENDENTLOADFLAG 링커 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 옵션을 입력 **추가 옵션**합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
- [DLL에 실행 파일 링크](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [DLL에 실행 파일 링크](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)
- [동적 연결 라이브러리 순서](/windows/desktop/Dlls/dynamic-link-library-search-order)
