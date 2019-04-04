---
title: CRichEditDoc 클래스
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: 4cc3af7649d30a153b67cd8269e595c11018833f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769793"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc 클래스

사용 하 여 [CRichEditView](../../mfc/reference/cricheditview-class.md) 하 고 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.

## <a name="syntax"></a>구문

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|문서의 정리를 수행 하기 위해 호출 됩니다.|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|스트림 입력 및 출력 서식 지정 정보를 포함 해야 하는지 여부를 나타냅니다.|
|[CRichEditDoc::GetView](#getview)|연결 된 검색 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|스트림 I/O 서식 지정이 포함 되는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

"Rich edit 컨트롤"에 사용자 입력 수 및 텍스트를 편집 하는 창입니다. 텍스트 문자와 단락 형식을 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트 서식 지정에 대 한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 서식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.

`CRichEditView` 텍스트 및 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc` 뷰에 클라이언트 항목 목록을 유지 관리 합니다. `CRichEditCntrItem` 컨테이너 쪽 OLE 클라이언트 항목에 대 한 액세스를 제공합니다.

이 Windows 공용 컨트롤 (및 따라서 합니다 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.

서식 있는 편집 문서를 사용 하 여 MFC 응용 프로그램에서 예제를 참조 합니다 [워드 패드](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxrich.h

##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem

이 함수 만들기를 호출을 `CRichEditCntrItem` 개체 및이 문서에 추가 합니다.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>매개 변수

*preo*<br/>
에 대 한 포인터를 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE 항목을 설명 하는 구조입니다. 새 `CRichEditCntrItem` 이 OLE 항목 주위에 개체 생성 합니다. 하는 경우 *preo* 가 null 인 경우 새 클라이언트 항목이 비어 있습니다.

### <a name="return-value"></a>반환 값

새에 대 한 포인터 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체는이 문서에 추가 되었습니다.

### <a name="remarks"></a>설명

이 함수는 모든 OLE 초기화를 수행 하지 않습니다.

자세한 내용은 참조는 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Windows SDK에는 구조입니다.

##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat

서식 있는 편집의 콘텐츠를 스트리밍에 대 한 텍스트 형식을 결정 하려면이 함수를 호출 합니다.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>반환 값

다음 플래그 중 하나입니다.

- SF_TEXT 나타냅니다는 다양 한 컨트롤을 편집 하는 경우에 서식 지정 정보를 유지 하지 않습니다.

- SF_RTF 나타냅니다 다양 한 컨트롤을 편집 하는 서식 지정 정보를 유지 관리.

### <a name="remarks"></a>설명

반환 값을 기반으로 합니다 [m_bRTF](#m_brtf) 데이터 멤버입니다. 경우에이 반환 SF_RTF `m_bRTF` TRUE이 고, 그렇지 않으면 SF_TEXT 합니다.

##  <a name="getview"></a>  CRichEditDoc::GetView

액세스 하려면이 함수를 호출 합니다 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체와 연결 된 `CRichEditDoc` 개체입니다.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CRichEditView` 문서와 연결 된 개체입니다.

### <a name="remarks"></a>설명

내에 포함 된 텍스트 및 서식 지정 정보를 `CRichEditView` 개체입니다. `CRichEditDoc` 개체 serialization에 대 한 OLE 항목을 유지 합니다. 하나만 있어야 `CRichEditView` 각각에 대해 `CRichEditDoc`합니다.

##  <a name="m_brtf"></a>  CRichEditDoc::m_bRTF

TRUE 인 경우 나타냅니다 [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) 하 고 [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) 단락 및 문자 형식을 특성에 저장 해야 합니다.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>참고자료

[MFC 샘플 워드 패드](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc 클래스](../../mfc/reference/coleserverdoc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem 클래스](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument 클래스](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl 클래스](../../mfc/reference/cricheditctrl-class.md)
