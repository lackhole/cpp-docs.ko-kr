---
title: 매개 변수 유효성 검사
ms.date: 11/04/2016
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
ms.openlocfilehash: 2c7b2ae50fdcbf59cd23cc309a4ddc4c0803e24e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748426"
---
# <a name="parameter-validation"></a>매개 변수 유효성 검사

대부분의 보안이 강화된 CRT 함수 및 여러 기존 함수는 해당 매개 변수의 유효성을 검사합니다. 여기에는 **NULL**에 대한 포인터 검사, 정수가 올바른 범위에 포함되어 있는지 검사 또는 열거형 값이 올바른지 검사가 포함될 수 있습니다. 잘못된 매개 변수가 검색되면 잘못된 매개 변수 처리기가 실행됩니다.

## <a name="invalid-parameter-handler-routine"></a>잘못된 매개 변수 처리기 루틴

C 런타임 라이브러리 함수는 잘못된 매개 변수를 검색하면 오류에 대한 일부 정보를 캡처한 다음 잘못된 매개 변수 처리기 디스패치 함수([_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md) 또는 [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md) 중 하나)를 래핑하는 매크로를 호출합니다. 호출되는 디스패치 함수는 코드가 디버그 빌드인지, 일반 정품 빌드인지 아니면 오류가 복구할 수 있는 것으로 간주되지 않는지에 따라 달라집니다.

디버그 빌드에서 잘못된 매개 변수 매크로가 있으면 대개 디스패치 함수가 호출되기 전에 어설션이 실패하며 디버거 중단점이 생성됩니다. 코드를 실행하면 운영 체제 및 런타임 라이브러리 버전에 따라 "중단", "다시 시도", "계속" 또는 유사한 선택 항목이 있는 대화 상자에서 사용자에게 어설션이 보고될 수 있습니다. 사용자는 이러한 옵션을 통해 프로그램을 즉시 종료하거나, 디버거를 연결하거나, 기존 코드가 계속 실행되도록 할 수 있습니다. 이 경우 디스패치 함수가 호출됩니다.

그러면 잘못된 매개 변수 처리기 디스패치 함수는 현재 할당되어 있는 잘못된 매개 변수 처리기를 호출합니다. 기본적으로 잘못된 매개 변수는 `_invoke_watson`을 호출합니다. 그러면 애플리케이션의 "작동이 중단"됩니다(애플리케이션이 종료되며 미니 덤프 생성). 운영 체제에서 사용하도록 설정된 경우 분석을 위해 Microsoft에 크래시 덤프를 로드할지를 묻는 대화 상자가 표시됩니다.

[_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) 또는 [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) 함수를 사용해 잘못된 매개 변수 처리기를 원하는 함수로 설정하면 이 동작을 변경할 수 있습니다. 직접 지정하는 함수가 애플리케이션을 종료하지 않는 경우에는 잘못된 매개 변수를 수신한 함수에 컨트롤이 반환됩니다. CRT에서 이러한 함수는 일반적으로 함수 실행을 중단하고 `errno`를 오류 코드로 설정한 다음 오류 코드를 반환합니다. 대부분의 경우 `errno` 값 및 반환 값은 모두 잘못된 매개 변수를 나타내는 `EINVAL`입니다. 경우에 따라 매개 변수로 전달된, 잘못된 파일 포인터에 대한 `EBADF`와 같은 보다 구체적인 오류 코드가 반환됩니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)<br/>
[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
