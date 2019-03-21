---
title: /GT(파이버 안전 스레드 로컬 저장소 지원)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 417ac00a446f773a424553e42478a4f0cf58efc6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822518"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT(파이버 안전 스레드 로컬 저장소 지원)

정적 스레드 로컬 저장소를 사용 하 여 할당 하는 데이터 즉,를 사용 하 여 할당 한 데이터의 파이버 안전을 지원 `__declspec(thread)`합니다.

## <a name="syntax"></a>구문

```
/GT
```

## <a name="remarks"></a>설명

데이터 선언 `__declspec(thread)` 스레드 로컬 저장소 (TLS) 배열을 통해 참조 됩니다. TLS 배열이 각 스레드에 대 한 시스템 유지 관리 하는 주소 배열입니다. 이 배열의 각 주소는 스레드 로컬 저장소 데이터의 위치를 제공합니다.

파이버는 스택 및 레지스터 컨텍스트로 구성 되며 다양 한 스레드에서 예약할 수 있는 간단한 개체입니다. 파이버는 스레드에서 실행할 수 있습니다. 파이버는 나중에 다른 스레드를 다시 시작 하므로, TLS 배열의 주소 해야 하지 캐시 하거나 최적화할 공용 부분식으로 함수 호출 (참조를 [/Og (전역 최적화)](og-global-optimizations.md) 옵션 세부 정보)입니다. **/GT** 같은 최적화를 방지 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **최적화** 속성 페이지.

1. 수정 된 **파이버 안전 최적화 사용** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
