---
title: CRichEditCntrItem 클래스
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: 674937df9b4ecef0d159a47a45a716d1175ad5d9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773842"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem 클래스

사용 하 여 [CRichEditView](../../mfc/reference/cricheditview-class.md) 하 고 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.

## <a name="syntax"></a>구문

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|`CRichEditCntrItem` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|다른 형식으로 항목을 활성화합니다.|

## <a name="remarks"></a>설명

"Rich edit 컨트롤"에 사용자 입력 수 및 텍스트를 편집 하는 창입니다. 텍스트 문자와 단락 형식을 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트 서식 지정에 대 한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 서식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.

`CRichEditView` 텍스트 및 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc` 보기에는 OLE 클라이언트 항목 목록을 유지 관리 합니다. `CRichEditCntrItem` 컨테이너 쪽 OLE 클라이언트 항목에 대 한 액세스를 제공합니다.

이 Windows 공용 컨트롤 (및 따라서 합니다 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.

서식 있는 편집 컨테이너 항목을 사용 하 여 MFC 응용 프로그램에서 예제를 참조 합니다 [워드 패드](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxrich.h

##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem

이 함수 만들기를 호출을 `CRichEditCntrItem` 개체 및 컨테이너 문서에 추가 합니다.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>매개 변수

*preo*<br/>
에 대 한 포인터를 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE 항목을 설명 하는 구조입니다. 새 `CRichEditCntrItem` 이 OLE 항목 주위에 개체 생성 합니다. 하는 경우 *preo* 가 null 인 경우 클라이언트 항목이 비어 있습니다.

*pContainer*<br/>
이 항목을 포함 하는 컨테이너 문서에 대 한 포인터입니다. 하는 경우 *pContainer* 가 null 인 경우 명시적으로 호출 해야 [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) 문서에이 클라이언트 항목을 추가 합니다.

### <a name="remarks"></a>설명

이 함수는 모든 OLE 초기화를 수행 하지 않습니다.

자세한 내용은 참조는 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Windows SDK에는 구조입니다.

##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject

장치 측면을 동기화 하려면이 함수를 호출 [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect),이 `CRichEditCntrltem` 에 지정 된 *reo*합니다.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>매개 변수

*reo*<br/>
에 대 한 참조를 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE 항목을 설명 하는 구조입니다.

### <a name="remarks"></a>설명

자세한 내용은 [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 워드 패드](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc 클래스](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)
