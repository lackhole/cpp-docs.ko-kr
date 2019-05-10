---
title: MSVC 컴파일러 옵션
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: ab41a5de027f28b361937e58fb179fd72db54e4e
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221745"
---
# <a name="compiler-options"></a>컴파일러 옵션

cl.exe는 Microsoft를 제어 하는 도구 C++ (MSVC) C 및 C++ 컴파일러 및 링커입니다. cl.exe는 Microsoft Visual Studio에 대 한 Windows를 지 원하는 운영 체제 에서만 실행할 수 있습니다.

> [!NOTE]
> Visual Studio 개발자 명령 프롬프트 에서만에서이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다. 자세한 내용은 [명령줄에서 MSVC 도구 집합을 사용 하 여](../building-on-the-command-line.md)입니다.

컴파일러는 COFF 공용 개체 파일 형식 () 개체 (.obj) 파일을 생성합니다. 링커는 실행 파일 (.exe) 또는 동적 연결 라이브러리 (Dll)를 생성 합니다.

모든 컴파일러 옵션은 대/소문자 구분를 참고 합니다. 두 슬래시를 사용할 수 있습니다 (`/`) 또는 대시 (`-`) 컴파일러 옵션을 지정 합니다.

연결 하지 않고 컴파일하면를 사용 합니다 [/c](c-compile-without-linking.md) 옵션입니다.

## <a name="find-a-compiler-option"></a>컴파일러 옵션 찾기

특정 컴파일러 옵션을 보려면, 다음 목록 중 하나를 참조 하세요.

- [컴파일러 옵션 사전순 목록](compiler-options-listed-alphabetically.md)

- [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>컴파일러 옵션을 지정 합니다.

각 컴파일러 옵션에 대 한 설명 하는 방법을 개발 환경에서 설정할 수 있습니다. 개발 환경 밖에 서 옵션을 지정 하는 내용은 다음을 참조 하세요.

- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)

- [CL 명령 파일](cl-command-files.md)

- [CL 환경 변수](cl-environment-variables.md)

## <a name="related-build-tools"></a>관련된 빌드 도구

[MSVC 링커 옵션](linker-options.md) 또한 프로그램을 빌드하는 방법에 영향을 줍니다.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](c-cpp-building-reference.md)<br/>
[CL에서의 링커 호출](cl-invokes-the-linker.md)
