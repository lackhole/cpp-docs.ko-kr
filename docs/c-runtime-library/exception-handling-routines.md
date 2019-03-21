---
title: 예외 처리 루틴
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: 8def356793906074e6fc4b8d7a139ce1915a5f9b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749141"
---
# <a name="exception-handling-routines"></a>예외 처리 루틴

C++ 예외 처리 함수를 사용하여 프로그램 실행 중에 예기치 않은 이벤트에서 복구할 수 있습니다.

## <a name="exception-handling-functions"></a>예외 처리 함수

|함수|기능|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 예외(C 구조적 예외)를 C++ 형식 예외로 처리|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|**terminate**에서 호출하는 사용자 고유 종료 루틴을 설치합니다.|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|**unexpected**에서 호출하는 사용자 고유 종료 함수를 설치합니다.|
|[terminate](../c-runtime-library/reference/terminate-crt.md)|예외가 throw된 후에 특정 상황에서 자동으로 호출됩니다. **terminate** 함수는 **set_terminate**를 사용하여 **abort** 또는 지정한 함수를 호출합니다.|
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|**set_unexpected**를 사용하여 **terminate** 또는 지정한 함수를 호출합니다. **unexpected** 함수는 현재 Microsoft C++ 예외 처리 구현에서 사용되지 않습니다.|

## <a name="see-also"></a>참고 항목

[범주별 유버니설 C 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)<br/>
