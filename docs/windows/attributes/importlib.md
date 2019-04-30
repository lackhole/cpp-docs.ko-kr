---
title: importlib (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: 29c7df8fbedbd107a9bb0b05466addc4672fc555
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409393"
---
# <a name="importlib"></a>importlib

다른 형식 라이브러리에 이미 컴파일된 형식을 만들고 있는 형식 라이브러리에서 사용할 수 있도록 합니다.

## <a name="syntax"></a>구문

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>매개 변수

*tlb_file*<br/>
현재 프로젝트의 형식 라이브러리로 가져오려는 .tlb 파일의 이름으로, 따옴표로 묶습니다.

## <a name="remarks"></a>설명

합니다 **importlib** C++ 원인 특성는 `importlib` 문이 생성된 된.idl 파일의 라이브러리 블록에 배치 합니다. 합니다 **importlib** 특성이 동일한 기능을 합니다 [importlib](/windows/desktop/Midl/importlib) MIDL 특성입니다.

## <a name="example"></a>예제

다음 코드를 사용 하는 방법의 예를 보여 줍니다 **importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
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

[컴파일러 특성](compiler-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)