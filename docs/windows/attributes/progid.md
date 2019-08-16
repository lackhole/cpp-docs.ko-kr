---
title: progid (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: d529d7362dc62207cfd72576159f560a3e04c221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514242"
---
# <a name="progid"></a>progid

COM 개체의 ProgID를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>매개 변수

*name*<br/>
개체를 나타내는 ProgID입니다.

Progid는 COM/ActiveX 개체를 식별 하는 데 사용 되는 CLSID (클래스 식별자)의 사람이 읽을 수 있는 버전입니다.

## <a name="remarks"></a>설명

**Progid** C++ 특성을 사용 하면 COM 개체에 대해 progid를 지정할 수 있습니다. ProgID의 형식은 name1. *name2. 버전*입니다. ProgID에 대 한 *버전* 을 지정 하지 않으면 기본 버전은 1입니다. *Name1. name2*를 지정 하지 않는 경우 기본 이름은 *classname*입니다. **Progid** 를 지정 하지 않고를 지정 `vi_progid`하는 경우에는 `vi_progid` name1이 사용 되 고 (다음 일련 번호) 버전이 추가 됩니다.

**Progid** 를 사용 하는 특성 블록에서 **uuid**를 사용 하지 않는 경우 컴파일러는 레지스트리를 확인 하 여 지정 된 **progid**에 대해 **uuid** 가 있는지 확인 합니다. **Progid** 를 지정 하지 않으면 버전 (coclass를 만드는 경우 coclass 이름)이 **progid**를 생성 하는 데 사용 됩니다.

**progid** 는 `coclass` 특성을 암시 합니다. 즉, **progid**를 지정 하는 경우 `coclass` 및 **progid** 특성을 지정 하는 것과 같습니다.

**Progid** 특성을 지정 하면 지정 된 이름으로 클래스가 자동으로 등록 됩니다. 생성 된 .idl 파일에는 **progid** 값이 표시 되지 않습니다.

ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하는 경우 특성의 동작이 변경 됩니다. 위의 동작 외에도이 특성을 사용 하 여 지정 된 정보는 `GetProgID` 함수에서 `coclass` 특성에 의해 삽입 됩니다. 자세한 내용은 [coclass](coclass.md) 특성을 참조 하세요.

## <a name="example"></a>예제

**Progid**의 샘플 사용에 대해서는 [coclass](coclass.md) 의 예제를 참조 하세요.

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
[클래스 특성](class-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID 키](/windows/win32/com/-progid--key)
