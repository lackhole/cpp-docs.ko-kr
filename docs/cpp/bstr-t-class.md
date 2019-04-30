---
title: _bstr_t 클래스
ms.date: 11/04/2016
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
ms.openlocfilehash: f394a48c0326058be705d14fb0413e23e8052ae2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386163"
---
# <a name="bstrt-class"></a>_bstr_t 클래스

**Microsoft 전용**

A `_bstr_t` 개체를 캡슐화 합니다 [BSTR 데이터 형식](/previous-versions/windows/desktop/automat/bstr)합니다. 클래스가 관리 리소스 할당 및 할당 해제 함수 호출을 통해 `SysAllocString` 하 고 `SysFreeString` 및 기타 `BSTR` 적절 한 경우 Api. 합니다 **_bstr_t** 클래스는 과도 한 오버 헤드를 방지 하기 위해 참조 가산을 사용 합니다.

### <a name="construction"></a>생성

|||
|-|-|
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` 개체를 생성합니다.|

### <a name="operations"></a>작업

|||
|-|-|
|[Assign](../cpp/bstr-t-assign.md)|`BSTR`을 `BSTR`로 래핑된 `_bstr_t`로 복사합니다.|
|[Attach](../cpp/bstr-t-attach.md)|`_bstr_t` 래퍼를 `BSTR`에 연결합니다.|
|[copy](../cpp/bstr-t-copy.md)|캡슐화된 `BSTR`의 복사본을 구성합니다.|
|[Detach](../cpp/bstr-t-detach.md)|`BSTR`로 래핑된 `_bstr_t`을 반환하고 `BSTR`을 `_bstr_t`에서 분리합니다.|
|[GetAddress](../cpp/bstr-t-getaddress.md)|`BSTR`로 래핑된 `_bstr_t`을 가리킵니다.|
|[GetBSTR](../cpp/bstr-t-getbstr.md)|`BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분을 가리킵니다.|
|[length](../cpp/bstr-t-length.md)|`_bstr_t`에 있는 문자의 수를 반환합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](../cpp/bstr-t-operator-equal.md)|기존 `_bstr_t` 개체에 새 값을 할당합니다.|
|[operator +=](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` 개체의 끝 부분에 문자를 추가합니다.|
|[연산자 +](../cpp/bstr-t-operator-add-equal-plus.md)|두 문자열을 연결합니다.|
|[연산자 !](../cpp/bstr-t-operator-logical-not.md)|확인 캡슐화 된 `BSTR` NULL 문자열입니다.|
|[operator ==, !=, \<, >, \<=, >=](../cpp/bstr-t-relational-operators.md)|두 `_bstr_t` 개체를 비교합니다.|
|[연산자 wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|캡슐화된 유니코드 또는 멀티바이트 `BSTR` 개체에 대한 포인터를 추출합니다.|

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comutil.h >

**Lib:** comsuppw.lib 또는 comsuppwd.lib(자세한 내용은 [/zc: wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조)

## <a name="see-also"></a>참고자료

[컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)