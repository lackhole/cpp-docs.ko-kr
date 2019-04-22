---
title: 버전 (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: fe1df9e12b9adbf9ce55978fd3479f7e740ddc96
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025754"
---
# <a name="version-c"></a>version(C++)

클래스의 여러 버전 중에서 특정 버전을 식별합니다.

## <a name="syntax"></a>구문

```cpp
[ version("version") ]
```

### <a name="parameters"></a>매개 변수

*version*<br/>
버전 번호는 `coclass`합니다. 지정 하지 않으면 1.0.idl 파일에 배치 됩니다.

## <a name="remarks"></a>설명

합니다 **버전** C++ 특성에 동일한 기능을 합니다 [버전](/windows/desktop/Midl/version) MIDL 특성 생성된 된.idl 파일에 전달 됩니다.

## <a name="example"></a>예제

참조를 [bindable](bindable.md) 의 샘플 사용에 대 한 예제 **버전**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|아니요|
|**필수 특성**|**coclass**|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[컴파일러 특성](compiler-attributes.md)<br/>
[클래스 특성](class-attributes.md)