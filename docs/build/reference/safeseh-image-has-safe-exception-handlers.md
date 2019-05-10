---
title: /SAFESEH(이미지에 안전한 예외 처리기 포함)
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 62784933cbecd4f312c52ae98cab7d232b893f35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318643"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH(이미지에 안전한 예외 처리기 포함)

```
/SAFESEH[:NO]
```

때 **/SAFESEH** 지정 않으면 링커에서 이미지의 안전한 예외 처리기 테이블을 만들 수 있을 경우에 이미지를 생성 합니다. 이 테이블은 예외 처리기는 해당 이미지에 올바른 운영 체제를 지정 합니다.

**/SAFESEH** 은 유효한 경우에 x86에 대 한 링크 대상입니다. **/SAFESEH** 예외 처리기에 이미 있는 플랫폼에 대 한 지원 되지 않습니다. 예를 들어, x64 및 ARM에서 모든 예외 처리기 PDATA에 표시 됩니다. ML64.exe는 ml64 함수를 통해 해제할 수 있도록 이미지로 내보내는 SEH 정보 (XDATA 및 PDATA) 주석 추가 지원 합니다. 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md) 자세한 내용은 합니다.

하는 경우 **/SAFESEH** 지정 하지 않으면 모든 모듈 안전한 예외 처리 기능을 사용 하 여 호환 되는 경우 링커는 안전한 예외 처리기 테이블을 사용 하 여 이미지를 생성 합니다. 모든 모듈에 안전한 예외 처리 기능과 호환 없는 경우 결과 이미지에 안전한 예외 처리기 테이블을 포함 되지 않습니다. 하는 경우 [/SUBSYSTEM](subsystem-specify-subsystem.md) WINDOWSCE 또는 EFI_ * 옵션 중 하나를 지정 합니다. 하위 시스템 하나도 가능으로 링커는 안전한 예외 처리기 테이블을 사용 하 여 이미지를 생성 하기 위해 시도 하지 않습니다 정보를 사용 합니다.

하는 경우 **/SAFESEH:NO** 지정, 링커는 모든 모듈은 안전한 예외 처리 기능을 사용 하 여 호환 되는 경우에 안전한 예외 처리기 테이블을 사용 하 여 이미지를 생성 하지 않습니다.

링커 입력된 파일 (모듈)의 하나 이상의 안전한 예외 처리기 기능을 사용 하 여 호환 되지 않으므로 이미지를 생성할 수 있으려면 필요가 링커에 대 한 가장 일반적인 이유. 시각적 개체의 이전 버전의 컴파일러를 사용 하 여 만들어졌기 때문에 안전한 예외 처리기를 사용 하 여 호환 되지 모듈에 대 한 일반적인 이유는 C++입니다.

사용 하 여 구조적된 예외 처리기로 함수를 등록할 수도 있습니다 [합니다. SAFESEH](../../assembler/masm/dot-safeseh.md)합니다.

기존 표시할 수 없는 안전한 예외 처리기 (또는 예외 처리기가 없는) 것으로 이진 빌드 시간에 안전한 예외 처리에 대 한 정보를 추가 해야 합니다.

링커의 안전한 예외 처리기 테이블을 작성할 수는 C 런타임 라이브러리를 사용 하 여 응용 프로그램에 따라 달라 집니다. 사용 하 여 링크 [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) 안전한 예외 처리기 테이블, (예: loadcfg.c CRT 소스 파일에서 찾을 수 있습니다)를 로드 구성 구조를 제공 해야 하 고 시각적 개체에 대해 정의 된 모든 항목을 포함 하는 C++합니다. 예를 들어:

```
#include <windows.h>
extern DWORD_PTR __security_cookie;  /* /GS security cookie */

/*
* The following two names are automatically created by the linker for any
* image that has the safe exception table present.
*/

extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is
                                           the count of table entries */
typedef struct {
    DWORD       Size;
    DWORD       TimeDateStamp;
    WORD        MajorVersion;
    WORD        MinorVersion;
    DWORD       GlobalFlagsClear;
    DWORD       GlobalFlagsSet;
    DWORD       CriticalSectionDefaultTimeout;
    DWORD       DeCommitFreeBlockThreshold;
    DWORD       DeCommitTotalFreeThreshold;
    DWORD       LockPrefixTable;            // VA
    DWORD       MaximumAllocationSize;
    DWORD       VirtualMemoryThreshold;
    DWORD       ProcessHeapFlags;
    DWORD       ProcessAffinityMask;
    WORD        CSDVersion;
    WORD        Reserved1;
    DWORD       EditList;                   // VA
    DWORD_PTR   *SecurityCookie;
    PVOID       *SEHandlerTable;
    DWORD       SEHandlerCount;
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;

const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    &__security_cookie,
    __safe_se_handler_table,
    (DWORD)(DWORD_PTR) &__safe_se_handler_count
};
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **링커** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 에 대 한 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
