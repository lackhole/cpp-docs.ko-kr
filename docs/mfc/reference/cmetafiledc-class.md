---
title: CMetaFileDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
ms.openlocfilehash: 95f54f50d7a87e9a2ad4689c14f3b7f8d42ff71e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403947"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC 클래스

원하는 이미지 또는 텍스트를 만들기 위해 재생할 수 있는 GDI(그래픽 디바이스 인터페이스) 명령 시퀀스가 포함된 Windows 메타파일을 구현합니다.

## <a name="syntax"></a>구문

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|`CMetaFileDC` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMetaFileDC::Close](#close)|장치 컨텍스트를 닫고 메타 파일 핸들을 만듭니다.|
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|확장 메타 파일 장치 컨텍스트를 닫고 확장 메타 파일 핸들을 만듭니다.|
|[CMetaFileDC::Create](#create)|Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 `CMetaFileDC` 개체입니다.|
|[CMetaFileDC::CreateEnhanced](#createenhanced)|향상 된 형식 메타 파일에 대 한 메타 파일 장치 컨텍스트를 만듭니다.|

## <a name="remarks"></a>설명

Windows 메타 파일을 구현 하려면 먼저 만듭니다는 `CMetaFileDC` 개체입니다. 호출를 `CMetaFileDC` 생성자를 호출 합니다 [만들기](#create) Windows 메타 파일 장치 컨텍스트를 만들고에 연결 하는 멤버 함수를 `CMetaFileDC` 개체.

다음 보내기는 `CMetaFileDC` 재생 되도록 하려는 CDC GDI 명령 시퀀스는 개체입니다. 와 같은 출력을 만든 GDI 명령만 `MoveTo` 고 `LineTo`를 사용할 수 있습니다.

메타 파일에 원하는 명령을 보낸 후에 호출 하 여 `Close` 메타 파일 장치 컨텍스트를 닫고 메타 파일 핸들을 반환 하는 멤버 함수입니다. 그런 다음 삭제를 `CMetaFileDC` 개체입니다.

[CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) 메타 파일 핸들을 반복적으로 메타 파일을 재생 하는 데 사용할 수 있습니다. 메타 파일 조작할 수도 있습니다 Windows 함수에서와 같은 [CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea)를 디스크에 메타 파일을 복사 합니다.

메타 파일은 더 이상 필요 없는 사용 하 여 메모리에서 삭제 합니다 [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) Windows 함수입니다.

구현할 수도 있습니다는 `CMetaFileDC` 개체를 처리할 수 있도록 둘 다 호출 출력 같은 GDI 호출 특성 `GetTextExtent`합니다. 이러한 메타 파일은 보다 유연 하 고 더 쉽게 다시 사용할 수 종종 출력 및 특성에 대 한 호출의 조합으로 구성 된 일반 GDI 코드입니다. 합니다 `CMetaFileDC` 클래스는 두 개의 장치 컨텍스트를 상속 `m_hDC` 고 `m_hAttribDC`, CDC에서. `m_hDC` 장치 컨텍스트 모두 처리 [CDC](../../mfc/reference/cdc-class.md) GDI 출력 호출 및 `m_hAttribDC` 장치 컨텍스트는 모든 CDC GDI 특성 호출을 처리 합니다. 일반적으로 이러한 두 장치 컨텍스트는 동일한 장치를 참조 하십시오. 경우 `CMetaFileDC`, DC 특성은 기본적으로 NULL로 설정 됩니다.

화면, 프린터 또는 장치를 메타 파일 이외의 가리키는 호출 하는 두 번째 장치 컨텍스트를 생성 합니다 `SetAttribDC` 멤버 함수를 사용 하 여 새 장치 컨텍스트 연결 `m_hAttribDC`. 정보에 대 한 GDI 호출 리디렉션됩니다 새 `m_hAttribDC`합니다. 출력 GDI 호출 이동 `m_hDC`, 메타 파일을 나타냅니다.

에 대 한 자세한 `CMetaFileDC`를 참조 하세요 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="close"></a>  CMetaFileDC::Close

메타 파일 장치 컨텍스트를 닫고를 사용 하 여 메타 파일을 재생 하는 데 사용할 수 있는 Windows 메타 파일 핸들을 만듭니다는 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) 멤버 함수입니다.

```
HMETAFILE Close();
```

### <a name="return-value"></a>반환 값

함수가 성공할 경우에 유효한 HMETAFILE 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

와 같은 Windows 함수를 사용 하 여 메타 파일을 조작 하 Windows 메타 파일 핸들을 사용할 수도 있습니다 [CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea)합니다.

Windows를 호출 하 여 메타 파일 사용 후 삭제 [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) 함수입니다.

##  <a name="closeenhanced"></a>  CMetaFileDC::CloseEnhanced

확장 메타 파일 장치 컨텍스트를 닫고 확장 형식 메타 파일을 식별 하는 핸들을 반환 합니다.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>반환 값

확장된 메타 파일, 성공할 경우 핸들을 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

응용 프로그램이이 함수에 의해 반환 되는 확장 메타 파일 핸들을 사용 하 여 다음 작업을 수행할 수 있습니다.

- 확장된 메타 파일에 저장 된 그림을 표시

- 확장된 메타 파일의 복사본 만들기

- 열거, 편집 또는 개별 레코드 확장된 메타 파일에 복사

- 확장 메타 파일 헤더에서 메타 파일 내용에 대 한 설명을 검색합니다

- 확장 메타 파일 헤더의 복사본을 검색

- 확장된 메타 파일의 이진 복사본을 검색

- 선택적 색상표의 색을 열거

- 향상 된 형식 메타 파일 형식을 Windows 메타 파일 변환

Win32를 호출 하 여 핸들을 해제 해야 응용 프로그램에서 확장된 메타 파일 핸들을 더 이상 필요한 경우 `DeleteEnhMetaFile` 함수입니다.

##  <a name="cmetafiledc"></a>  CMetaFileDC::CMetaFileDC

생성 된 `CMetaFileDC` 두 단계로 개체입니다.

```
CMetaFileDC();
```

### <a name="remarks"></a>설명

첫째, 호출 `CMetaFileDC`, 호출 `Create`, Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 `CMetaFileDC` 개체입니다.

##  <a name="create"></a>  CMetaFileDC::Create

생성 된 `CMetaFileDC` 두 단계로 개체입니다.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFilename*<br/>
Null로 끝나는 문자열을 가리킵니다. 만들려는 메타 파일의 파일 이름을 지정 합니다. 하는 경우 *lpszFilename* 가 null 인 경우 새 메모리 내 메타 파일 생성 됩니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

먼저 생성자를 호출 `CMetaFileDC`, 다음 호출 `Create`, Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 `CMetaFileDC` 개체입니다.

##  <a name="createenhanced"></a>  CMetaFileDC::CreateEnhanced

향상 된 형식 메타 파일에 대 한 장치 컨텍스트를 만듭니다.

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>매개 변수

*pDCRef*<br/>
확장된 메타 파일에 대 한 참조 장치를 식별합니다.

*lpszFileName*<br/>
Null로 끝나는 문자열을 가리킵니다. 만들려는 확장된 메타 파일의 파일 이름을 지정 합니다. 확장된 메타 파일 메모리 기반 이며 손실 또는 경우는 개체가 소멸 될 때 해당 내용을이 매개 변수가 NULL 인 경우 Win32 `DeleteEnhMetaFile` 함수를 호출 합니다.

*lpBounds*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 데이터 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) HIMETRIC 단위 (.01 밀리미터 단위로) 그림의 확장된 메타 파일에 저장 될 크기를 지정 하는 개체입니다.

*lpszDescription*<br/>
그림의 제목 뿐만 아니라 그림을 생성 한 응용 프로그램의 이름을 지정 하는 0으로 끝나는 문자열을 가리킵니다.

### <a name="return-value"></a>반환 값

확장된 메타 성공할 경우이 파일에 대 한 장치 컨텍스트의 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 DC 장치 독립적인 그림을 저장할 수 있습니다.

로 식별 되는 참조 장치를 사용 하는 Windows를 *pDCRef* 매개 변수를 확인 및 단위를 그림 처음 표시 되는 장치를 기록 합니다. 경우는 *pDCRef* 매개 변수가 NULL 이면 현재 디스플레이 장치를 사용 하 여 참조 합니다.

왼쪽 및 위쪽 멤버를 `RECT` 가리키는 데이터 구조는 *lpBounds* 매개 변수 각각, 오른쪽 및 아래쪽 구성원 보다 작거나 같아야 합니다. 사각형의 가장자리 점 그림에 포함 됩니다. 하는 경우 *lpBounds* 가 null 인 경우는 GDI (그래픽 장치 인터페이스) 응용 프로그램을 그린 그림이 묶을 수 있는 가장 작은 사각형의 크기를 계산 합니다. 합니다 *lpBounds* 가능한 경우 매개 변수를 제공 해야 합니다.

가리키는 문자열을 *lpszDescription* 매개 변수는 응용 프로그램 이름과 그림 사이 null 문자가 있어야 하며 두 null 문자로 종료 해야 합니다-예를 들어, "XYZ 그래픽 Editor\0Bald Eagle\0\0, "\0 나타냅니다 null 문자. 하는 경우 *lpszDescription* 가 null 인 경우 확장 메타 파일 헤더에 해당 항목이 없습니다.

응용 프로그램 확장된 메타 파일에 그래픽 그림을 저장 하려면이 함수에 의해 생성 된 DC를 사용 합니다. 이 DC를 식별 하는 핸들 GDI 함수를 전달할 수 있습니다.

응용 프로그램 그림 메타 파일에서에 저장 한 후 표시할 수 그림 모든 출력 장치에서 호출 하 여는 `CDC::PlayMetaFile` 함수입니다. Windows에서 가리키는 사각형 그림을 표시할 때 사용 합니다 *lpBounds* 매개 변수 및 배치 하 고 그림 확장 참조 장치에서 확인 데이터입니다. 이 함수에서 반환 된 장치 컨텍스트는 모든 새 DC와 사용 하 여 연결 된 동일한 기본 특성을 포함 합니다.

응용 프로그램에서 Win32를 사용 해야 `GetWinMetaFileBits` 확장된 메타 파일에서 이전 Windows 메타 파일 형식으로 변환 하는 함수입니다.

확장된 메타 파일의 파일 이름을 사용 해야 합니다. EMF 확장입니다.

## <a name="see-also"></a>참고자료

[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
