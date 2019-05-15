---
title: MFC 클래스 개체의 형식 캐스팅
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: c7586f3c3f3aefd78fa868cc847df27e8aac58ab
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611654"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC 클래스 개체의 형식 캐스팅

형식 캐스팅 매크로 또는 캐스팅 법적 인지 확인 하지 않고 특정 클래스의 개체를 가리키는 포인터에 대 한 지정 된 포인터를 캐스팅 하는 방법을 제공 합니다.

다음 표에서 MFC 형식 캐스팅 매크로 나열 합니다.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC 클래스 개체에 대 한 포인터를 캐스팅 하는 매크로

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|캐스팅 법적 인지를 확인 하는 동안 클래스 개체에 대 한 포인터에 대 한 포인터를 캐스팅 합니다.|
|[STATIC_DOWNCAST](#static_downcast)|관련 형식에 대 한 포인터를 하나의 클래스에서 개체에 대 한 포인터를 캐스팅합니다. 개체가 없는 경우 디버그 빌드에서 어설션을 사용 하면를 "일종의" 대상 형식입니다.|

##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST

캐스팅 법적 인지를 확인 하는 동안 클래스 개체에 대 한 포인터에 대 한 포인터를 캐스팅할 편리한 방법을 제공 합니다.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>매개 변수

*class*<br/>
클래스의 이름입니다.

*pointer*<br/>
형식의 개체에 대 한 포인터로 캐스팅할 수에 대 한 포인터 *클래스*합니다.

### <a name="remarks"></a>설명

매크로 캐스트를 *포인터* 매개 변수 개체에 대 한 포인터를 합니다 *클래스* 매개 변수의 형식입니다.

포인터에 의해 참조 되는 개체가 있는 경우는 식별 된 클래스가 "일종의" 매크로 적절 한 포인터를 반환 합니다. 유효한 캐스트 없으면 매크로 NULL을 반환 합니다.

##  <a name="static_downcast"></a>  STATIC_DOWNCAST

캐스트 *pobject* 에 대 한 포인터는 *class_name* 개체입니다.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
로 캐스팅 되 고 클래스의 이름입니다.

*pobject*<br/>
에 대 한 포인터로 캐스팅할 수에 대 한 포인터를 *class_name* 개체입니다.

### <a name="remarks"></a>설명

*pobject* NULL 이거나 직접 파생 된 클래스 또는 간접적으로 개체를 가리키므로 *class_name*합니다. 빌드에서 _DEBUG 전처리기 기호 정의 사용 하 여 응용 프로그램의 경우 매크로 ASSERT는 *pobject* 가 NULL이 아닌 개체를 가리키는 경우 또는 "일종의"에 지정 된 클래스를 *class_name*매개 변수 (참조 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). 이외에 **_DEBUG** 매크로 빌드 형식 검사 없이 캐스팅을 수행 합니다.

에 지정 된 클래스는 *class_name* 매개 변수에서 파생 되어야 합니다 `CObject` 는 DECLARE_DYNAMIC IMPLEMENT_DYNAMIC는 DECLARE_DYNCREATE 및 IMPLEMENT_DYNCREATE, 또는 DECLARE_SERIAL 및 IMPLEMENT_ 사용 해야 합니다 이 문서에 설명 된 직렬 매크로로 [CObject 클래스: CObject에서 클래스 파생 시키기](../../mfc/deriving-a-class-from-cobject.md)합니다.

예를 들어,에 대 한 포인터를 캐스팅할 수 있습니다 `CMyDoc`라는 `pMyDoc`에 대 한 포인터로 `CDocument` 이 식을 사용 하 여:

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

하는 경우 `pMyDoc` 에서 직접 또는 간접적으로 파생 된 개체를 가리키지 않습니다 `CDocument`, 매크로 어설션 됩니다.

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
