---
title: 컴파일러 COM 지원 클래스
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: 066fe797bc500625e96e027777a70f278b88cddb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399202"
---
# <a name="compiler-com-support-classes"></a>컴파일러 COM 지원 클래스

**Microsoft 전용**

표준 클래스는 COM 형식 중 일부를 지원하는 데 사용됩니다. 클래스에 정의 된 \<comdef.h > 및 형식 라이브러리에서 생성 된 헤더 파일입니다.

|클래스|용도|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|`BSTR` 형식을 래핑하여 유용한 연산자와 메서드를 제공합니다.|
|[_com_error](../cpp/com-error-class.md)|throw 된 오류 개체를 정의 [_com_raise_error](../cpp/com-raise-error.md) 대부분의 오류가 발생 합니다.|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM 인터페이스 포인터를 캡슐화 하 고 필요한 호출을 자동화 `AddRef`하십시오 `Release`, 및 `QueryInterface`합니다.|
|[_variant_t](../cpp/variant-t-class.md)|`VARIANT` 형식을 래핑하여 유용한 연산자와 메서드를 제공합니다.|

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 COM 지원](../cpp/compiler-com-support.md)<br/>
[컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)