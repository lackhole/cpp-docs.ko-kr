---
title: CMFCRibbonUndoButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: cd657ac035c004e7aa9bfcd2f6dbd2f3c90da80c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410094"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton 클래스

`CMFCRibbonUndoButton` 최신 사용자 명령을 포함 하는 드롭다운 목록에서 단추를 구현 하는 클래스입니다. 사용자는 다시 실행 하거나 해당 변경 내용을 취소 하려면 드롭다운 목록에서 가장 최근 명령 중 하나 이상을 선택할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|새 `CMFCRibbonUndoButton` 지정 하는 명령 ID, 텍스트 레이블 및 부모 개체의 이미지 목록에서 이미지를 사용 하 여 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|작업 목록에 새 작업을 추가합니다.|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|드롭다운 목록에는 작업 목록을 지웁니다.|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|사용자가 선택한 드롭다운 목록에서 항목 수를 결정 합니다.|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|개체는 메뉴에 포함 되는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

`CMFCRibbonUndoButton` 클래스는 스택을 드롭 다운 목록을 나타내는 데 사용 합니다.

## <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCRibbonUndoButton` 클래스 및 동작의 목록에 새 작업을 추가 합니다. 이 코드 조각은의 일부인 합니다 [리본 가젯 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonundobutton.h

##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction

작업 목록에 새 작업을 추가합니다.

```
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
[in] 드롭다운 목록에서 표시할 작업 레이블.

##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList

드롭다운 목록에는 작업 목록을 지웁니다.

```
void CleanUpUndoList();
```

##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton

새 `CMFCRibbonUndoButton` 지정 하는 명령 ID, 텍스트 레이블 및 부모 개체의 이미지 목록에서 이미지를 사용 하 여 개체입니다.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 명령 식별자를 지정합니다.

*lpszText*<br/>
[in] 단추의 텍스트 레이블을 지정합니다.

*nSmallImageIndex*<br/>
[in] 단추의 작은 이미지에 대 한 부모 개체의 이미지 목록에서 0부터 시작 인덱스입니다.

*nLargeImageIndex*<br/>
[in] 인덱스에 대 한 부모 개체의 이미지 목록에서를 단추의 큰 이미지입니다.

*hIcon*<br/>
[in] 단추의 이미지로 사용할 수 있는 아이콘에 대 한 핸들입니다.

##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber

사용자가 선택한 드롭다운 목록에서 항목 수를 결정 합니다.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>반환 값

사용자가 선택한 항목의 수입니다.

##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu

개체는 메뉴에 포함 되는지 여부를 나타냅니다.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery 클래스](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
