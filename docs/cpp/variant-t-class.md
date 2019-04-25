---
title: _variant_t 클래스
ms.date: 11/04/2016
f1_keywords:
- _variant_t
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
ms.openlocfilehash: 69976cab9caed653a8278f80821569b613f690eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165952"
---
# <a name="variantt-class"></a>_variant_t 클래스

**Microsoft 전용**

A **_variant_t** 개체를 캡슐화 합니다 `VARIANT` 데이터 형식입니다. 클래스 리소스 할당 및 할당 취소를 관리 하 고 함수를 호출 하는 `VariantInit` 고 `VariantClear` 적절 하 게 합니다.

### <a name="construction"></a>생성

|||
|-|-|
|[_variant_t](../cpp/variant-t-variant-t.md)|생성 된 **_variant_t** 개체입니다.|

### <a name="operations"></a>작업

|||
|-|-|
|[Attach](../cpp/variant-t-attach.md)|연결 된 `VARIANT` 개체를 **_variant_t** 개체.|
|[지우기](../cpp/variant-t-clear.md)|캡슐화 된 지웁니다 `VARIANT` 개체입니다.|
|[ChangeType](../cpp/variant-t-changetype.md)|형식을 변경 합니다 **_variant_t** 표시 된 개체 `VARTYPE`합니다.|
|[Detach](../cpp/variant-t-detach.md)|캡슐화 된 분리 `VARIANT` 이 개체 **_variant_t** 개체입니다.|
|[SetString](../cpp/variant-t-setstring.md)|이 문자열을 할당 **_variant_t** 개체입니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](../cpp/variant-t-operator-equal.md)|기존에 새 값을 할당 **_variant_t** 개체입니다.|
|[operator ==, !=](../cpp/variant-t-relational-operators.md)|두 개를 비교 **_variant_t** 개체가 같음 또는 같지 않음.|
|[추출기](../cpp/variant-t-extractors.md)|캡슐화 된 데이터를 추출 `VARIANT` 개체입니다.|

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comutil.h >

**Lib:** comsuppw.lib 또는 comsuppwd.lib(자세한 내용은 [/zc: wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조)

## <a name="see-also"></a>참고자료

[컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)