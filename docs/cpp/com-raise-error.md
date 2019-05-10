---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 5790fceef26d6de4edff604270cc7108f764aced
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399254"
---
# <a name="comraiseerror"></a>_com_raise_error

**Microsoft 전용**

Throw 된 [_com_error](../cpp/com-error-class.md) 오류에 대 한 응답에서입니다.

## <a name="syntax"></a>구문

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>매개 변수

*hr*<br/>
HRESULT 정보입니다.

*perrinfo*<br/>
`IErrorInfo` 개체

## <a name="remarks"></a>설명

**_com_raise_error**에 정의 되어 있는 \<comdef.h >에서 동일한 이름과 프로토타입의 사용자 작성 버전으로 대체할 수 있습니다. 이는 `#import`를 사용하고 C++ 예외 처리는 사용하지 않으려는 경우 실행할 수 있습니다. 경우 사용자 버전에서 **_com_raise_error** 하기로 결정할 수는 `longjmp` 또는 메시지 상자를 표시 하 고 중지 합니다. 컴파일러 COM 지원 코드가 반환을 예상하고 있지 않기 때문에 사용자 버전은 반환할 수 없습니다.

사용할 수도 있습니다 [_set_com_error_handler](../cpp/set-com-error-handler.md) 기본 오류 처리 함수를 교체할 수 있습니다.

기본적으로 **_com_raise_error** 다음과 같이 정의 됩니다.

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comdef.h >

**Lib:** 경우는 **wchar_t is Native Type** 컴파일러 옵션이 설정 되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용 합니다. 만일 **wchar_t를 빌트인 타입으로 취급하기(Treat WChar_t As Built in Type)** 가 해제되어 있는 경우 comsupp.lib를 사용합니다. 자세한 내용은 [/Zc:wchar_t(wchar_t를 네이티브 형식으로 인식)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)