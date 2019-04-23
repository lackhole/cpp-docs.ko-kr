---
title: idl_quote (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_quote
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
ms.openlocfilehash: fd7455298c9a1b69926d85766b6cd7f96bd374cc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037119"
---
# <a name="idlquote"></a>idl_quote

시각적 개체의 현재 버전에서 지원 되지 않는 IDL 구문을 사용할 수 있습니다 C++ 생성된 된.idl 파일을 통과 하도록 합니다.

## <a name="syntax"></a>구문

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>매개 변수

*텍스트*<br/>
특성 이름을 하려는 시각적 개체는 C++ 컴파일러에서 컴파일러 오류를 반환 하지 않고 생성된 된.idl 파일을 통과 합니다.

## <a name="remarks"></a>설명

경우는 **idl_quote** C++ 특성 (세미콜론으로 닫는 괄호 뒤), 독립 실행형 특성으로 사용 됩니다 *텍스트* 그대로 병합 된.idl 파일에 배치 됩니다. 하는 경우 **idl_quote** 기호를 사용할 경우 *텍스트* 해당 기호에 대 한 특성 블록 내에 배치 됩니다.

## <a name="example"></a>예제

다음 코드는 지원 되지 않는 특성을 지정할 수는 방법을 보여 줍니다 (사용 하 여 **에서**, 지원 되는) 정의 하는 정의 되지 않은.idl 구문을 사용 하는 방법과:

```cpp
// cpp_attr_ref_idl_quote.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];

[export]
struct MYFLOT {
   int i;
};

[export]
struct MYDUB {
   int i;
};

[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];

typedef struct _S1_TYPE {
   long l1;

union {
   MYFLOT f1; MYDUB d2; } U1_TYPE;
} S1_TYPE;

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]
__interface IStatic{
   HRESULT Func1([idl_quote("in")] int i);
   HRESULT func( S1_TYPE* myStruct );
};
```

이 코드를 사용 하면 `MYFLOT` 하 고 `MYDUB` 하며 *텍스트* 생성된 된.idl 파일에 배치할 항목. 합니다 *이름을* 매개 변수 *텍스트* 참조 하는 것 보다 먼저 배치할 *이름* 생성된 된.idl 파일에서. 합니다 *종속성* 매개 변수 앞에 배치 해야 하는 종속성 목록 정의가 강제로 *텍스트* 생성된 된.idl 파일에 있습니다.

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
[독립 실행형 특성](stand-alone-attributes.md)