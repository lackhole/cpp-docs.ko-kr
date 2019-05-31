---
title: 런타임 개체 모델 서비스
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: 3e9c3dcc02cb4307787f3e0baf5e99ac31b3d183
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174844"
---
# <a name="run-time-object-model-services"></a>런타임 개체 모델 서비스

클래스 [CObject](../../mfc/reference/cobject-class.md) 하 고 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 런타임 클래스 정보, serialization 및 동적 개체 만들기에 대 한 액세스를 포함 하 여 여러 개체 서비스를 캡슐화 합니다. 모든 클래스에서 파생 된 `CObject` 이 기능을 상속 합니다.

런타임 클래스 정보에 대 한 액세스를 사용 하면 런타임 시 개체의 클래스에 대 한 정보를 확인할 수 있습니다. 런타임 시 개체의 클래스를 결정 하는 기능 추가 형식 검사 함수 인수 및 개체의 클래스를 기반으로 하는 특수 한 용도의 코드를 작성 해야 할 때 유용 합니다. 런타임 클래스 정보로 직접 지원 되지 않습니다는 C++ 언어입니다.

Serialization은 쓰거나 읽을 하거나 개체의 내용을 파일에서의 프로세스입니다. 응용 프로그램 종료 후에 개체의 내용을 저장 하려면 serialization을 사용할 수 있습니다. 응용 프로그램 다시 시작 되 면 개체 파일에서 읽을 수 있습니다. 이러한 데이터 개체를 "영구." 라고 합니다.

동적 개체 만들기를 사용 하면 런타임에 지정된 된 클래스의 개체를 만들 수 있습니다. 예를 들어, 문서, 뷰 및 프레임 개체 지원 해야 동적 생성 프레임 워크를 동적으로 만들고 해야 하기 때문에 합니다.

다음 표에서 런타임 클래스 정보, serialization 및 동적 생성을 지 원하는 MFC 매크로 나열 합니다.

이러한 런타임 개체 서비스와 serialization에 대 한 자세한 내용은 문서를 참조 하세요. [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.

### <a name="run-time-object-model-services-macros"></a>런타임 개체 모델 서비스 매크로

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|(클래스 선언에서 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있습니다.|
|[DECLARE_DYNCREATE](#declare_dyncreate)|동적 만들기 (클래스 선언에서 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있습니다.|
|[DECLARE_SERIAL](#declare_serial)|Serialization 및 런타임 클래스 정보 (클래스 선언에서 사용 해야 합니다)에 액세스할 수 있습니다.|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|(클래스 구현에 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있습니다.|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|동적 만들기 (클래스 구현에 사용 해야 합니다) 런타임 정보에 액세스할 수 있습니다.|
|[IMPLEMENT_SERIAL](#implement_serial)|Serialization 및 런타임 클래스 정보 (클래스 구현에 사용 해야 합니다)에 대 한 액세스를 허용 합니다.|
|[RUNTIME_CLASS](#runtime_class)|반환 된 `CRuntimeClass` 명명된 된 클래스에 해당 합니다.|

OLE 개체의 런타임 시 동적 생성을 자주 필요합니다. 예를 들어 OLE 서버 응용 프로그램 클라이언트의 요청에 응답에서 OLE 항목을 동적으로 만들 수 있어야 합니다. 마찬가지로, 자동화 서버 항목을 만드는 자동화 클라이언트에서 요청에 응답할에서 수 있어야 합니다.

Microsoft Foundation Class 라이브러리를 OLE에 특정 두 매크로 제공합니다.

### <a name="dynamic-creation-of-ole-objects"></a>OLE 개체의 동적 생성

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|공용 컨트롤 라이브러리에서 지정 된 API를 구현 하는지 여부를 결정 합니다.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|공용 컨트롤 라이브러리에서 지정 된 API를 구현 하는지 여부를 결정 합니다.|
|[DECLARE_OLECREATE](#declare_olecreate)|개체를를 OLE 자동화를 통해 만들 수 있습니다.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|선언 된 `GetUserTypeNameID` 고 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE 컨트롤 속성을 표시 하도록 속성 페이지의 목록을 제공 하는 선언 합니다.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|개체를를 OLE 시스템에서 만들 수 있습니다.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|구현 된 `GetUserTypeNameID` 고 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE](#implement_olecreate) 사용 하는 모든 클래스의 구현 파일에 표시 되어야 `DECLARE_OLECREATE`합니다. |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS

공용 컨트롤 라이브러리에서 지정 된 API를 구현 하는지 여부를 결정 합니다.

### <a name="syntax"></a>구문

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>매개 변수

*proc*<br/>
함수 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 또는 함수의 서 수 값을 지정 합니다. 하위 단어;에 있어야이 매개 변수 서 수 값 인 경우 상위 단어에는 0 이어야 합니다. 이 매개 변수는 유니코드 여야 합니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 공용 컨트롤 라이브러리 함수가 지정 여부를 결정할 *proc* (호출 하는 대신 [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress)합니다.

### <a name="requirements"></a>요구 사항

afxcomctl32.h, afxcomctl32.inl이

## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2

공용 컨트롤 라이브러리에서 지정 된 API를 구현 하는지 여부를 결정 합니다. (이 버전의 유니코드 버전 이기 [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).

### <a name="syntax"></a>구문

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>매개 변수

*proc*<br/>
함수 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 또는 함수의 서 수 값을 지정 합니다. 하위 단어;에 있어야이 매개 변수 서 수 값 인 경우 상위 단어에는 0 이어야 합니다. 이 매개 변수는 유니코드 여야 합니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 공용 컨트롤 라이브러리 함수가 지정 여부를 결정할 *proc* (호출 하는 대신 [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress)합니다. 이 매크로 AFX_COMCTL32_IF_EXISTS의 유니코드 버전입니다.

### <a name="requirements"></a>요구 사항

afxcomctl32.h, afxcomctl32.inl이

##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC

클래스를 파생 하는 경우 개체의 클래스에 대 한 런타임 정보에 액세스할 수 있도록 추가 `CObject`합니다.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

DECLARE_DYNAMIC 매크로 클래스에 대 한 헤더 (.h) 모듈에 추가한 다음이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에서 해당 모듈을 포함 합니다.

설명 된 대로 DECLARE_ 동적이 고 IMPLEMENT_DYNAMIC 매크로 사용 하는 경우 다음 RUNTIME_CLASS 매크로 사용할 수 및 `CObject::IsKindOf` 런타임에 개체의 클래스를 결정 하는 함수입니다.

DECLARE_DYNAMIC 클래스 선언에 포함 되어 IMPLEMENT_DYNAMIC 클래스 구현에 포함 되어야 합니다.

DECLARE_DYNAMIC 매크로에 대 한 자세한 내용은 참조 하세요. [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [IMPLEMENT_DYNAMIC](#implement_dynamic)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE

개체를 사용 하면 `CObject`-런타임에 동적으로 만들 클래스를 파생 합니다.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

프레임 워크는이 기능을 사용 하 여 새 개체를 동적으로 만들 수 있습니다. 예를 들어, 새 보기 새 문서를 열었을 때 생성 됩니다. 문서, 뷰 및 프레임 클래스는 프레임 워크를 동적으로 만들고 해야 하기 때문에 동적 만들기를 지원 해야 합니다.

DECLARE_DYNCREATE 매크로 클래스의 경우.h 모듈에서 추가한 다음이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에서 해당 모듈을 포함 합니다.

DECLARE_DYNCREATE 클래스 선언에 포함 되어 IMPLEMENT_DYNCREATE 클래스 구현에 포함 되어야 합니다.

DECLARE_DYNCREATE 매크로에 대 한 자세한 내용은 참조 하세요. [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

> [!NOTE]
>  DECLARE_DYNCREATE 매크로 DECLARE_DYNAMIC의 모든 기능을 포함 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [IMPLEMENT_DYNCREATE](#implement_dyncreate)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="declare_olectltype"></a> DECLARE_OLECTLTYPE

선언 된 `GetUserTypeNameID` 고 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.

### <a name="syntax"></a>구문

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

`GetUserTypeNameID` 및 `GetMiscStatus` 에 선언 된 순수 가상 함수에는 `COleControl`합니다. 이러한 함수는 순수 가상 이러한 재정의 되어야 컨트롤 클래스의 합니다. DECLARE_OLECTLTYPE, 외에도 IMPLEMENT_OLECTLTYPE 매크로 컨트롤 클래스 선언에 추가 해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="declare_proppageids"></a> DECLARE_PROPPAGEIDS

OLE 컨트롤 속성을 표시 하도록 속성 페이지의 목록을 제공 하는 선언 합니다.

### <a name="syntax"></a>구문

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
속성 페이지를 소유 하는 컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

사용 된 `DECLARE_PROPPAGEIDS` 클래스 선언의 끝 매크로입니다. 그런 다음 클래스의 멤버 함수를 정의 하는.cpp 파일에서 사용 하 여 합니다 `BEGIN_PROPPAGEIDS` 매크로, 각 컨트롤의 속성 페이지에 대해 매크로 항목 및 `END_PROPPAGEIDS` 속성 페이지 목록의 끝을 선언 하는 매크로입니다.

속성 페이지에 대 한 자세한 내용은 문서를 참조 하세요. [ActiveX 컨트롤: 속성 페이지](../mfc-activex-controls-property-pages.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="declare_serial"></a>  DECLARE_SERIAL

생성은 C++ 에 필요한 헤더 코드를 `CObject`-serialize 할 수 있는 클래스를 파생 합니다.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

Serialization은 파일에서 기록 하거나를 개체의 내용을 읽는 프로세스입니다.

DECLARE_SERIAL 매크로.h 모듈에서 사용 하 고이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈의 해당 모듈을 포함 합니다.

DECLARE_SERIAL 클래스 선언에 포함 되어 IMPLEMENT_SERIAL 클래스 구현에 포함 되어야 합니다.

DECLARE_SERIAL 매크로 DECLARE_DYNAMIC 및 DECLARE_DYNCREATE의 모든 기능을 포함 합니다.

AFX_API 매크로 사용 하 여 자동으로 내보낼 수는 `CArchive` DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로 사용 하는 클래스에 대 한 추출 연산자입니다. 다음 코드를 사용 하 여 클래스 선언을 (.h 파일에 있음)를 대괄호로 묶습니다.

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

DECLARE_SERIAL 매크로에 대 한 자세한 내용은 참조 하세요. [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="implement_dynamic"></a>  IMPLEMENT_DYNAMIC

생성 된 C++ 동적 하는 데 필요한 코드 `CObject`-클래스 이름 및 계층 내 위치에 런타임 액세스를 사용 하 여 클래스를 파생 합니다.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*base_class_name*<br/>
기본 클래스의 이름입니다.

### <a name="remarks"></a>설명

.Cpp 모듈에서 IMPLEMENT_DYNAMIC 매크로 사용 하 고 결과 개체 코드를 한 번만 연결 합니다.

자세한 내용은 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE

개체를 사용 하면 `CObject`-런타임에 동적으로 생성 될 클래스를 파생 DECLARE_DYNCREATE 매크로 사용 하는 경우 시간입니다.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*base_class_name*<br/>
기본 클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

이 기능을 사용 하 여 새 개체를 동적으로 만들거나 예를 들어, 직렬화 하는 동안 디스크에서 개체를 읽을 경우에 프레임 워크입니다. 클래스 구현 파일에서 IMPLEMENT_DYNCREATE 매크로 추가 합니다. 자세한 내용은 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

DECLARE_DYNCREATE 및 IMPLEMENT_DYNCREATE 매크로 사용 하는 경우 사용할 수 있습니다 RUNTIME_CLASS 매크로 및 `CObject::IsKindOf` 런타임에 개체의 클래스를 결정 하는 멤버 함수입니다.

DECLARE_DYNCREATE 클래스 선언에 포함 되어 IMPLEMENT_DYNCREATE 클래스 구현에 포함 되어야 합니다.

이 매크로 정의 클래스에 대 한 기본 생성자를 호출 하는 참고 합니다. Trivial이 아닌 생성자를 클래스에 의해 명시적으로 구현 되는 경우 명시적으로 기본 생성자도 구현 해야 합니다. 기본 생성자는 클래스에 추가할 수 있습니다 **사설** 하거나 **보호** 클래스 구현 외부에서 호출 되지 않도록 멤버 섹션.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS

이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE](#implement_olecreate) DECLARE_OLECREATE를 사용 하는 모든 클래스의 구현 파일에 표시 되어야 합니다.

### <a name="syntax"></a>구문

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*external_name*<br/>
(인용 부호 안에 포함 됨) 다른 응용 프로그램에 노출 되는 개체 이름입니다.

*nFlags*<br/>
다음 플래그 중 하나 이상 포함 되어 있습니다.

   - `afxRegInsertable` OLE 개체에 대 한 개체 삽입 대화 상자에 표시를 제어할 수 있습니다.
   - `afxRegApartmentThreading` ThreadingModel 레지스트리의 스레딩 모델을 설정 하는 아파트 =.
   - `afxRegFreeThreading` ThreadingModel 레지스트리의 스레딩 모델을 설정 합니다. 무료 =.

         You can combine the two flags `afxRegApartmentThreading` and `afxRegFreeThreading` to set ThreadingModel=Both. See [InprocServer32](/windows/desktop/com/inprocserver32) in the Windows SDK for more information on threading model registration.

*l*, *w1*를 *w2*를 *b1*를 *b2*를 *b3*, *b4* 를 *b5*를 *b6*를 *b7*를 *b 8* 클래스의 CLSID의 구성 요소입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  IMPLEMENT_OLECREATE_FLAGS를 사용 하는 경우에 개체에서 사용 하 여 스레딩 모델을 지정할 수 있습니다 합니다 *nFlags* 매개 변수입니다. 단일 스레딩 모델만 지원 하려는 경우 IMPLEMENT_OLECREATE를 사용 합니다.

External name에 다른 응용 프로그램에 노출 된 식별자입니다. 클라이언트 응용 프로그램에서는 외부 이름을 사용 하 여 자동화 서버에서이 클래스의 개체를 요청 합니다.

OLE 클래스 ID가 고유 128 비트 식별자 개체입니다. 하나 이루어져 **긴**, 두 개의 **WORD**및 8 **바이트**s에 의해 표시 된 대로 *l*를 *w1*, *w2*, 및 *b1* 를 통해 *b 8* 구문 설명에서 합니다. 응용 프로그램 마법사 및 코드 마법사를 필요에 따라 고유한 OLE 클래스 Id를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="implement_olectltype"></a> IMPLEMENT_OLECTLTYPE

구현 된 `GetUserTypeNameID` 고 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.

### <a name="syntax"></a>구문

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 클래스의 이름입니다.

*idsUserTypeName*<br/>
컨트롤의 외부 이름을 포함 하는 문자열의 리소스 ID입니다.

*dwOleMisc*<br/>
하나 이상의 플래그를 포함 하는 열거형입니다. 이 열거형에 대 한 자세한 내용은 참조 하세요. [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Windows SDK에 있습니다.

### <a name="remarks"></a>설명

IMPLEMENT_OLECTLTYPE, 외에도 DECLARE_OLECTLTYPE 매크로 컨트롤 클래스 선언에 추가 해야 합니다.

`GetUserTypeNameID` 멤버 함수는 사용자 컨트롤 클래스를 식별 하는 리소스 문자열을 반환 합니다. `GetMiscStatus` 컨트롤에 대 한 OLEMISC 비트를 반환합니다. 이 열거형 컨트롤의 기타 특성을 설명 하는 설정의 컬렉션을 지정 합니다. 에 대 한 전체 설명은 OLEMISC 설정을 참조 하세요 [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Windows SDK에 있습니다.

> [!NOTE]
>  ActiveX 컨트롤에서 사용 하는 기본 설정은 다음과 같습니다. OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE, 및 OLEMISC_RECOMPOSEONRESIZE 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL

생성 된 C++ 동적 하는 데 필요한 코드 `CObject`-클래스 이름 및 계층 내 위치에 런타임 액세스를 사용 하 여 클래스를 파생 합니다.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*base_class_name*<br/>
기본 클래스의 이름입니다.

*wSchema*<br/>
UINT "버전 번호를" 보관 식별 하 고 처리 하 여 생성 된 데이터를 역직렬화 하는 중 프로그램을 사용 하도록 설정 하려면 인코딩할는 이전 버전을 프로그래밍 합니다. 클래스 스키마 수-1이 아니어야 합니다.

### <a name="remarks"></a>설명

IMPLEMENT_SERIAL 매크로 모듈에서에서 사용할.cpp; 다음 결과 개체 코드를 한 번만 연결 합니다.

AFX_API 매크로 사용 하 여 자동으로 내보낼 수는 `CArchive` DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로 사용 하는 클래스에 대 한 추출 연산자입니다. 다음 코드를 사용 하 여 클래스 선언을 (.h 파일에 있음)를 대괄호로 묶습니다.

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

자세한 내용은 참조는 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="runtime_class"></a>  RUNTIME_CLASS

이름에서의 런타임 클래스 구조를 가져옵니다는 C++ 클래스입니다.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
실제 이름 (따옴표로 묶이지) 클래스입니다.

### <a name="remarks"></a>설명

RUNTIME_CLASS 반환에 대 한 포인터를 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 에서 지정한 클래스에 대 한 구조 *class_name*합니다. 만 `CObject`-DECLARE_DYNAMIC, DECLARE_DYNCREATE, 또는 DECLARE_SERIAL를 사용 하 여 선언 된 파생된 클래스에 대 한 포인터를 반환 합니다는 `CRuntimeClass` 구조입니다.

자세한 내용은 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE

개체를 사용 하면 `CCmdTarget`-OLE 자동화를 통해 생성 되는 클래스를 파생 합니다.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

이 매크로 다른 OLE 지원 응용 프로그램이이 형식의 개체를 만들 수 있습니다.

DECLARE_OLECREATE 매크로 클래스의 경우.h 모듈에서 추가한 다음이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에서 해당 모듈을 포함 합니다.

DECLARE_OLECREATE 클래스 선언에 포함 되어 IMPLEMENT_OLECREATE 클래스 구현에 포함 되어야 합니다. DECLARE_OLECREATE를 사용 하 여 클래스 선언 DECLARE_DYNCREATE 또는 DECLARE_SERIAL 사용 해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE

이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) 사용 하는 모든 클래스의 구현 파일에 표시 되어야 `DECLARE_OLECREATE`합니다.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*external_name*<br/>
(인용 부호 안에 포함 됨) 다른 응용 프로그램에 노출 되는 개체 이름입니다.

*l*, *w1*를 *w2*를 *b1*를 *b2*를 *b3*, *b4* 를 *b5*를 *b6*를 *b7*를 *b 8* 클래스의 CLSID의 구성 요소입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  기본적으로 IMPLEMENT_OLECREATE를 사용 하는 경우 스레딩 모델에만 지원 합니다. IMPLEMENT_OLECREATE_FLAGS를 사용 하는 경우에 개체에서 사용 하 여 스레딩 모델을 지정할 수 있습니다 합니다 *nFlags* 매개 변수입니다.

External name에 다른 응용 프로그램에 노출 된 식별자입니다. 클라이언트 응용 프로그램에서는 외부 이름을 사용 하 여 자동화 서버에서이 클래스의 개체를 요청 합니다.

OLE 클래스 ID가 고유 128 비트 식별자 개체입니다. 하나 이루어져 **긴**, 두 개의 **WORD**및 8 **바이트**s에 의해 표시 된 대로 *l*를 *w1*, *w2*, 및 *b1* 를 통해 *b 8* 구문 설명에서 합니다. 응용 프로그램 마법사 및 코드 마법사를 필요에 따라 고유한 OLE 클래스 Id를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[MFC 공용 컨트롤 라이브러리 격리](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID 키](/windows/desktop/com/clsid-key-hklm)
