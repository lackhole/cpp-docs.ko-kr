---
title: MFC에서 사용하는 콜백 함수
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 84581a4a1147a5b0b046e1bf2fbe412bffe9c662
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65612243"
---
# <a name="callback-functions-used-by-mfc"></a>MFC에서 사용하는 콜백 함수

Microsoft Foundation Class 라이브러리에 세 개의 콜백 함수가 나타납니다. 이러한 콜백 함수에 전달 되 [cdc:: enumobjects](../../mfc/reference/cdc-class.md#enumobjects)하십시오 [cdc:: graystring](../../mfc/reference/cdc-class.md#graystring), 및 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)합니다. 콜백 경계를 넘어 예외를 throw 할 수 없습니다 때문에 Windows를 반환 하기 전에 모든 콜백 함수가 MFC 예외를 트래핑 해야 하는 참고 합니다. 예외에 대 한 자세한 내용은 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.

|이름||
|----------|-----------------|
|[CDC::EnumObjects에 대한 콜백 함수](#enum_objects)||
|[CDC::GrayString에 대한 콜백 함수](#graystring)||
|[CDC::SetAbortProc에 대한 콜백 함수](#setabortproc)||

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="enum_objects"></a> Cdc:: enumobjects에 대 한 콜백 함수

합니다 *ObjectFunc* 이름은 응용 프로그램 제공 함수 이름의 자리 표시자입니다.

### <a name="syntax"></a>구문

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>매개 변수

*lpszLogObject*<br/>
가리키는 [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen) 하거나 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 개체의 논리적 특성에 대 한 정보를 포함 하는 데이터 구조입니다.

*lpData*<br/>
응용 프로그램에서 제공한 데이터를 가리킵니다. 전달 된 `EnumObjects` 함수입니다.

### <a name="return-value"></a>반환 값

콜백 함수에서 반환 된 **int**합니다. 이 반환 값은 사용자 정의입니다. 콜백 함수가 0을 반환 하는 경우 `EnumObjects` 열거형 조기에 중지 됩니다.

### <a name="remarks"></a>설명

실제 이름을 내보내야 합니다.

## <a name="graystring"></a>  Cdc:: graystring에 대 한 콜백 함수

*OutputFunc* 응용 프로그램에서 제공한 콜백 함수 이름에 대 한 자리 표시자입니다.

### <a name="syntax"></a>구문

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>매개 변수

*hDC*<br/>
최소한의 비트맵을 사용 하 여 메모리 장치 컨텍스트를 식별 너비와 높이 지정 된 `nWidth` 하 고 `nHeight` 에 `GrayString`입니다.

*lpData*<br/>
그릴 문자열을 가리킵니다.

*nCount*<br/>
출력에 문자 수를 지정 합니다.

### <a name="return-value"></a>반환 값

콜백 함수의 반환 값 TRUE 성공을 나타내려면를 해야 합니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

콜백 함수 (*OutputFunc*) (0, 0) 좌표를 기준으로 이미지를 그리기 해야 대신 (*x*에 *y*).

## <a name="setabortproc"></a>  Cdc:: setabortproc에 대 한 콜백 함수

이름을 *AbortFunc* 응용 프로그램 제공 함수 이름에 대 한 자리 표시자입니다.

### <a name="syntax"></a>구문

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>매개 변수

*hPr*<br/>
장치 컨텍스트를 식별합니다.

*코드*<br/>
오류가 발생 했는지 여부를 지정 합니다. 오류가 발생 하지 않은 경우 0입니다. 이 경우 SP_OUTOFDISK 인쇄 관리자의 현재 디스크 공간이 부족 하 고 더 많은 디스크 공간을 사용할 수 있게 됩니다 응용 프로그램이 대기 하는 경우입니다. 하는 경우 *코드* SP_OUTOFDISK에는 응용 프로그램에서 인쇄 작업을 중단할 필요가 없습니다. 호출 하 여 인쇄 관리자를 생성 해야 표시 되지 않는 경우는 `PeekMessage` 또는 `GetMessage` Windows 함수입니다.

### <a name="return-value"></a>반환 값

중단-처리기 함수의 반환 값은 인쇄 작업을 계속 하려면 이면 0이 아닌 값 및 0 취소 되 면 합니다.

### <a name="remarks"></a>설명

실제 이름을의 설명 섹션에 설명 된 대로 내보내야 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)합니다.

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)
