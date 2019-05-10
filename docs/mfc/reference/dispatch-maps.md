---
title: 디스패치 맵
ms.date: 06/20/2018
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 5ebedaa02a03bcc7802110977b96659dae45f174
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322516"
---
# <a name="dispatch-maps"></a>디스패치 맵

OLE 자동화 메서드를 호출 하 고 응용 프로그램에서 속성에 액세스 하는 방법을 제공 합니다. 이러한 요청을 디스패치를 위한 Microsoft Foundation Class 라이브러리에서 제공 하는 메커니즘은 "디스패치 맵," 데이터 형식 및 속성 자체 뿐만 아니라 개체 함수 및 속성의 내부 및 외부 이름을 지정 하는 함수 인수입니다.

|디스패치 맵 매크로|설명|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|디스패치 맵 클래스의 메서드 및 속성 (클래스 선언에서 사용 해야 합니다)를 노출 하는 선언 합니다.|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|디스패치 맵 정의 시작합니다.|
|[END_DISPATCH_MAP](#end_dispatch_map)|디스패치 맵 정의 종료합니다.|
|[DISP_FUNCTION](#disp_function)|디스패치 맵 사용 하 여 OLE automation 함수를 정의 합니다.|
|[DISP_PROPERTY](#disp_property)|OLE 자동화 속성을 정의합니다.|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE 자동화 속성을 정의 하 고 Get 및 Set 함수 이름을 지정 합니다.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|알림 사용 하 여 OLE 자동화 속성을 정의합니다.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Get 및 Set 함수 이름과 매개 변수를 사용 하는 OLE 자동화 속성을 정의 합니다.|
|[DISP_DEFVALUE](#disp_defvalue)|기존 속성을 개체의 기본값으로 만듭니다.|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

경우는 `CCmdTarget`-프로그램의 파생된 클래스는 OLE 자동화 클래스의 메서드 및 속성을 노출 하는 디스패치 맵을 제공 하는 지원 합니다.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>설명

클래스 선언의 끝 DECLARE_DISPATCH_MAP 매크로 사용 합니다. 그런 다음 합니다. BEGIN_DISPATCH_MAP 매크로 사용 하는 클래스의 멤버 함수를 정의 하는 CPP 파일입니다. 각 클래스에 노출 된 메서드 및 속성 (DISP_FUNCTION, DISP_PROPERTY, 및 등)에 대해 매크로 항목을 포함 합니다. 마지막으로, END_DISPATCH_MAP 매크로 사용 합니다.

> [!NOTE]
> DECLARE_DISPATCH_MAP 후 멤버를 선언 하는 경우 새 액세스 유형을 지정 해야 합니다 ( **공개**, **개인**, 또는 **보호**)에 있습니다.

응용 프로그램 마법사 및 코드 마법사 자동화 클래스 만들기에 디스패치 맵을 유지 관리를 지원 합니다. 디스패치 맵에 대 한 자세한 내용은 참조 하세요. [자동화 서버](../../mfc/automation-servers.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP

디스패치 맵의 정의 선언합니다.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
디스패치 맵입니다.이 소유 하는 클래스의 이름을 지정 합니다.

*baseClass*<br/>
기본 클래스 이름을 지정 *theClass*합니다.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 시작 디스패치 맵 BEGIN_DISPATCH_MAP 매크로 사용 하 여, 각 디스패치 함수 및 속성에 대해 매크로 항목을 추가 및 완료를 END_DISPATCH_ 사용 하 여 디스패치 맵 맵 매크로입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

디스패치 맵의 정의 종료합니다.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>설명

BEGIN_DISPATCH_MAP와 함께에서 사용 해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

디스패치 맵에서 OLE automation 함수를 정의합니다.

```cpp
DISP_FUNCTION(
  theClass,
  pszName,
  pfnMember,
  vtRetVal,
  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
외부 함수의 이름입니다.

*pfnMember*<br/>
멤버 함수의 이름입니다.

*vtRetVal*<br/>
함수의 반환 형식을 지정 하는 값입니다.

*vtsParams*<br/>
함수의 매개 변수 목록을 지정 하는 하나 이상의 상수의 공백으로 구분 된 목록입니다.

### <a name="remarks"></a>설명

합니다 *vtRetVal* 인수 VARTYPE 형식입니다. 이 인수에 대 한 가능한 값은 다음과에서 수행 되는 `VARENUM` 열거형:

|기호|반환 형식|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*vtsParams* 인수는 공백으로 구분 된 목록에서 값을 `VTS_*` 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들면 다음과 같습니다.

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

에 대 한 포인터 뒤에 정수 (short)를 정수 (short)이 포함 된 목록을 지정 합니다.

`VTS_` 상수 및 해당 의미는 다음과 같습니다.

|기호|매개 변수 유형|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` 또는 `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPDISPATCH|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` 또는 `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__short\*__|
|VTS_PI4|__long\*__|
|VTS_PR4|__float\*__|
|VTS_PR8|__double\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|매개 변수 없이|

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property"></a>  DISP_PROPERTY

디스패치 맵에서 OLE 자동화 속성을 정의합니다.

```cpp
DISP_PROPERTY(
  theClass,
  pszName,
  memberName,
  vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*memberName*<br/>
속성이 저장 되는 멤버 변수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

합니다 *vtPropType* 형식의 인수가 **VARTYPE**합니다. 이 인수에 대 한 가능한 값은 VARENUM 열거에서 수행 됩니다.

|기호|속성 형식|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

외부 클라이언트 속성에 의해 지정 된 멤버 변수의 값을 변경 하는 경우 *memberName* 변경;는 변경 알림이 있습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property_ex"></a>  DISP_PROPERTY_EX

가져오기 및 디스패치 맵에서 속성의 값을 설정 하는 데 사용 하는 함수 이름과 OLE 자동화 속성을 정의 합니다.

```cpp
DISP_PROPERTY_EX(
  theClass,
  pszName,
  memberGet,
  memberSet,
  vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*memberGet*<br/>
속성을 가져오는 데 멤버 함수의 이름입니다.

*memberSet*<br/>
속성을 설정 하는 데 사용 하는 멤버 함수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

*memberGet* 및 *memberSet* 함수 시그니처가 의해 결정 된 *vtPropType* 인수. 합니다 *memberGet* 함수 없습니다 인수를 사용 하 여 지정 된 형식의 값을 반환 *vtPropType*합니다. *memberSet* 함수에서 지정 된 형식의 인수를 사용 *vtPropType* nothing을 반환 합니다.

합니다 *vtPropType* 인수 VARTYPE 형식입니다. 이 인수에 대 한 가능한 값은 VARENUM 열거에서 가져옵니다. 이러한 값을 목록에 대 한 설명을 참조는 *vtRetVal* 에 매개 변수 [DISP_FUNCTION](#disp_function)합니다. 참고는 VT_EMPTY를 DISP_FUNCTION 주의에 나열 된 속성 데이터 형식으로 허용 되지 않습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

디스패치 맵에서 알림 사용 하 여 OLE 자동화 속성을 정의합니다.

```cpp
DISP_PROPERTY_NOTIFY(
  theClass,
  szExternalName,
  memberName,
  pfnAfterSet,
  vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*szExternalName*<br/>
속성의 외부 이름입니다.

*memberName*<br/>
속성이 저장 되는 멤버 변수의 이름입니다.

*pfnAfterSet*<br/>
이름에 대 한 알림 함수의 *szExternalName*합니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

DISP_PROPERTY를 사용 하 여 정의 된 속성과 달리 DISP_PROPERTY_NOTIFY를 사용 하 여 정의 된 속성이 자동으로 호출 하 여 지정 된 함수 *pfnAfterSet* 속성이 변경 될 경우.

합니다 *vtPropType* 인수 VARTYPE 형식입니다. 이 인수에 대 한 가능한 값은 VARENUM 열거에서 수행 됩니다.

|기호|속성 형식|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM

별도의 액세스 속성을 정의 `Get` 및 `Set` 멤버 함수입니다.

```cpp
DISP_PROPERTY_PARAM(
  theClass,
  pszExternalName,
  pfnGet,
  pfnSet,
  vtPropType,
  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszExternalName*<br/>
속성의 외부 이름입니다.

*pfnGet*<br/>
속성을 가져오는 데 멤버 함수의 이름입니다.

*pfnSet*<br/>
속성을 설정 하는 데 사용 하는 멤버 함수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

*vtsParams*<br/>
공백으로 구분 된 문자열 `VTS_*` 각 매개 변수에 대해 하나씩 가변 매개 변수 형식입니다.

### <a name="remarks"></a>설명

DISP_PROPERTY_EX 매크로 달리이 매크로 사용 하면 속성에 대 한 매개 변수 목록을 지정할 수 있습니다. 매개 변수화 되거나 인덱싱된 속성을 구현 하기 위한 유용 합니다.

### <a name="example"></a>예제

Get의 다음 선언을 고려 하십시오 및 집합 멤버 속성에 액세스 하는 경우 특정 행과 열을 요청 하는 데 사용할 수 있는 함수:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

이러한 컨트롤 디스패치 맵에 다음 DISP_PROPERTY_PARAM 매크로에 해당합니다.

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

또 다른 예로, 다음 get는 것이 좋습니다 및 함수 멤버를 설정 합니다.

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

이러한 컨트롤 디스패치 맵에 다음 DISP_PROPERTY_PARAM 매크로에 해당합니다.

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_defvalue"></a>  DISP_DEFVALUE

기존 속성을 개체의 기본값으로 만듭니다.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
개체의 "값"을 나타내는 속성의 외부 이름입니다.

### <a name="remarks"></a>설명

기본값을 사용하면 Visual Basic 응용 프로그램에 대한 자동화 개체 프로그래밍을 더 간소화할 수 있습니다.

개체의 "기본값"은 개체에 대한 참조가 속성 또는 멤버 함수를 지정하지 않을 때 검색 또는 설정되는 속성입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
