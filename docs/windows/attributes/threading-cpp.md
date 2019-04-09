---
title: 스레딩 (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: cdebf06a62ebbd1d8648b9777fe200bc7a373261
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038280"
---
# <a name="threading-c"></a>threading(C++)

COM 개체에 대 한 스레딩 모델을 지정합니다.

## <a name="syntax"></a>구문

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>매개 변수

*model*<br/>
(선택 사항) 다음과 같은 스레딩 모델 중 하나입니다.

- `apartment` (아파트 스레딩)

- `neutral` (사용자 인터페이스를 사용 하 여.NET framework의 구성 요소)

- `single` (간단한 스레딩)

- `free` (자유 스레딩)

- `both` (아파트 및 자유 스레딩)

기본값은 `apartment`입니다.

## <a name="remarks"></a>설명

합니다 **스레딩** c + + 특성 생성된 된.idl 파일에서 표시 되지 않지만 COM 개체의 구현에서 사용 됩니다.

ATL 프로젝트의 경우는 [coclass](coclass.md) 특성이 있는에서 지정한 스레딩 모델 *모델* 템플릿 매개 변수로 전달 되는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 클래스 에 의해 삽입 된는 `coclass` 특성입니다.

합니다 **스레딩** 특성에는 또한에 대 한 액세스 보호를 [event_source](event-source.md)합니다.

## <a name="example"></a>예제

참조 된 [사용이 허가](licensed.md) 의 샘플 사용에 대 한 예제 **스레딩**합니다.

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

[COM 특성](com-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[이전 코드를 위한 다중 스레드 지원(Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[중립 아파트](/windows/desktop/cossdk/neutral-apartments)