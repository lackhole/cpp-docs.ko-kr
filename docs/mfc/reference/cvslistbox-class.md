---
title: CVSListBox 클래스
ms.date: 11/19/2018
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
ms.openlocfilehash: 618f4f386db477dd301ada862ebd2094a6c6651f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324446"
---
# <a name="cvslistbox-class"></a>CVSListBox 클래스

`CVSListBox` 클래스는 편집할 수 있는 목록 컨트롤을 지원 합니다.

## <a name="syntax"></a>구문

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CVSListBox::CVSListBox](#cvslistbox)|`CVSListBox` 개체를 생성합니다.|
|`CVSListBox::~CVSListBox`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CVSListBox::AddItem](#additem)|목록 컨트롤에 문자열을 추가 합니다. ( `CVSListBoxBase::AddItem`을 재정의합니다.)|
|[CVSListBox::EditItem](#edititem)|목록 컨트롤 항목의 텍스트에서 편집 작업을 시작 합니다. ( `CVSListBoxBase::EditItem`을 재정의합니다.)|
|[CVSListBox::GetCount](#getcount)|편집할 수 있는 목록 컨트롤에 문자열을 검색합니다. ( `CVSListBoxBase::GetCount`을 재정의합니다.)|
|[CVSListBox::GetItemData](#getitemdata)|편집할 수 있는 목록 컨트롤 항목을 사용 하 여 연결 하는 응용 프로그램별 32 비트 값을 검색 합니다. ( `CVSListBoxBase::GetItemData`을 재정의합니다.)|
|[CVSListBox::GetItemText](#getitemtext)|편집할 수 있는 목록 컨트롤 항목의 텍스트를 검색합니다. ( `CVSListBoxBase::GetItemText`을 재정의합니다.)|
|[CVSListBox::GetSelItem](#getselitem)|편집할 수 있는 목록 컨트롤에서 현재 선택된 된 항목의 인덱스를 검색합니다. ( `CVSListBoxBase::GetSelItem`을 재정의합니다.)|
|`CVSListBox::PreTranslateMessage`|디스패치 되기 전에 창 메시지를 변환 합니다 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 함수입니다. 자세한 내용 및 메서드 구문 참조 [cwnd:: Pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)합니다. ( `CVSListBoxBase::PreTranslateMessage`을 재정의합니다.)|
|[CVSListBox::RemoveItem](#removeitem)|편집할 수 있는 목록 컨트롤에서 항목을 제거 합니다. ( `CVSListBoxBase::RemoveItem`을 재정의합니다.)|
|[CVSListBox::SelectItem](#selectitem)|편집할 수 있는 목록 제어 문자열을 선택합니다. ( `CVSListBoxBase::SelectItem`을 재정의합니다.)|
|[CVSListBox::SetItemData](#setitemdata)|응용 프로그램별 32 비트 값을 편집할 수 있는 목록 컨트롤 항목을 사용 하 여 연결합니다. ( `CVSListBoxBase::SetItemData`을 재정의합니다.)|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|현재 포함 된 목록 뷰 컨트롤에 핸들을 반환합니다.|

## <a name="remarks"></a>설명

`CVSListBox` 클래스 사용자 만들기, 수정, 삭제 또는 목록 컨트롤에서 항목을 다시 정렬할 수 있는 편집 단추 집합을 제공 합니다.

다음은 편집할 수 있는 목록 컨트롤의 그림입니다. "Item2" 이라는 두 번째 목록 항목을 편집 하기 위해 선택 됩니다.

![CVSListBox 컨트롤](../../mfc/reference/media/cvslistbox.png "CVSListBox 컨트롤")

리소스 편집기를 사용 하 여 편집할 수 있는 목록 컨트롤을 추가 하는 경우 다음에 유의 합니다 **도구 상자** 편집기의 창 편집할 수 있는 미리 정의 된 목록 컨트롤을 제공 하지 않습니다. 대신,와 같은 정적 컨트롤을 추가 합니다 **그룹 상자** 제어 합니다. 프레임 워크를 사용 하면 자리 표시자로 정적 컨트롤을 사용 하는 크기 및 편집할 수 있는 목록 컨트롤의 위치 지정 합니다.

편집할 수 있는 목록 컨트롤을 대화 상자 템플릿에서 사용 하려면 선언 된 `CVSListBox` 대화 상자 클래스에서 변수입니다. 를 지원 하기 위해 변수와 컨트롤 간의 데이터 교환을 정의 `DDX_Control` 의 항목 매크로 `DoDataExchange` 대화 상자의 메서드. 기본적으로 편집할 수 있는 목록 컨트롤 편집 단추 없이 만들어집니다. 편집 단추를 사용 하도록 설정 하려면 상속 된 CVSListBoxBase::SetStandardButtons 메서드를 사용 합니다.

자세한 내용은 참조는 샘플 디렉터리는 `New Controls` Page3.cpp 파일과 Page3.h 샘플입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxvslistbox.h

##  <a name="additem"></a>  CVSListBox::AddItem

목록 컨트롤에 문자열을 추가 합니다.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*strIext*<br/>
[in] 문자열에 대 한 참조입니다.

*dwData*<br/>
[in] 문자열을 사용 하 여 연결 되는 응용 프로그램별 32 비트 값입니다. 기본값은 0입니다.

*iIndex*<br/>
[in] 문자열을 포함 하는 위치의 0부터 시작 하는 인덱스입니다. 경우는 *iIndex* 매개 변수가-1 이면 문자열이 목록의 끝에 추가 됩니다. 기본값은 -1입니다.

### <a name="return-value"></a>반환 값

목록 컨트롤에서 입력 문자열의 위치의 0부터 시작 하는 인덱스입니다.

### <a name="remarks"></a>설명

사용 하 여는 [CVSListBox::GetItemData](#getitemdata) 에 지정 된 값을 검색 하는 메서드는 *dwData* 매개 변수입니다. 이 값은 응용 프로그램별 정수 또는 기타 데이터에 대 한 포인터 수 있습니다.

##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox

`CVSListBox` 개체를 생성합니다.

```
CVSListBox();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="edititem"></a>  CVSListBox::EditItem

목록 컨트롤 항목의 텍스트에서 편집 작업을 시작 합니다.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 목록 컨트롤 항목의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

편집 작업을 성공적으로 시작 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

사용자는 항목의 레이블을 두 번 클릭 하거나 눌러 편집 작업을 시작 합니다 **F2** 또는 **스페이스바** 항목에 포커스가 있는 경우 키입니다.

##  <a name="getcount"></a>  CVSListBox::GetCount

편집할 수 있는 목록 컨트롤에 문자열을 검색합니다.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>반환 값

목록 컨트롤의 항목 수입니다.

### <a name="remarks"></a>설명

개수는 마지막 항목의 인덱스 값을 보다 하나 더 큰 인덱스는 0부터 시작 하므로 note 합니다.

##  <a name="getitemdata"></a>  CVSListBox::GetItemData

편집할 수 있는 목록 컨트롤 항목을 사용 하 여 연결 하는 응용 프로그램별 32 비트 값을 검색 합니다.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 편집할 수 있는 목록 컨트롤 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

지정 된 항목과 연결 된 32 비트 값입니다.

### <a name="remarks"></a>설명

사용 된 [CVSListBox::SetItemData](#setitemdata) 또는 [CVSListBox::AddItem](#additem) 목록 컨트롤 항목을 사용 하 여 32 비트 값을 연결 하는 방법입니다. 이 값은 응용 프로그램별 정수 또는 기타 데이터에 대 한 포인터 수 있습니다.

##  <a name="getitemtext"></a>  CVSListBox::GetItemText

편집할 수 있는 목록 컨트롤 항목의 텍스트를 검색합니다.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 편집할 수 있는 목록 컨트롤 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 지정된 된 항목의 텍스트가 포함 된 개체입니다.

### <a name="remarks"></a>설명

##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd

현재 포함 된 목록 뷰 컨트롤에 핸들을 반환합니다.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>반환 값

포함 된 목록 뷰 컨트롤에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 검색을 지 원하는 포함 된 목록 뷰 컨트롤에 대 한 핸들을 `CVSListBox` 클래스입니다.

##  <a name="getselitem"></a>  CVSListBox::GetSelItem

편집할 수 있는 목록 컨트롤에서 현재 선택된 된 항목의 인덱스를 검색합니다.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 현재 선택한 항목의 0부터 시작 인덱스 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

##  <a name="removeitem"></a>  CVSListBox::RemoveItem

편집할 수 있는 목록 컨트롤에서 항목을 제거 합니다.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 편집할 수 있는 목록 컨트롤 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 지정된 된 항목이 제거 됩니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="selectitem"></a>  CVSListBox::SelectItem

편집할 수 있는 목록 제어 문자열을 선택합니다.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
[in] 편집할 수 있는 목록 컨트롤 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 된 항목을 선택 하 고 필요한 경우 항목을 뷰로 스크롤합니다.

##  <a name="setitemdata"></a>  CVSListBox::SetItemData

응용 프로그램별 32 비트 값을 편집할 수 있는 목록 컨트롤 항목을 사용 하 여 연결합니다.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 편집할 수 있는 목록 컨트롤 항목의 0부터 시작 하는 인덱스입니다.

*dwData*<br/>
[in] 32 비트 값입니다. 이 값은 응용 프로그램별 정수 또는 기타 데이터에 대 한 포인터 수 있습니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
