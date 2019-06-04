---
title: CImage 클래스
ms.date: 02/01/2018
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: 0b61d38d141392dc85a150ddd2caf50b28146ae7
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503166"
---
# <a name="cimage-class"></a>CImage 클래스

`CImage` 향상 된 비트맵 지원, 로드 및 JPEG, GIF, BMP, 및 PNG 이동식 네트워크 그래픽 () 형식 이미지를 저장 하는 기능을 포함 하 여 제공 합니다.

> [!IMPORTANT]
> 이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CImage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CImage::CImage](#cimage)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|투명 하거나 반투명 픽셀로 있는 비트맵을 표시 합니다.|
|[CImage::Attach](#attach)|연결에 HBITMAP를 `CImage` 개체입니다. 비 DIB 구역 비트맵 또는 DIB 구역 비트맵을 사용 하 여 사용할 수 있습니다.|
|[CImage::BitBlt](#bitblt)|현재이 장치 컨텍스트를 원본 장치 컨텍스트에서 비트맵을 복사 합니다.|
|[CImage::Create](#create)|DIB 구역을 비트맵을 만들고 이전에 생성 된 연결 `CImage` 개체입니다.|
|[CImage::CreateEx](#createex)|(사용 하 여 추가 매개 변수) DIB 구역을 비트맵을 만들고 이전에 생성 된 연결 `CImage` 개체입니다.|
|[CImage::Destroy](#destroy)|비트맵을 분리 합니다 `CImage` 개체 및 비트맵을 삭제 합니다.|
|[CImage::Detach](#detach)|비트맵의 분리는 `CImage` 개체입니다.|
|[CImage::Draw](#draw)|소스 사각형에서 대상 사각형으로 비트맵을 복사 합니다. `Draw` 확장 또는 필요한 경우 대상 사각형의 크기에 맞게 비트맵을 압축 하 고 투명 한 색 및 알파 혼합을 처리 합니다.|
|[CImage::GetBits](#getbits)|비트맵의 실제 픽셀 값에 대 한 포인터를 검색합니다.|
|[CImage::GetBPP](#getbpp)|픽셀당 비트를 검색합니다.|
|[CImage::GetColorTable](#getcolortable)|색상표에 있는 항목의 범위에서 빨간색, 녹색, 파란색 (RGB) 색 값을 검색합니다.|
|[CImage::GetDC](#getdc)|현재 비트맵을 선택 하는 장치 컨텍스트를 검색 합니다.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|사용 가능한 이미지 형식 및 해당 설명을 찾습니다.|
|[CImage::GetHeight](#getheight)|현재 픽셀 이미지의 높이 검색합니다.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|사용 가능한 이미지 형식 및 해당 설명을 찾습니다.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|색상표에 있는 항목의 최대 수를 검색 합니다.|
|[CImage::GetPitch](#getpitch)|현재 이미지 (바이트)에서의 피치를 검색합니다.|
|[CImage::GetPixel](#getpixel)|지정 된 픽셀의 색을 검색 *x* 하 고 *y*합니다.|
|[CImage::GetPixelAddress](#getpixeladdress)|지정된 된 픽셀의 주소를 검색 합니다.|
|[CImage::GetTransparentColor](#gettransparentcolor)|색상표에서 투명 한 색의 위치를 검색합니다.|
|[CImage::GetWidth](#getwidth)|현재 픽셀 이미지의 너비를 검색합니다.|
|[CImage::IsDIBSection](#isdibsection)|연결 된 비트맵이 DIB 구역을 인지 확인 합니다.|
|[CImage::IsIndexed](#isindexed)|비트맵의 색을 인덱싱된 팔레트에 매핑되는 것을 나타냅니다.|
|[CImage::IsNull](#isnull)|소스 비트맵을 현재 로드 된 경우를 나타냅니다.|
|[CImage::IsTransparencySupported](#istransparencysupported)|응용 프로그램에 투명 한 비트맵 지원 하는지 여부를 나타냅니다.|
|[CImage::Load](#load)|지정된 된 파일에서 이미지를 로드합니다.|
|[CImage::LoadFromResource](#loadfromresource)|지정된 된 리소스에서 이미지를 로드합니다.|
|[CImage::MaskBlt](#maskblt)|지정 된 마스크와 래스터 연산을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.|
|[CImage::PlgBlt](#plgblt)|원본 장치 컨텍스트의 사각형에서 대상 장치 컨텍스트에서 평행 사변형에 비트 블록 전송을 수행합니다.|
|[CImage::ReleaseDC](#releasedc)|사용 하 여 검색 된 장치 컨텍스트를 해제 [CImage::GetDC](#getdc)합니다.|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI +에서 사용 되는 리소스를 해제 합니다. 전역에서 만든 리소스를 호출 해야 `CImage` 개체입니다.|
|[CImage::Save](#save)|지정된 된 형식으로 이미지를 저장합니다. `Save` 이미지 옵션을 지정할 수 없습니다.|
|[CImage::SetColorTable](#setcolortable)|빨간색, 녹색, 파란색 RGB 설정) 색상 DIB 섹션의 색 테이블의 항목 범위에 있는 값입니다.|
|[CImage::SetPixel](#setpixel)|지정된 된 색을 지정된 된 좌표에서 픽셀을 설정합니다.|
|[CImage::SetPixelIndexed](#setpixelindexed)|색 색상표의 지정 된 인덱스에 지정된 된 좌표에서 픽셀을 설정합니다.|
|[CImage::SetPixelRGB](#setpixelrgb)|지정한 빨강, 녹색, 파란색 (RGB) 값으로 지정된 된 좌표에서 픽셀을 설정합니다.|
|[CImage::SetTransparentColor](#settransparentcolor)|투명 하 게 처리 하려면 색의 인덱스를 설정 합니다. 색상표에 하나의 색 투명 하 게 될 수 있습니다.|
|[CImage::StretchBlt](#stretchblt)|소스 사각형에서 필요한 경우 대상 사각형의 크기에 맞게 비트맵을 늘이거나 대상 사각형으로 비트맵을 복사 합니다.|
|[CImage::TransparentBlt](#transparentblt)|이 현재 장치 컨텍스트에 소스 장치 컨텍스트에에서 투명 한 색을 사용 하 여 비트맵을 복사합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CImage::operator HBITMAP](#operator_hbitmap)|에 연결 된 Windows 핸들을 반환 합니다 `CImage` 개체입니다.|

## <a name="remarks"></a>설명

`CImage` 비트맵 또는 부정 하거나 장치 독립적 비트맵 (DIB) 섹션은 사용 사용할 수 있습니다 [Create](#create) 또는 [CImage::Load](#load) DIB 섹션만 사용 합니다. 비 DIB 섹션 비트맵을 연결할 수 있습니다는 `CImage` 를 사용 하 여 개체 [연결](#attach), 하지만 다음을 사용할 수 없습니다. 다음 `CImage` DIB 구역을 비트맵만을 지원 하는 메서드:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

연결 된 비트맵을 DIB 구역을 인지를 확인 하려면 호출 [IsDibSection](#isdibsection)합니다.

> [!NOTE]
> Visual Studio.NET 2003에서이 클래스는 수의 개수를 유지 `CImage` 생성 되는 개체입니다. 함수를 0으로 카운트가 때마다 `GdiplusShutdown` GDI +에서 사용 되는 리소스를 해제 하려면 자동으로 호출 됩니다. 이렇게 하면 모든 `CImage` Dll에서 직접 또는 간접적으로 생성 된 개체는 항상 올바르게 소멸 올바르고 `GdiplusShutdown` 에서 호출 되지 않습니다 `DllMain`합니다.

> [!NOTE]
> 전역을 사용 하 여 `CImage` 개체 DLL에 권장 되지 않습니다. 전역 사용 해야 하는 경우 `CImage` 개체를 dll로 호출 [CImage::ReleaseGDIPlus](#releasegdiplus) 를 명시적으로 GDI +에서 사용 되는 리소스를 해제 합니다.

`CImage` 새 선택할 수 없습니다 [CDC](../../mfc/reference/cdc-class.md)합니다. `CImage` 이미지에 대 한 자체 HDC를 만듭니다. HBITMAP 연관만 HBITMAP를 한 번에 하나의 HDC를 선택할 수 있습니다, 되므로 `CImage` 다른 HDC를 선택할 수 없습니다. CDC를 해야 하는 경우 검색에서 HDC 합니다 `CImage` 를 지정 하 고 [CDC::FromHandle](../../mfc/reference/cdc-class.md#fromhandle)합니다.

## <a name="example"></a>예제

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

사용 하는 경우 `CImage` MFC 프로젝트에서 프로젝트의 멤버 함수는 예상에 대 한 포인터를 확인 한 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체입니다. 사용 하려는 경우 `CImage` 이러한 함수를 사용 하 여 같은 [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)를 사용 하 여 [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), 전달에 `CImage` HBITMAP를 사용 하 여 반환 된 `CBitmap*`합니다.

## <a name="example"></a>예제

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

통해 `CImage`, DIB 섹션의 실제 비트에 액세스할 수 있습니다. 사용할 수는 `CImage` Win32 HBITMAP 또는 DIB 구역을 사용 했던 개체입니다.

사용할 수 있습니다 `CImage` MFC 또는 ATL.

> [!NOTE]
> 사용 하 여 프로젝트를 만들면 `CImage`를 정의 해야 합니다 `CString` 포함 하기 전에 `atlimage.h`입니다. 프로젝트에 ATL MFC 없이 사용 하는 경우 포함 `atlstr.h` 포함 하기 전에 `atlimage.h`입니다. 프로젝트에 MFC (또는 MFC 지원을 통해 ATL 프로젝트를) 사용 하는 경우 포함 `afxstr.h` 포함 하기 전에 `atlimage.h`입니다.<br/>
> <br/>
> 마찬가지로, 포함 해야 합니다 `atlimage.h` 포함 하기 전에 `atlimpl.cpp`입니다. 이를 위해 쉽게 포함 `atlimage.h` 에서 프로그램 `stdafx.h`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlimage.h

##  <a name="alphablend"></a>  CImage::AlphaBlend

투명 하거나 반투명 픽셀로 있는 비트맵을 표시 합니다.

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트에 대 한 핸들입니다.

*xDest*<br/>
X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*yDest*<br/>
Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*bSrcAlpha*<br/>
전체 소스 비트맵에 사용 하는 알파 투명도 값입니다. 기본값 (255) 0xff 불투명 이미지는 픽셀 별 알파 값만 사용 하려는 가정 합니다.

*bBlendOp*<br/>
전체 소스 비트맵 및 소스 비트맵에 대 한 형식 정보에 적용할 전역 알파 값을 원본 및 대상 비트맵에는 알파 혼합 함수입니다. 원본 및 대상 blend 함수는 현재 AC_SRC_OVER로 제한 합니다.

*pointDest*<br/>
에 대 한 참조를 [지점](/previous-versions/dd162805\(v=vs.85\)) 논리 단위에서 대상 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.

*nDestWidth*<br/>
논리 단위를 대상 사각형의 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리 단위에서 높이입니다.

*xSrc*<br/>
소스 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.

*ySrc*<br/>
소스 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.

*nSrcWidth*<br/>
논리 단위를 소스 사각형의 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리 단위에서 높이입니다.

*rectDest*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조, 대상을 식별 합니다.

*rectSrc*<br/>
에 대 한 참조를 `RECT` 구조, 소스를 식별 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

알파 혼합 비트맵 픽셀 별 기준 색 혼합을 지원 합니다.

때 *bBlendOp* 설정할지 AC_SRC_OVER 기본값으로 소스 비트맵 소스 픽셀의 알파 값을 기반으로 대상 비트맵을 통해 배치 됩니다.

##  <a name="attach"></a>  CImage::Attach

연결 *hBitmap* 에 `CImage` 개체입니다.

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
HBITMAP 핸들입니다.

*eOrientation*<br/>
비트맵의 방향을 지정합니다. 다음 중 하나일 수 있습니다.

- 비트맵의 방향을 DIBOR_DEFAULT 운영 체제에 의해 결정 됩니다.

- 비트맵의 선은 반대 순서로 DIBOR_BOTTOMUP 합니다. 이 인해 [CImage::GetBits](#getbits) 비트맵 버퍼의 끝 부분에 대 한 포인터를 반환 하 고 [CImage::GetPitch](#getpitch) 음수를 반환 합니다.

- DIBOR_TOPDOWN 비트맵 선은 위에서 아래 순입니다. 이 인해 [CImage::GetBits](#getbits) 비트맵 버퍼의 첫 번째 바이트에 대 한 포인터를 반환 하 고 [CImage::GetPitch](#getpitch) 양수 값을 반환할 합니다.

### <a name="remarks"></a>설명

비트맵을 DIB 아닌 섹션 비트맵 또는 DIB 구역 비트맵을 수 있습니다. 참조 [IsDIBSection](#isdibsection) DIB 함께만 사용할 수 있는 메서드의 목록에 대 한 비트맵을 섹션입니다.

##  <a name="bitblt"></a>  CImage::BitBlt

현재이 장치 컨텍스트를 원본 장치 컨텍스트에서 비트맵을 복사 합니다.

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
HDC 대상입니다.

*xDest*<br/>
대상 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.

*dwROP*<br/>
래스터 작업 수행 수입니다. 래스터 작업 코드를 대상 (현재 선택 된 브러시에 의해 정의 됨) 처럼 원본, 대상 및 패턴의 비트를 결합 하는 방법에 정확 하 게 정의 합니다. 참조 [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) 다른 래스터 연산은 코드와 해당 설명의 목록을 Windows SDK에 있습니다.

*pointDest*<br/>
A [지점](/previous-versions/dd162805\(v=vs.85\)) 대상 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.

*nDestWidth*<br/>
논리 단위를 대상 사각형의 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리 단위에서 높이입니다.

*xSrc*<br/>
소스 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.

*ySrc*<br/>
소스 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.

*rectDest*<br/>
A [RECT](/previous-versions/dd162897\(v=vs.85\)) 대상 사각형을 나타내는 구조입니다.

*pointSrc*<br/>
`POINT` 소스 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) Windows SDK에 있습니다.

##  <a name="cimage"></a>  CImage::CImage

`CImage` 개체를 생성합니다.

```
CImage() throw();
```

### <a name="remarks"></a>설명

개체를 생성 한 후 호출 [만들기](#create), [부하](#load)를 [LoadFromResource](#loadfromresource), 또는 [연결](#attach) 비트맵 개체에 연결 합니다.

**참고** Visual Studio에서이 클래스의 개수를 유지 합니다 `CImage` 생성 되는 개체입니다. 함수를 0으로 카운트가 때마다 `GdiplusShutdown` GDI +에서 사용 되는 리소스를 해제 하려면 자동으로 호출 됩니다. 이렇게 하면 모든 `CImage` Dll에서 직접 또는 간접적으로 생성 된 개체는 항상 올바르게 소멸 하 고 `GdiplusShutdown` DllMain에서 호출 되지 않습니다.

전역을 사용 하 여 `CImage` 개체 DLL에 권장 되지 않습니다. 전역 사용 해야 하는 경우 `CImage` 개체를 dll로 호출 [CImage::ReleaseGDIPlus](#releasegdiplus) 를 명시적으로 GDI +에서 사용 되는 리소스를 해제 합니다.

##  <a name="create"></a>  CImage::Create

만듭니다는 `CImage` 비트맵을 연결할 이전에 생성 된 `CImage` 개체입니다.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
너비는 `CImage` 비트맵 픽셀에서입니다.

*nHeight*<br/>
높이 `CImage` 비트맵 픽셀에서입니다. 하는 경우 *nHeight* 이 양수인 경우 비트맵 상향식 DIB 이며 해당 원본 왼쪽된 아래 모퉁이. 하는 경우 *nHeight* 음수 이면 비트맵 하향식 DIB 이며 해당 원점은 왼쪽된 위 모퉁이.

*nBPP*<br/>
비트맵의 픽셀 당 비트 수입니다. 일반적으로 4, 8, 16, 24 또는 32 흑백 비트맵 또는 마스크에 대 한 1을 수 있습니다.

*dwFlags*<br/>
비트맵 개체에 알파 채널이 있는지를 지정 합니다. 0 개 이상의 다음 값의 조합일 수 있습니다.

- *createAlphaChannel* 경우에 사용할 수 *nBPP* 은 32, 및 *eCompression* BI_RGB 됩니다. 를 지정 하는 경우 만든된 이미지의 각 픽셀 (영숫자가 아닌 32 비트 이미지에 사용 되지 않는)의 네 번째 바이트에 저장 된 각 픽셀에 대 한 알파 (투명도) 값. 호출할 때이 알파 채널은 자동으로 사용 됩니다 [CImage::AlphaBlend](#alphablend)합니다.

> [!NOTE]
> 에 대 한 호출 [CImage::Draw](#draw), 알파 채널을 사용 하 여 이미지는 자동으로 알파 대상으로 혼합 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="createex"></a>  CImage::CreateEx

만듭니다는 `CImage` 비트맵을 연결할 이전에 생성 된 `CImage` 개체입니다.

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
너비는 `CImage` 비트맵 픽셀에서입니다.

*nHeight*<br/>
높이 `CImage` 비트맵 픽셀에서입니다. 하는 경우 *nHeight* 이 양수인 경우 비트맵 상향식 DIB 이며 해당 원본 왼쪽된 아래 모퉁이. 하는 경우 *nHeight* 음수 이면 비트맵 하향식 DIB 이며 해당 원점은 왼쪽된 위 모퉁이.

*nBPP*<br/>
비트맵의 픽셀 당 비트 수입니다. 일반적으로 4, 8, 16, 24 또는 32 흑백 비트맵 또는 마스크에 대 한 1을 수 있습니다.

*eCompression*<br/>
(위에서 아래로 Dib를 압축할 수 없습니다.) 압축 된 상향식 비트맵에 대 한 압축 유형을 지정 합니다. 다음 값 중 하나입니다.

- BI_RGB 형식으로 압축 된 아닙니다. 호출할 때이 값을 지정할 `CImage::CreateEx` 호출과 같습니다 `CImage::Create`합니다.

- BI_BITFIELDS 형식으로 압축 되지 및 색상표의 각 픽셀의 각각 빨강, 녹색 및 파랑 구성 요소를 지정 하는 세 가지 DWORD 색 마스크 구성 됩니다. 16 및 32 bpp 비트맵을 사용 하는 경우에 유효 합니다.

*pdwBitfields*<br/>
경우에 사용 *eCompression* 설정할지를 BI_BITFIELDS, 그렇지 않으면 NULL 이어야 합니다. 비트를 각 픽셀의 색의 빨강, 녹색 및 파랑 구성 요소에 대해 각각 사용 지정, 세 개의 DWORD 비트 마스크의 배열에 대 한 포인터입니다. 비트 필드에 대 한 제한 사항에 대 한 자세한 내용은 [BITMAPINFOHEADER](/previous-versions//dd183376\(v=vs.85\)) Windows SDK에 있습니다.

*dwFlags*<br/>
비트맵 개체에 알파 채널이 있는지를 지정 합니다. 0 개 이상의 다음 값의 조합일 수 있습니다.

- *createAlphaChannel* 경우에 사용할 수 *nBPP* 은 32, 및 *eCompression* BI_RGB 됩니다. 를 지정 하는 경우 만든된 이미지의 각 픽셀 (영숫자가 아닌 32 비트 이미지에 사용 되지 않는)의 네 번째 바이트에 저장 된 각 픽셀에 대 한 알파 (투명도) 값. 호출할 때이 알파 채널은 자동으로 사용 됩니다 [CImage::AlphaBlend](#alphablend)합니다.

   > [!NOTE]
   > 에 대 한 호출 [CImage::Draw](#draw), 알파 채널을 사용 하 여 이미지는 자동으로 알파 대상으로 혼합 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE이 고 그렇지 않으면 FALSE입니다.

### <a name="example"></a>예제

다음 예제에서는 16 비트를 사용 하 여 각 픽셀을 인코딩할 100 x 100 픽셀 비트맵을 만듭니다. 지정된 된 16 비트 픽셀 0-3 비트 인코딩 빨강 구성 요소, 4 ~ 7 비트, 녹색, 인코딩 및 8 ~ 11 비트 인코딩 파란색입니다. 나머지 4 비트 사용 되지 않습니다.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

##  <a name="destroy"></a>  CImage::Destroy

비트맵을 분리 합니다 `CImage` 개체 및 비트맵을 삭제 합니다.

```
void Destroy() throw();
```

##  <a name="detach"></a>  CImage::Detach

비트맵을 분리는 `CImage` 개체입니다.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>반환 값

분리 비트맵에 대 한 핸들 또는 비트맵이 없습니다 연결 되어 있으면 NULL입니다.

##  <a name="draw"></a>  CImage::Draw

현재 장치 컨텍스트에 원본 장치 컨텍스트에서 비트맵을 복사 합니다.

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트의 핸들입니다.

*xDest*<br/>
X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*yDest*<br/>
Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nDestWidth*<br/>
논리 단위를 대상 사각형의 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리 단위에서 높이입니다.

*xSrc*<br/>
X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*ySrc*<br/>
Y 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nSrcWidth*<br/>
논리 단위를 소스 사각형의 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리 단위에서 높이입니다.

*rectDest*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조, 대상을 식별 합니다.

*rectSrc*<br/>
에 대 한 참조를 `RECT` 구조, 소스를 식별 합니다.

*pointDest*<br/>
에 대 한 참조를 [지점](/previous-versions/dd162805\(v=vs.85\)) 논리 단위에서 대상 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Draw` 동일한 작업을 수행할 [StretchBlt](#stretchblt)투명 한 색 또는 알파 채널 이미지 포함 되지 않은 경우. 이 경우 `Draw` 하거나 동일한 작업을 수행할 [지연 해야](#transparentblt) 또는 [해 서 AlphaBlend](#alphablend) 필요에 따라 합니다.

버전의 `Draw` 소스 사각형을 지정 하지 않는, 전체 원본 이미지의 기본값입니다. 버전의 `Draw` 대상 사각형의 크기를 지정 하지 않은, 기본 및 확장 하지 않는 원본 이미지의 크기는 또는 발생을 축소 합니다.

##  <a name="getbits"></a>  CImage::GetBits

비트맵의 각된 픽셀의 실제 비트 값에 대 한 포인터를 검색합니다.

```
void* GetBits() throw();
```

### <a name="return-value"></a>반환 값

비트맵 버퍼에 대 한 포인터입니다. 비트맵 상향식 DIB 이면 포인터가 가리키는 버퍼의 끝을 부분입니다. 비트맵 하향식 DIB 이면 포인터가 버퍼의 첫 번째 바이트를 가리킵니다.

### <a name="remarks"></a>설명

이 포인터를 반환한 값과 함께 사용 하 여 [GetPitch](#getpitch)를 찾아서 개별 픽셀 이미지를 변경할 수 있습니다.

> [!NOTE]
> 이 메서드는 DIB 섹션 포함 된 비트맵만; 지원 픽셀을 액세스 하는 결과적으로 `CImage` 픽셀 DIB 섹션 하는 동일한 방식으로 개체입니다. 반환된 된 포인터 (0, 0) 위치에 픽셀을 가리킵니다.

##  <a name="getbpp"></a>  CImage::GetBPP

비트 / 픽셀 값을 검색 합니다.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>반환 값

픽셀당 비트 수입니다.

### <a name="remarks"></a>설명

이 값이 각 픽셀을 정의 하는 비트 수 및 최대 수가 비트맵의 색을 결정 합니다.

픽셀당 비트는 일반적으로 1, 4, 8, 16, 24 또는 32입니다. 참조를 `biBitCount` 소속 [BITMAPINFOHEADER](/previous-versions//dd183376\(v=vs.85\)) 이 값에 대 한 자세한 내용은 Windows SDK에 있습니다.

##  <a name="getcolortable"></a>  CImage::GetColorTable

DIB 섹션의 색상표에 있는 항목의 범위에서 빨간색, 녹색, 파란색 (RGB) 색 값을 검색합니다.

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>매개 변수

*iFirstColor*<br/>
검색할 첫 번째 항목의 색 테이블 인덱스입니다.

*nColors*<br/>
검색할 색 테이블 항목의 수입니다.

*prgbColors*<br/>
배열에 대 한 포인터 [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) 색을 검색 하는 구조 테이블 항목입니다.

##  <a name="getdc"></a>  CImage::GetDC

현재에 선택한 이미지를가지고 있는 장치 컨텍스트를 검색 합니다.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>반환 값

디바이스 컨텍스트에 대한 핸들입니다.

### <a name="remarks"></a>설명

호출할 때마다 `GetDC`에 대 한 후속 호출을 해야 [ReleaseDC](#releasedc)합니다.

##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString

이미지를 저장 하기 위한 사용 가능한 이미지 형식을 찾습니다.

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>매개 변수

*strExporters*<br/>
`CSimpleString` 개체에 대한 참조입니다. 참조 **주의** 자세한 내용은 합니다.

*aguidFileTypes*<br/>
문자열에 있는 파일 형식의 하나에 해당 하는 각 요소와 Guid의 배열입니다. 예에서 *pszAllFilesDescription* 아래 *aguidFileTypes*[0] GUID_NULL 이며 나머지 배열 값은 현재 운영 체제에서 지 원하는 이미지 파일 형식입니다.

> [!NOTE]
> 상수의 전체 목록은 참조 하세요 **이미지 파일 형식 상수** Windows SDK에 있습니다.

*pszAllFilesDescription*<br/>
이 매개 변수가 NULL이 아닌 경우 필터 문자열 목록 맨 앞에 추가 필터 중 하나의 갖습니다. 이 필터의 현재 값을 갖습니다 *pszAllFilesDescription* 해당 설명에 대 한 목록의 모든 다른 내보내기에서 지원 되는 확장명의 파일을 수락 하 고 있습니다.

예를 들어:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
목록에서 제외할 파일 형식을 지정 하는 비트 플래그 집합입니다. 사용할 수 있는 플래그는:

- `excludeGIF` = 0x01 제외 GIF 파일.

- `excludeBMP` = 0x02 제외 BMP (Windows 비트맵) 파일입니다.

- `excludeEMF` = 0x04 제외 EMF (확장 메타 파일) 파일입니다.

- `excludeWMF` = 0x08 제외 WMF (Windows 메타 파일) 파일입니다.

- `excludeJPEG` = 0x10 제외 JPEG 파일.

- `excludePNG` = 0x20 제외 PNG 파일입니다.

- `excludeTIFF` = 0x40 제외 TIFF 파일입니다.

- `excludeIcon` = 0x80 제외 ICO (Windows 아이콘) 파일입니다.

- `excludeOther` = 0x80000000 위에 나열 되지 않은 다른 모든 파일 형식을 제외 합니다.

- `excludeDefaultLoad` = 0의 형식이 기본적으로 포함 된 모든 파일 로드

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` 저장에 대 한 일반적으로 특별 한 요구 사항이 있기 때문에 이러한 파일은 기본적으로 제외 됩니다.

*chSeparator*<br/>
이미지 형식 간에 사용 되는 구분 기호입니다. 참조 **주의** 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

MFC 프로그램에 결과 형식 문자열을 전달할 수 있습니다 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 이름으로 파일 저장 대화 상자에서 사용할 수 있는 이미지의 파일 확장명을 노출 하는 개체 형식을 지정 합니다.

매개 변수 *strExporter* 형식은:

description0 파일&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;....file 설명 *n*&#124;\*.ext *n*&#124;&#124;

여기서 '&#124;'으로 지정 된 구분 기호 문자 `chSeparator`합니다. 예를 들어:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

기본 구분 기호를 사용 하 여 '&#124;'는 MFC에이 문자열을 전달 하는 경우 `CFileDialog` 개체입니다. 일반적인 파일 저장 대화 상자에이 문자열을 전달 하는 경우 null 구분 기호 '\0'를 사용 합니다.

##  <a name="getheight"></a>  CImage::GetHeight

이미지의 픽셀에서 높이 검색합니다.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>반환 값

이미지의 픽셀에서 높이입니다.

##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString

이미지를 로드 하는 사용 가능한 이미지 형식을 찾습니다.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>매개 변수

*strImporters*<br/>
`CSimpleString` 개체에 대한 참조입니다. 참조 **주의** 자세한 내용은 합니다.

*aguidFileTypes*<br/>
문자열에 있는 파일 형식의 하나에 해당 하는 각 요소와 Guid의 배열입니다. 예에서 *pszAllFilesDescription* 아래 *aguidFileTypes*[0] GUID_NULL 나머지 배열 값은 현재 운영 체제에서 지 원하는 이미지 파일 형식입니다.

> [!NOTE]
> 상수의 전체 목록은 참조 하세요 **이미지 파일 형식 상수** Windows SDK에 있습니다.

*pszAllFilesDescription*<br/>
이 매개 변수가 NULL이 아닌 경우 필터 문자열 목록 맨 앞에 추가 필터 중 하나의 갖습니다. 이 필터의 현재 값을 갖습니다 *pszAllFilesDescription* 해당 설명에 대 한 목록의 모든 다른 내보내기에서 지원 되는 확장명의 파일을 수락 하 고 있습니다.

예를 들어:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
목록에서 제외할 파일 형식을 지정 하는 비트 플래그 집합입니다. 사용할 수 있는 플래그는:

- `excludeGIF` = 0x01 제외 GIF 파일.

- `excludeBMP` = 0x02 제외 BMP (Windows 비트맵) 파일입니다.

- `excludeEMF` = 0x04 제외 EMF (확장 메타 파일) 파일입니다.

- `excludeWMF` = 0x08 제외 WMF (Windows 메타 파일) 파일입니다.

- `excludeJPEG` = 0x10 제외 JPEG 파일.

- `excludePNG` = 0x20 제외 PNG 파일입니다.

- `excludeTIFF` = 0x40 제외 TIFF 파일입니다.

- `excludeIcon` = 0x80 제외 ICO (Windows 아이콘) 파일입니다.

- `excludeOther` = 0x80000000 위에 나열 되지 않은 다른 모든 파일 형식을 제외 합니다.

- `excludeDefaultLoad` = 0의 형식이 기본적으로 포함 된 모든 파일 로드

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` 저장에 대 한 일반적으로 특별 한 요구 사항이 있기 때문에 이러한 파일은 기본적으로 제외 됩니다.

*chSeparator*<br/>
이미지 형식 간에 사용 되는 구분 기호입니다. 참조 **주의** 자세한 내용은 합니다.

### <a name="remarks"></a>설명

에 MFC에 결과 형식 문자열을 전달할 수 있습니다 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 에서 사용할 수 있는 이미지의 파일 확장명을 노출 하는 개체 형식을 지정 합니다 **파일 열기** 대화 상자.

매개 변수 *strImporter* 형식은:

description0 파일&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;....file 설명 *n*&#124;\*.ext *n*&#124;&#124;

여기서 '&#124;'은 지정 된 구분 기호 문자 *chSeparator*합니다. 예를 들어:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

기본 구분 기호를 사용 하 여 '&#124;'는 MFC에이 문자열을 전달 하는 경우 `CFileDialog` 개체입니다. 이 문자열을 공용으로 전달 하는 경우 null 구분 기호 '\0'를 사용 **파일 열기** 대화 상자.

##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries

색상표에 있는 항목의 최대 수를 검색 합니다.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>반환 값

색상표에 있는 엔트리의 수입니다.

### <a name="remarks"></a>설명

이 메서드는 DIB 구역을 비트맵만 지원합니다.

##  <a name="getpitch"></a>  CImage::GetPitch

이미지의 피치를 검색합니다.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>반환 값

이미지의 피치 합니다. 반환 값이 음수 이면 비트맵 상향식 DIB 이며 해당 원본 왼쪽된 아래 모퉁이. 반환 값이 양수 이면 비트맵 하향식 DIB 이며 원점은 왼쪽된 위 모퉁이.

### <a name="remarks"></a>설명

(바이트) 비트맵 줄의 시작 부분을 나타내는 두 개의 메모리 주소 다음 비트맵 줄의 시작 부분 사이의 거리입니다. 피치 바이트 단위로 측정 됩니다, 때문에 이미지의 피치를 사용 하면 픽셀 형식을 결정 하도록 도와줍니다. 피치 추가 메모리를 비트맵에 대 한 예약을 포함할 수도 있습니다.

사용 하 여 `GetPitch` 사용 하 여 [GetBits](#getbits) 이미지의 각 픽셀을 찾으려고 합니다.

> [!NOTE]
> 이 메서드는 DIB 구역을 비트맵만 지원합니다.

##  <a name="getpixel"></a>  CImage::GetPixel

지정 된 위치에 있는 픽셀의 색을 검색 *x* 하 고 *y*합니다.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
픽셀의 x 좌표입니다.

*y*<br/>
픽셀의 y 좌표입니다.

### <a name="return-value"></a>반환 값

빨간색, 녹색, 파란색 (RGB) 값을 픽셀의입니다. 현재 클립 영역 외부의 픽셀 인 경우 반환 값은 CLR_INVALID 합니다.

##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress

정확한 픽셀의 주소를 검색합니다.

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
픽셀의 x 좌표입니다.

*y*<br/>
픽셀의 y 좌표입니다.

### <a name="remarks"></a>설명

주소는 픽셀 좌표, 비트맵 및 픽셀 당 비트의 피치에 따라 결정 됩니다.

픽셀당 8 비트 미만의 있는 형식의 경우이 메서드는 픽셀을 포함 하는 바이트의 주소를 반환 합니다. 예를 들어, 이미지 형식, 픽셀당 4 비트 있으면 `GetPixelAddress` 반환 바이트 당 픽셀 수 2 바이트에서 첫 번째 픽셀의 주소를 계산 해야 합니다.

> [!NOTE]
> 이 메서드는 DIB 구역을 비트맵만 지원합니다.

##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor

투명 한 색 색상표의 인덱싱된 위치를 검색합니다.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>반환 값

투명 한 색의 인덱스입니다.

##  <a name="getwidth"></a>  CImage::GetWidth

이미지의 픽셀에서 너비를 검색합니다.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>반환 값

픽셀에서 비트맵의 너비입니다.

##  <a name="isdibsection"></a>  CImage::IsDIBSection

연결 된 비트맵이 DIB 구역을 인지 확인 합니다.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>반환 값

연결 된 비트맵이 DIB 구역을 이면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

비트맵을 DIB 섹션이 표시 되지 않으면, 다음을 사용할 수 없습니다 `CImage` 메서드 DIB 구역을 비트맵만을 지원 합니다.

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

##  <a name="isindexed"></a>  CImage::IsIndexed

비트맵의 픽셀 색 색상표에 매핑되는 지 여부를 결정 합니다.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>반환 값

TRUE if indexed; otherwise FALSE.

### <a name="remarks"></a>설명

이 메서드는 8 비트 비트맵 하는 경우에 TRUE를 반환 합니다 (256 색)이 있습니다.

> [!NOTE]
> 이 메서드는 DIB 구역을 비트맵만 지원합니다.

##  <a name="isnull"></a>  CImage::IsNull

비트맵을 현재 로드 된 경우를 결정 합니다.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>설명

이 메서드가 TRUE를 반환 비트맵 현재 로드 되어 있지 않으면; 그렇지 않으면 FALSE입니다.

##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported

응용 프로그램에 투명 한 비트맵 지원 하는지 여부를 나타냅니다.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>반환 값

이 속성을 0이 아닌 경우 현재 플랫폼에서 투명도 지원 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

반환 값은 0이 아닌 경우 및 투명도 지원 되는 경우에 대 한 호출 [해 서 AlphaBlend](#alphablend)를 [지연 해야](#transparentblt), 또는 [그리기](#draw) 투명 한 색을 처리 합니다.

##  <a name="load"></a>  CImage::Load

이미지를 로드합니다.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>매개 변수

*pszFileName*<br/>
로드할 이미지 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*pStream*<br/>
로드할 이미지 파일의 이름을 포함 하는 스트림에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

지정한 이미지를 로드 *pszFileName* 하거나 *pStream*합니다.

올바른 이미지 형식은 BMP, GIF, JPEG, PNG 및 TIFF입니다.

##  <a name="loadfromresource"></a>  CImage::LoadFromResource

비트맵 리소스에서 이미지를 로드합니다.

```
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
로드할 이미지를 포함 하는 모듈의 인스턴스를 처리 합니다.

*pszResourceName*<br/>
로드할 이미지를 포함 하는 리소스의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*nIDResource*<br/>
로드할 리소스의 ID입니다.

### <a name="remarks"></a>설명

리소스는 비트맵 형식 이어야 합니다.

##  <a name="maskblt"></a>  CImage::MaskBlt

지정 된 마스크와 래스터 연산을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
해당 실행 파일에는 리소스가 포함 된 모듈에 대 한 핸들입니다.

*xDest*<br/>
X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*yDest*<br/>
Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nDestWidth*<br/>
논리 단위를 대상 사각형 및 소스 비트맵의 너비입니다.

*nDestHeight*<br/>
대상 사각형 및 소스 비트맵의 논리 단위에서 높이입니다.

*xSrc*<br/>
소스 비트맵의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.

*ySrc*<br/>
소스 비트맵의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.

*hbmMask*<br/>
원본 장치 컨텍스트에서 색 비트맵을 함께 단색 마스크 비트맵에 대 한 핸들입니다.

*xMask*<br/>
지정 된 마스크 비트맵의 가로 픽셀 오프셋 합니다 *hbmMask* 매개 변수입니다.

*yMask*<br/>
지정 된 마스크 비트맵의 세로 픽셀 오프셋 합니다 *hbmMask* 매개 변수입니다.

*dwROP*<br/>
전경색과 배경색을 모두 3 개로 구성 된 래스터 연산 코드 메서드를 사용 하 여 원본 및 대상 데이터의 조합에 컨트롤을 지정 합니다. 백그라운드 래스터 연산 코드는이 값의 상위 단어에 대해 높은 순서 바이트가에 저장 됩니다. 전경 래스터 연산 코드는이 값의 상위 단어의 낮은 순서 바이트에 저장 됩니다. 이 값의 하위 단어를 무시 되 고 0 이어야 합니다. 전경색과 배경색이 메서드의 컨텍스트에서 설명은 참조 하세요. `MaskBlt` Windows SDK에 있습니다. 일반적인 래스터 연산 코드 목록은 참조 하세요. `BitBlt` Windows SDK에 있습니다.

*rectDest*<br/>
에 대 한 참조를 `RECT` 구조, 대상을 식별 합니다.

*pointSrc*<br/>
`POINT` 소스 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.

*pointMask*<br/>
`POINT` 마스크 비트맵의 왼쪽된 위 모퉁이 나타내는 구조입니다.

*pointDest*<br/>
에 대 한 참조를 `POINT` 논리 단위에서 대상 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows NT 4.0 이상만 해당 버전에 적용 됩니다.

##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP

이 연산자를 사용 하 여 연결 된 Windows GDI 핸들을 가져오려면는 `CImage` 개체입니다. 이 연산자는 캐스팅 연산자를 HBITMAP 개체의 직접 사용을 지원 합니다.

##  <a name="plgblt"></a>  CImage::PlgBlt

원본 장치 컨텍스트의 사각형에서 대상 장치 컨텍스트에서 평행 사변형에 비트 블록 전송을 수행합니다.

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트의 핸들입니다.

*pPoints*<br/>
대상 평행 사변형의 세 모퉁이 식별 하는 세 가지 논리 공간의 점 배열에 대 한 포인터입니다. 소스 사각형의 왼쪽된 위 모퉁이이 배열, 오른쪽 위 모퉁이이 배열의 두 번째 지점 및 세 번째 지점 왼쪽된 아래 모서리에서 첫 번째 요소에 매핑됩니다. 소스 사각형의 오른쪽 아래 모퉁이 평행 사변형에 암시적 네 번째 지점에 매핑됩니다.

*hbmMask*<br/>
소스 사각형의 색을 마스크 하는 데 사용 되는 선택적 흑백 비트맵 핸들입니다.

*xSrc*<br/>
X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*ySrc*<br/>
Y 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nSrcWidth*<br/>
논리 단위를 소스 사각형의 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리 단위에서 높이입니다.

*xMask*<br/>
흑백 비트맵의 왼쪽된 위 모퉁이의 x 좌표입니다.

*yMask*<br/>
흑백 비트맵의 왼쪽된 위 모퉁이의 y 좌표입니다.

*rectSrc*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조 소스 사각형의 좌표를 지정 합니다.

*pointMask*<br/>
A [지점](/previous-versions/dd162805\(v=vs.85\)) 마스크 비트맵의 왼쪽된 위 모퉁이 나타내는 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

하는 경우 *hbmMask* 유효한 단색 비트맵을 식별 `PlgBit` 이 비트맵을 사용 하 여 소스 사각형에서 색 데이터 비트 마스크입니다.

이 메서드는 Windows NT 4.0 이상만 해당 버전에 적용 됩니다. 참조 [PlgBlt](/windows/desktop/api/wingdi/nf-wingdi-plgblt) 자세한 내용을 보려면 Windows SDK에 있습니다.

##  <a name="releasedc"></a>  CImage::ReleaseDC

장치 컨텍스트를 해제 합니다.

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>설명

한 번에 하나만 비트맵 장치 컨텍스트를 선택할 수 있습니다, 되므로 호출 해야 합니다 `ReleaseDC` 를 호출할 때마다 [GetDC](#getdc)합니다.

##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus

GDI +에서 사용 되는 리소스를 해제 합니다.

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>설명

전역 할당 된 사용 가능한 리소스를이 메서드를 호출 해야 `CImage` 개체입니다. 참조 [CImage::CImage](#cimage)합니다.

##  <a name="save"></a>  CImage::Save

지정 된 스트림 또는 디스크에 파일 이미지를 저장합니다.

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
파일 이미지 데이터를 포함 하는 COM IStream 개체에 대 한 포인터입니다.

*pszFileName*<br/>
이미지 파일 이름에 대 한 포인터입니다.

*guidFileType*<br/>
이미지를 저장 하려면 파일 형식입니다. 다음 중 하나일 수 있습니다.

- `ImageFormatBMP` 압축 되지 않은 비트맵 이미지입니다.

- `ImageFormatPNG` 그래픽 PNG (Portable Network) 압축 된 이미지입니다.

- `ImageFormatJPEG` JPEG 압축 된 이미지입니다.

- `ImageFormatGIF` GIF 이미지를 압축 합니다.

> [!NOTE]
> 상수의 전체 목록은 참조 하세요 **이미지 파일 형식 상수** Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

지정한 이름과 형식을 사용 하 여 이미지를 저장 하려면이 함수를 호출 합니다. 경우는 *guidFileType* 매개 변수를 포함할 파일 이름의 파일 확장명에서 이미지 형식을 결정 하는 데 사용 됩니다. 제공 된 확장명이 없는 경우 이미지 BMP 형식으로 저장 됩니다.

##  <a name="setcolortable"></a>  CImage::SetColorTable

DIB 섹션의 색상표에 다양 한 항목에 대 한 빨간색, 녹색, 파란색 (RGB) 색 값을 설정 합니다.

```
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>매개 변수

*iFirstColor*<br/>
설정할 첫 번째 항목의 색 테이블 인덱스입니다.

*nColors*<br/>
색 테이블 항목 집합의 수입니다.

*prgbColors*<br/>
배열에 대 한 포인터 [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) 색을 설정 하는 구조 테이블 항목입니다.

### <a name="remarks"></a>설명

이 메서드는 DIB 구역을 비트맵만 지원합니다.

##  <a name="setpixel"></a>  CImage::SetPixel

비트맵의 지정된 된 위치에 픽셀의 색을 설정합니다.

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
설정할 픽셀의 가로 위치입니다.

*y*<br/>
설정할 픽셀의 세로 위치입니다.

*color*<br/>
픽셀을 설정한 색입니다.

### <a name="remarks"></a>설명

이 메서드는 픽셀 좌표는 선택한 클리핑 영역 외부에서 놓이는 지 확인 하는 경우 실패 합니다.

##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed

픽셀 색에 있는 색을 설정 *iIndex* 색 색상표에서입니다.

```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
설정할 픽셀의 가로 위치입니다.

*y*<br/>
설정할 픽셀의 세로 위치입니다.

*iIndex*<br/>
색상표에서 색의 인덱스입니다.

##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB

지정 된 위치에서 픽셀을 설정 *x* 및 *y* 나타난 색 *r*를 *g*, 및 *b*빨간색, 녹색, 파란색 (RGB) 이미지입니다.

```
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
설정할 픽셀의 가로 위치입니다.

*y*<br/>
설정할 픽셀의 세로 위치입니다.

*r*<br/>
빨간색의 농도입니다.

*g*<br/>
녹색 색의 강도 따라 합니다.

*b*<br/>
파랑 색의 강도 따라 합니다.

### <a name="remarks"></a>설명

빨간색, 녹색 및 파란색 매개 변수를 각각 0과 255 사이의 숫자로 표시 됩니다. 모든 세 개의 매개 변수를 0으로 설정 하면 결합 된 결과 색은 검정입니다. 255 세 개의 모든 매개 변수를 설정 하는 경우 결합 된 결과 색은 흰색입니다.

##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor

투명으로 지정된 된 인덱스 위치에 색을 설정합니다.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>매개 변수

*iTransparentColor*<br/>
설정에 투명 한 색의 색상표의 인덱스입니다. -1 이면 색 없음 설정은 투명 합니다.

### <a name="return-value"></a>반환 값

색의 인덱스는 이전에 투명 하 게 설정 합니다.

##  <a name="stretchblt"></a>  CImage::StretchBlt

현재이 장치 컨텍스트를 원본 장치 컨텍스트에서 비트맵을 복사 합니다.

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트의 핸들입니다.

*xDest*<br/>
X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*yDest*<br/>
Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nDestWidth*<br/>
논리 단위를 대상 사각형의 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리 단위에서 높이입니다.

*dwROP*<br/>
래스터 작업 수행 수입니다. 래스터 작업 코드를 대상 (현재 선택 된 브러시에 의해 정의 됨) 처럼 원본, 대상 및 패턴의 비트를 결합 하는 방법에 정확 하 게 정의 합니다. 참조 [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) 다른 래스터 연산은 코드와 해당 설명의 목록을 Windows SDK에 있습니다.

*rectDest*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조, 대상을 식별 합니다.

*xSrc*<br/>
X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*ySrc*<br/>
Y 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nSrcWidth*<br/>
논리 단위를 소스 사각형의 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리 단위에서 높이입니다.

*rectSrc*<br/>
에 대 한 참조를 `RECT` 구조, 소스를 식별 합니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [StretchBlt](/windows/desktop/api/wingdi/nf-wingdi-stretchblt) Windows SDK에 있습니다.

##  <a name="transparentblt"></a>  CImage::TransparentBlt

현재이 장치 컨텍스트를 원본 장치 컨텍스트에서 비트맵을 복사 합니다.

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트의 핸들입니다.

*xDest*<br/>
X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*yDest*<br/>
Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nDestWidth*<br/>
논리 단위를 대상 사각형의 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리 단위에서 높이입니다.

*crTransparent*<br/>
소스 비트맵을 투명 하 게 처리할 색입니다. 기본적으로 CLR_INVALID, 현재 이미지의 투명 한 색으로 설정 된 색상을 사용 해야 함을 나타내는입니다.

*rectDest*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조, 대상을 식별 합니다.

*xSrc*<br/>
X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*ySrc*<br/>
Y 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.

*nSrcWidth*<br/>
논리 단위를 소스 사각형의 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리 단위에서 높이입니다.

*rectSrc*<br/>
에 대 한 참조를 `RECT` 구조, 소스를 식별 합니다.

### <a name="return-value"></a>반환 값

TRUE 이면 성공적이 고, 그렇지 않으면 FALSE.

### <a name="remarks"></a>설명

`TransparentBlt` 소스 비트맵 및 픽셀 당 8 비트 픽셀당 4 비트에 대 한 지원 됩니다. 사용 하 여 [CImage::AlphaBlend](#alphablend) 투명도 사용 하 여 32 비트 / 픽셀 비트맵을 지정 합니다.

### <a name="example"></a>예제

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>참고자료

[MMXSwarm 샘플](../../overview/visual-cpp-samples.md)<br/>
[SimpleImage 샘플](../../overview/visual-cpp-samples.md)<br/>
[장치 독립적 비트맵](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)<br/>
[장치 독립적 비트맵](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)
