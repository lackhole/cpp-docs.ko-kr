---
title: C 런타임 오류 R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: cbade3ce8686c8c293b8d40a73c546805e42215d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034023"
---
# <a name="c-runtime-error-r6035"></a>C 런타임 오류 R6035

Microsoft Visual c + + 런타임 라이브러리 오류 R6035-이 응용 프로그램의 모듈은 해당 보안 쿠키에 의존 하는 함수 활성 상태인 동안 모듈의 전역 보안 쿠키를 초기화 합니다.  이전 __security_init_cookie를 호출 합니다.

[__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) 전역 보안 쿠키를 처음 사용 하기 전에 호출 해야 합니다.

전역 보안 쿠키로 컴파일된 코드에서 버퍼 오버런을 방지 되 [/GS (버퍼 보안 검사)](../../build/reference/gs-buffer-security-check.md) 고 구조적된 예외 처리 코드에서 사용 합니다. 기본적으로, 오버런 방지 함수에 사용 되는 항목에 쿠키가 스택에 배치 되 고 종료 시 스택의 값 전역 쿠키에 대해 비교 됩니다. 값이 서로 다르면 버퍼 오버런이 발생 하 고 프로그램의 즉시 종료를 나타냅니다.

오류 R6035 나타내는 호출 `__security_init_cookie` 보호 된 함수를 입력 한 후 변경 되었습니다. 계속 하려면 실행 인 경우에 쿠키가 스택에 이상 일치 하지 않으므로 전역 쿠키 가상 버퍼 오버런이 감지 됩니다.

다음 DLL 예를 살펴보세요. DLL 진입점은 링커를 통해 DllEntryPoint로 [/ENTRY (진입점 기호)](../../build/reference/entry-entry-point-symbol.md) 옵션입니다. DLL 자체를 호출 해야 하므로 전역 보안 쿠키는 일반적으로 초기화 하는 CRT의 초기화를 바이패스이 `__security_init_cookie`합니다.

```
// Wrong way to call __security_init_cookie
DllEntryPoint(...) {
   DllInitialize();
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}

void DllInitialize() {
   __security_init_cookie();
}
```

이 예제에서는 DllEntryPoint 구조적된 예외 처리를 사용 하 고 따라서 보안 쿠키를 사용 하 여 버퍼 오버런을 탐지 하기 때문에 오류 R6035 생성 됩니다. 전역 보안 쿠키는 시간별 DllInitialize 라고 스택에 배치 된 이미에.

이 예제는 올바른 방법은 보여 줍니다.

```
// Correct way to call __security_init_cookie
DllEntryPoint(...) {
   __security_init_cookie();
   DllEntryHelper();
}

void DllEntryHelper() {
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}
```

이 경우 DllEntryPoint 버퍼 오버런 으로부터 보호 되지 않습니다 (로컬 문자열 버퍼가 고 구조적된 예외 처리를 사용 하지 않습니다). 안전 하 게 호출할 수 있으므로 `__security_init_cookie`합니다. 다음 보호 되는 도우미 함수를 호출 합니다.

> [!NOTE]
>  오류 메시지가 R6035만 x86에서 생성 된 디버그 CRT 하 고 구조적된 예외 처리 하지만 조건에 대해서만 모든 형식의 예외에 대 한 모든 플랫폼에는 오류 처리, c + + EH 같은 키를 누릅니다.

## <a name="see-also"></a>참고자료

[MSVC의 보안 기능](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)