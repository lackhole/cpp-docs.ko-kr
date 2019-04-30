---
title: CHtmlEditDoc 클래스
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: c2a00b2501647f6101fed8ed1d4cd23dad7ab209
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346182"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc 클래스

사용 하 여 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), MFC 문서 뷰 아키텍처 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공 합니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|`CHtmlEditDoc` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|검색 된 `CHtmlEditView` 이 문서에 연결 된 개체입니다.|
|[CHtmlEditDoc::IsModified](#ismodified)|사용자가 수정 된 문서 관련된 보기의 WebBrowser 컨트롤에 포함 되는지 여부를 반환 합니다.|
|[CHtmlEditDoc::OpenURL](#openurl)|URL을 엽니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxhtml.h

##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc

`CHtmlEditDoc` 개체를 생성합니다.

```
CHtmlEditDoc();
```

##  <a name="getview"></a>  CHtmlEditDoc::GetView

검색 된 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) 이 문서에 연결 된 개체입니다.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>반환 값

문서에 대 한 포인터를 반환 합니다. `CHtmlEditView` 개체입니다.

##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified

사용자가 수정 된 문서 관련된 보기의 WebBrowser 컨트롤에 포함 되는지 여부를 반환 합니다.

```
virtual BOOL IsModified();
```

##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL

URL을 엽니다.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
열려는 URL입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

## <a name="see-also"></a>참고자료

[HTMLEdit 샘플](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
