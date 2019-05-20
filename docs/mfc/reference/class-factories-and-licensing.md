---
title: 클래스 팩터리 및 라이선스
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: 18d86122e57af056a50a4d94bac89d65a7b71c7d
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611847"
---
# <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스

OLE 컨트롤의 인스턴스를 만들려면 컨테이너 응용 프로그램을 컨트롤의 클래스 팩터리의 멤버 함수를 호출 합니다. 컨트롤의 실제 OLE 개체 이기 때문에 클래스 팩토리는 컨트롤의 인스턴스를 만드는 하는 일을 담당 합니다. 모든 OLE 컨트롤 클래스는 클래스 팩터리를 가져야 합니다.

OLE 컨트롤의 또 다른 중요 한 기능 라이선스를 적용 하는 기능은 해당 합니다. 컨트롤을 사용 하면 컨트롤 프로젝트를 만드는 동안 라이선스를 통합할 수 있습니다. 컨트롤 라이선스에 대 한 자세한 내용은 문서를 참조 하세요. [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)합니다.

다음 표에서 몇 가지 매크로 및 함수를 선언 하 고 컨트롤의 클래스 팩터리를 구현 하는 데 사용 하는 컨트롤의 라이선스.

### <a name="class-factories-and-licensing"></a>클래스 팩터리 및 라이선스

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE 컨트롤 또는 속성 페이지 클래스 팩터리를 선언합니다.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|컨트롤의 구현 `GetClassID` 함수 및 클래스 팩터리 인스턴스를 선언 합니다.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|모든 라이선스 함수 선언의 시작합니다.|
|[END_OLEFACTORY](#end_olefactory)|모든 라이선스 함수 선언의 종료 됩니다.|
|[AfxVerifyLicFile](#afxverifylicfile)|컨트롤을 특정 컴퓨터에서 사용 하도록 허가 되어 있는지 여부를 확인 합니다.|

##  <a name="declare_olecreate_ex"></a>  DECLARE_OLECREATE_EX

클래스 팩터리를 선언 및 `GetClassID` 컨트롤 클래스의 멤버 함수입니다.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

라이선스를 지원 하지 않는 컨트롤에 대 한 컨트롤 클래스 헤더 파일에서이 매크로 사용 합니다.

이 매크로 다음 코드 샘플과 동일한 용도로 사용 하는 참고 합니다.

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="implement_olecreate_ex"></a>  IMPLEMENT_OLECREATE_EX

컨트롤의 클래스 팩터리를 구현 하며 [가 Classid](../../mfc/reference/colecontrol-class.md#getclassid) 컨트롤 클래스의 멤버 함수입니다.

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 속성 페이지 클래스의 이름입니다.

*external_name*<br/>
응용 프로그램에 노출 하는 개체 이름입니다.

*l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*<br/>
클래스의 CLSID의 구성 요소입니다. 이러한 매개 변수에 대 한 자세한 내용은 설명 부분을 참조 하세요 [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)합니다.

### <a name="remarks"></a>설명

이 매크로 DECLARE_OLECREATE_EX 매크로 또는 BEGIN_OLEFACTORY 및 END_OLEFACTORY 매크로 사용 하는 모든 컨트롤 클래스의 구현 파일에 나타나야 합니다. External name에 다른 응용 프로그램에 노출 되는 OLE 컨트롤의 식별자입니다. 컨테이너에서는이 이름을 사용 하 여이 컨트롤 클래스의 개체를 요청 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="begin_olefactory"></a>  BEGIN_OLEFACTORY

컨트롤 클래스의 헤더 파일에서 클래스 팩터리의 선언을 시작합니다.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
이 해당 클래스 팩터리 컨트롤 클래스의 이름을 지정 합니다.

### <a name="remarks"></a>설명

BEGIN_OLEFACTORY 직후 클래스 팩터리 함수를 라이선스의 선언 해야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="end_olefactory"></a>  END_OLEFACTORY

컨트롤의 클래스 팩터리 선언의 종료 됩니다.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
이 해당 클래스 팩터리 컨트롤 클래스의 이름입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="afxverifylicfile"></a>  AfxVerifyLicFile

라이선스 파일에서 명명 된를 확인 하려면이 함수를 호출 `pszLicFileName` OLE 컨트롤에 대 한 유효 합니다.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
사용이 허가 된 컨트롤과 연결 된 DLL의 인스턴스 핸들입니다.

*pszLicFileName*<br/>
라이선스 파일을 포함 하는 null로 끝나는 문자열을 가리킵니다.

*pszLicFileContents*<br/>
라이선스 파일의 시작 부분에서 찾을 시퀀스를 일치 해야 하는 바이트 시퀀스를 가리킵니다.

*cch*<br/>
문자 수가 *pszLicFileContents*합니다.

### <a name="return-value"></a>반환 값

라이선스 파일이 있고에서 문자 시퀀스를 시작 하는 경우 0이 아닌 *pszLicFileContents*그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

하는 경우 *cch* 가-1 이면이 함수를 사용 합니다.

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
