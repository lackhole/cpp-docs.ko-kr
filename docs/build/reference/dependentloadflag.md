---
title: /DEPENDENTLOADFLAG(기본 종속 로드 플래그 설정)
description: /DEPENDENTLOADFLAG 옵션은 LoadLibrary를 사용 하 여 로드 된 Dll에 대 한 기본 플래그를 설정 합니다.
ms.date: 12/22/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 3a403f22c88ccd3e25ba95c183656ad2ffafd05a
ms.sourcegitcommit: ef34a11cb04511221bf5c7b9f4f55ad91a7a603f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2019
ms.locfileid: "75330000"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG(기본 종속 로드 플래그 설정)

Dll을 로드 하는 데 `LoadLibrary`를 사용할 때 사용 되는 기본 로드 플래그를 설정 합니다.

## <a name="syntax"></a>구문

> **/DEPENDENTLOADFLAG**[ __:__ *load_flags*]

### <a name="arguments"></a>인수

*load_flags*<br/>
모든 [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) 호출에 적용할 종속 로드 플래그를 지정하는 10 진수, `0x` 앞에 오는 0을 포함 하는 8 진수 또는 선행 16 진수의 선택적 "C" 스타일 16 비트 정수 값입니다. 기본값은 0입니다.

## <a name="remarks"></a>주의

이 옵션은 Visual Studio 2017에 새로 있습니다. Windows 10 RS1 이상 버전에서 실행 되는 앱에만 적용 됩니다. 이 옵션은 앱을 실행 하는 다른 운영 체제에서 무시 됩니다.

지원 되는 운영 체제에서이 옵션은 `LoadLibrary("dependent.dll")`에 대 한 호출을 `LoadLibraryEx("dependent.dll", 0, load_flags)`에 해당 하는 것으로 변경 하는 효과를 가집니다. [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) 에 대 한 호출은 영향을 받지 않습니다. 이 옵션은 앱에서 로드 한 Dll에 재귀적으로 적용 되지 않습니다.

이 플래그를 사용 하 여 [DLL 심기 공격](/windows/win32/dlls/dynamic-link-library-security) 을 더 어렵게 만들 수 있습니다. 예를 들어 앱이 `LoadLibrary` 사용 하 여 종속 DLL을 로드 하는 경우 공격자는 현재 디렉터리와 같이 `LoadLibrary`에서 사용 하는 검색 경로에서 같은 이름의 DLL을 지정할 수 있습니다 .이는 안전한 DLL 검색 모드가 비활성화 된 경우 시스템 디렉터리 전에 확인 될 수 있습니다. Safe DLL 검색 모드는 나중에 사용자의 현재 디렉터리를 검색 순서 대로 배치 하 고 Windows XP SP2 이상 버전에서 기본적으로 사용 하도록 설정 됩니다. 자세한 내용은 [동적 연결 라이브러리 검색 순서](/windows/win32/Dlls/dynamic-link-library-search-order)를 참조 하세요.

링크 옵션 `/DEPENDENTLOADFLAG:0xA00` 지정 하는 경우 (결합 된 플래그의 값 `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`) 사용자 컴퓨터에서 safe DLL 검색 모드를 사용 하지 않도록 설정한 경우에도 DLL 검색 경로는 응용 프로그램 디렉터리로 제한 되 고 그 다음 에%windows%\system32 디렉터리가 사용 됩니다. `/DEPENDENTLOADFLAG:0x800` 옵션 은%windows%\system32 디렉터리에 대 한 검색을 제한 하 여 훨씬 더 제한적입니다. 보호 된 디렉터리는 더 어려워집니다. 하지만 공격자가 변경 하는 경우에는 불가능 합니다. 사용 가능한 플래그와 기호화 된 값 및 숫자 값에 대 한 자세한 내용은 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)의 *dwFlags* 매개 변수 설명을 참조 하십시오. 다양 한 종속 로드 플래그를 사용할 때 사용 되는 검색 순서에 대 한 자세한 내용은 [LOAD_LIBRARY_SEARCH 플래그를 사용 하 여 검색 순서](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags)를 참조 하세요.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 DEPENDENTLOADFLAG 링커 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **링커** > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션**에 옵션을 입력 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하세요.

## <a name="see-also"></a>참조

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
- [DLL에 실행 파일 링크](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [DLL에 실행 파일 링크](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [동적 연결 라이브러리 검색 순서](/windows/win32/Dlls/dynamic-link-library-search-order)
