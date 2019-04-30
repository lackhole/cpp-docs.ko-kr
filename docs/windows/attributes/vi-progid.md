---
title: vi_progid (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: 7050543c9acf3801a99d3e32e119325900bdb050
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404769"
---
# <a name="viprogid"></a>vi_progid

ProgID의 버전에 관계 없이 폼을 지정합니다.

## <a name="syntax"></a>구문

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>매개 변수

*name*<br/>
개체를 나타내는 버전 독립 ProgID입니다.

Progid는 COM/ActiveX 개체를 식별 하는 데 클래스 식별자 (CLSID)의 알기 쉬운 버전을 제공 합니다.

## <a name="remarks"></a>설명

합니다 **vi_progid** C++ 특성을 사용 하면 COM 개체에 대 한 버전 독립 ProgID를 지정 합니다. 형식은 ProgID *name1.name2.version*합니다. 버전 종속 ProgID 없는 *버전*합니다. 둘 다 지정할 수는 `progid` 하며 **vi_progid** 특성을 `coclass`. 지정 하지 않는 경우 **vi_progid**의 버전 독립 ProgID가 지정 된 값을 [progid](progid.md) 특성입니다.

**vi_progid** 의미 합니다 `coclass` 지정 하는 경우, 특성 **vi_progid**, 다릅니다 지정 하는 것을 `coclass` 및 **vi_progid** 특성입니다.

합니다 **vi_progid** 특성을 사용 하면 지정 된 이름으로 자동으로 등록 하는 클래스입니다. 생성된 된.idl 파일 ProgID 값이 표시 됩니다.

ATL 프로젝트의 경우는 [coclass](coclass.md) 특성도, 지정 된 ProgID를 사용 되는 `GetVersionIndependentProgID` 함수 (삽입을 `coclass` 특성).

## <a name="example"></a>예제

참조 된 [coclass](coclass.md) 의 샘플 사용에 대 한 예제 **vi_progid**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[ProgID 키](/windows/desktop/com/-progid--key)
