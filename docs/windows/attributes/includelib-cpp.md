---
title: includelib (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 57f039eeae527dd03884b12e7d9eb424d87f597f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409358"
---
# <a name="includelib-c"></a>includelib(C++)

생성된 된.idl 파일에 포함 될.idl 또는.h 파일을 사용 하면 됩니다.

## <a name="syntax"></a>구문

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>매개 변수

*name.idl*<br/>
생성된 된.idl 파일의 일부분으로 포함 하려는.idl 파일의 이름입니다.

## <a name="remarks"></a>설명

합니다 **includelib** C++ 특성을 한 후 생성 된.idl 파일에 포함 될.idl 또는.h 파일을 사용 하면 합니다 `importlib` 문입니다.

## <a name="example"></a>예제

다음 코드는.cpp 파일에 표시 됩니다.

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|예|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)