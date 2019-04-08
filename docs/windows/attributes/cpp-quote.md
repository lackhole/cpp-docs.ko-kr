---
title: cpp_quote (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 378435ced5a541785b7b32bc9d2f408034d5a2d8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024686"
---
# <a name="cppquote"></a>cpp_quote

생성된 된.idl 파일의 따옴표 없이 지정된 된 문자열을 내보냅니다.

## <a name="syntax"></a>구문

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>매개 변수

*statement*<br/>
C 명령입니다.

## <a name="remarks"></a>설명

합니다 **cpp_quote** c + + 특성은.idl 파일에서 전처리기 지시문을 배치 하려는 경우에 유용 합니다.

사용할 수도 있습니다 **cpp_quote** MIDL 컴파일의 일부로.h 파일을 생성 합니다. 예를 들어, c + + IDL 특성을 사용 하지만 일부 작업에 대 한이 파일을 사용할 수 없습니다는 c + + 헤더 파일에 있으면 다음 컴파일할 수 있습니다 하 여 사용할 수 있어야 하는.h 있으므로 MIDL 생성 파일을 만듭니다.

합니다 **cpp_quote** 특성이 동일한 기능을 합니다 [cpp_quote](/windows/desktop/Midl/cpp-quote) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [이중](dual.md) 예로 사용 하는 방법을 사용 하 여 **cpp_quote**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)