---
title: CMFCAcceleratorKey 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: 6a99ad00a43ac7912320ee469d542b6bf9cca3de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403960"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey 클래스

가상 키 매핑 및 서식을 구현 하는 도우미 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|`CMFCAcceleratorKey` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCAcceleratorKey::Format](#format)|가속 구조 시각적 표현으로 변환합니다.|
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|설정에 대 한 바로 가기 키를 `CMFCAcceleratorKey` 개체입니다.|

## <a name="remarks"></a>설명

액셀러레이터 키가 바로 가기 키 라고도 합니다. 사용자가 입력 하는 바로 가기 키를 표시 하려는 경우는 [CMFCAcceleratorKeyAssignCtrl 클래스](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 맵 바로 가기 키, Alt + Shift + S와 같은 "Alt + Shift + S"와 같은 사용자 지정 텍스트 형식으로 합니다. 각 `CMFCAcceleratorKey` 개체를 텍스트 형식으로 단일 바로 가기 키를 매핑합니다.

바로 가기 키 및 액셀러레이터 키 테이블을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)합니다.

## <a name="example"></a>예제

다음 예제에는 생성 하는 방법을 보여 줍니다.는 `CMFCAcceleratorKey` 개체 및 사용 방법은 해당 `Format` 메서드.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>요구 사항

**헤더:** afxacceleratorkey.h

##  <a name="cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey

생성 된 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체입니다.

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>매개 변수

*lpAccel*<br/>
[in] 바로 가기 키에 대 한 포인터입니다.

### <a name="remarks"></a>설명

만들 때 바로 가기 키를 제공 하지 않으면를 `CMFCAccleratorKey`를 사용 하 여는 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) 사용 하 여 바로 가기 키를 연결 하는 방법에 `CMFCAcceleratorKey` 개체.

##  <a name="format"></a>  CMFCAcceleratorKey::Format

가속 구조를 연결 된 문자열 값으로 변환합니다.

```
void Format(CString& str) const;
```

### <a name="parameters"></a>매개 변수

*str*<br/>
[out] 에 대 한 참조를 `CString` 메서드 번역 된 바로 가기 키를 기록 하는 위치 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 문자열 형식의 연결 된 바로 가기 키를 검색합니다. 문자열 형식의 설정할 수 있습니다는 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 생성자 또는 메서드를 사용 하 여 개체 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator)합니다.

##  <a name="setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator

에 대 한 바로 가기 키를 설정 합니다 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 개체입니다.

```
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>매개 변수

*lpAccel*<br/>
[in] 바로 가기 키에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 설정에 대 한 바로 가기 키를 `CMFCAcceleratorKey` 만들었을 때 바로 가기 키를 제공 하지 않았습니다를 `CMFCAcceleratorKey`.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)
