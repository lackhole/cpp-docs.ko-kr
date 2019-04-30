---
title: 포함 (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: d9c68601bea4cecd92b371dada5fb086aeb7657f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409449"
---
# <a name="include-c"></a>include(C++)

생성된 된.idl 파일에 포함할 하나 이상의 헤더 파일을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>매개 변수

*header_file*<br/>
생성된 된.idl 파일에 포함 하려는 파일의 이름입니다.

## <a name="remarks"></a>설명

**포함** C++ 원인 특성는 `#include` 문 아래에 배치 하는 `import "docobj.idl"` 생성 된.idl 파일의 문.

**포함** C++ 특성에 동일한 기능을 합니다 [포함](/windows/desktop/Midl/include) MIDL 특성입니다.

## <a name="example"></a>예제

다음 코드를 사용 하는 방법의 예를 보여 줍니다 **포함**합니다. 예를 들어 파일 include.h만 포함 된 `#include` 문입니다.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)