---
title: CDocItem 클래스
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 6c1c1da14d732b6aff6ae07f86ae7b9c1b690b84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168195"
---
# <a name="cdocitem-class"></a>CDocItem 클래스

문서 데이터의 구성 요소로, 문서 항목에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDocItem::GetDocument](#getdocument)|항목을 포함 하는 문서를 반환 합니다.|
|[CDocItem::IsBlank](#isblank)|항목 정보를 포함 하는지 여부를 결정 합니다.|

## <a name="remarks"></a>설명

`CDocItem` 개체는 클라이언트와 서버 문서의 OLE 항목을 나타내는 데 사용 됩니다.

자세한 내용은 문서를 참조 하세요. [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="getdocument"></a>  CDocItem::GetDocument

항목을 포함 하는 문서를 가져오려면이 함수를 호출 합니다.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>반환 값

항목을 포함 하는 문서에 대 한 포인터 항목이 문서의 일부가 아닌 경우 NULL입니다.

### <a name="remarks"></a>설명

이 함수는 파생된 클래스에서 재정의 되 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 하 고 [COleServerItem](../../mfc/reference/coleserveritem-class.md), 포인터를 반환 하는 [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), 또는 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 개체입니다.

##  <a name="isblank"></a>  CDocItem::IsBlank

기본 serialization이 수행 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 항목 정보가 들어 있지 않습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본적으로 `CDocItem` 개체는 빈 되지 않습니다. [COleClientItem](../../mfc/reference/coleclientitem-class.md) 에서 직접 파생 되므로 개체는 비어 있는 경우에 따라 `CDocItem`합니다. 그러나 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체는 항상 비어 있습니다. 기본적으로 포함 된 OLE 응용 프로그램 `COleClientItem` x 또는 y 없는 개체 범위 serialize 됩니다. 재정의에서 TRUE를 반환 하 여 이렇게 `IsBlank` 항목에 x 또는 y 범위입니다.

직렬화 하는 동안 다른 작업을 구현 하려는 경우이 함수를 재정의 합니다.

## <a name="see-also"></a>참고자료

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDocument 클래스](../../mfc/reference/coledocument-class.md)<br/>
[COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)<br/>
[COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)
