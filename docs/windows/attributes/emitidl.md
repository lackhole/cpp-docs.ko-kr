---
title: emitidl (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.emitidl
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
ms.openlocfilehash: 6c4055e0f14bced1e5047fc502a4bf274126f804
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031636"
---
# <a name="emitidl"></a>emitidl

모든 후속 IDL 특성 처리 되 고 생성된 된.idl 파일에 배치 하는지 여부를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>매개 변수

*state*<br/>
다음 값 중 하나: `true`, `false`를 `forced`, `restricted`에 `push`, 또는 `pop`합니다.

- 경우 `true`, 소스 코드 파일에서 발생 한 모든 IDL 범주 특성이 생성된 된.idl 파일에 배치 됩니다. 이것이 기본 설정에 대 한 **emitidl**합니다.

- 경우 `false`, 소스 코드 파일에서 발생 한 모든 IDL 범주 특성이 생성된 된.idl 파일에 배치 되지 합니다.

- 경우 `restricted`, IDL 특성 없이 파일에 포함 되도록 허용 된 [모듈](module-cpp.md) 특성. 컴파일러는.idl 파일을 생성 하지 않습니다.

- 경우 `forced`, 후속 재정의 `restricted` 있어야 파일 특성을는 `module` 특성 경우 IDL 파일의 특성입니다.

- `push` 현재 저장할 수 있습니다 **emitidl** 설정을 내부 **emitidl** 스택 및 `pop` 설정할 수 있습니다 **emitidl** 내부 맨 위에 있는 모든 값이 하 **emitidl** 스택.

`defaultimports=`*boolean* \(optional)

- 경우 *부울* 됩니다 **true**, docobj.idl 생성된 된.idl 파일을 가져오면 됩니다. 또한.idl 파일을.h 동일한 이름의 파일을 경우 `#include` 원본에 코드.h 파일과 동일한 디렉터리에 위치한 다음 생성된 된.idl 파일에는.idl 파일에 대 한 import 문을 포함 합니다.

- 하는 경우 *부울* 됩니다 **false**, docobj.idl는 생성 된.idl 파일을 가져올 수 없습니다. .Idl 파일을 명시적으로 가져와야 [가져올](import.md)합니다.

## <a name="remarks"></a>설명

후 합니다 **emitidl** 소스 코드 파일에서 c + + 특성이 있으면, IDL 범주 특성은 생성된 된.idl 파일에 배치 됩니다. 없는 경우 없습니다 **emitidl** 특성을 소스 코드 파일의 IDL 특성이 생성된 된.idl 파일에 출력 됩니다.

여러 개 있을 수 있기 **emitidl** 소스 코드 파일의 특성입니다. 하는 경우 `[emitidl(false)];` 후속 없이 파일에서 발생 `[emitidl(true)];`, 특성이 없는 생성된 된.idl 파일에 처리 됩니다.

컴파일러는 새 파일을 발견 될 때마다 **emitidl** 로 암시적으로 설정 됩니다 **true**합니다.

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
[독립 실행형 특성](stand-alone-attributes.md)
