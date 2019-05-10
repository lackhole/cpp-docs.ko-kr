---
title: helpfile (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 7aff6addffb13d2d45953d190eeaac518fe48d6d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409566"
---
# <a name="helpfile"></a>helpfile

형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.

## <a name="syntax"></a>구문

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
도움말 항목이 포함 된 파일의 이름입니다.

## <a name="remarks"></a>설명

**helpfile** C++ 특성에 동일한 기능을 합니다 [helpfile](/windows/desktop/Midl/helpfile) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [모듈](module-cpp.md) 사용 하는 방법의 예제 **helpfile**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**인터페이스**, **typedef**합니다 **클래스**, 메서드, **속성**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)