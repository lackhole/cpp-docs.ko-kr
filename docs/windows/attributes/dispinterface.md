---
title: dispinterface (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 6fd5010dc20d03c518206d81919e3beafbcaa9a9
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346297"
---
# <a name="dispinterface"></a>dispinterface

.Idl 파일의 인터페이스를 디스패치 인터페이스로 배치합니다.

## <a name="syntax"></a>구문

```cpp
[dispinterface]
```

## <a name="remarks"></a>설명

**dispinterface** C++ 특성이 인터페이스 앞에 오면, 생성된 .idl 파일에서 인터페이스가 라이브러리 블록 내부에 배치됩니다.

기본 클래스를 지정하지 않으면 디스패치 인터페이스가 `IDispatch`에서 파생됩니다. 디스패치 인터페이스의 멤버에 대한 [id](id.md) 를 지정해야 합니다.

MIDL 문서에 있는 [dispinterface](/windows/desktop/Midl/dispinterface) 의 사용 예:

```cpp
dispinterface helloPro
   { interface hello; };
```

**dispinterface** 특성에 대해 유효하지 않습니다.

## <a name="example"></a>예제

[dispinterface](bindable.md) 사용법에 대한 예는 **bindable**의 예를 참조하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[용도별 특성](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)