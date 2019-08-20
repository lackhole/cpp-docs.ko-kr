---
title: 견고성
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: f41fc019c6a1779362644e29c5518d40690fe9db
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500679"
---
# <a name="robustness"></a>견고성

다음 C 런타임 라이브러리 함수를 사용하여 프로그램의 견고성을 높입니다.

## <a name="run-time-robustness-functions"></a>런타임 견고성 함수

|함수|기능|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|**new** 연산자에서 메모리 할당에 실패하는 경우 오류 처리 메커니즘에 제어를 전달합니다.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 예외(C 구조적 예외)를 C++ 형식 예외로 처리합니다.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|[terminate](../c-runtime-library/reference/terminate-crt.md)로 호출하는 자체 종료 함수를 설치합니다.|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|[unexpected](../c-runtime-library/reference/unexpected-crt.md)로 호출하는 자체 종료 함수를 설치합니다.|

## <a name="see-also"></a>참고 항목

[범주별 유버니설 C 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)<br/>
