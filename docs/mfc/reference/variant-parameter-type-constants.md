---
title: 가변 매개 변수 형식 상수
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: b15a303f69ce13cf3ba3b6c1c0739acdb8a33c7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309482"
---
# <a name="variant-parameter-type-constants"></a>가변 매개 변수 형식 상수

이 항목에서는 Microsoft Foundation Class Library의 OLE 컨트롤 클래스를 사용 하 여 사용 하도록 설계 된 가변 매개 변수 유형을 나타내는 새 상수를 나열 합니다.

다음은 클래스 상수의 목록입니다.

##  <a name="_mfc_variant_data_constants"></a> 가변 데이터 상수

- VTS_COLOR 32 비트 정수 RGB 색 값을 나타내는 데 사용 합니다.

- VTS_FONT는 포인터로 `IFontDisp` OLE 글꼴 개체 인터페이스입니다.

- VTS_HANDLE는 Windows 핸들 값입니다.

- VTS_PICTURE는 포인터로 `IPictureDisp` OLE 그림 개체의 인터페이스입니다.

- VTS_OPTEXCLUSIVE 16 비트 값을 라디오 단추 등의 컨트롤 그룹에 사용할 수 있는 컨트롤에 사용 합니다. 이 형식 그룹에서 하나의 컨트롤에 TRUE 값을 FALSE 여야 합니다 다른 모든 컨테이너에 지시 합니다.

- VTS_TRISTATE 16 비트는 부호 있는 정수 세 가지 가능한 값 중 하나 (선택한, 캐시, 사용할 수 없음) 예를 들어, 확인란을 가질 수 있는 속성에 사용 합니다.

- HIMETRIC 단위에서 x 축 따라 위치를 나타내는 데 사용 되는 32 비트 부호 없는 정수를 VTS_XPOS_HIMETRIC입니다.

- VTS_YPOS_HIMETRIC 32 비트 부호 없는 정수를 HIMETRIC 단위로 y 축 따라 위치를 나타내는 데 사용

- X 축 따라 위치를 픽셀 단위로 나타내는 데는 32 비트 부호 없는 정수를 VTS_XPOS_PIXELS입니다.

- Y 축 따라 위치를 픽셀 단위로 나타내는 데는 32 비트 부호 없는 정수를 VTS_YPOS_PIXELS입니다.

- 픽셀에서 화면 개체의 너비를 나타내는 데는 32 비트 부호 없는 정수를 VTS_XSIZE_PIXELS입니다.

- 픽셀에서 화면 개체의 높이 나타내는 데는 32 비트 부호 없는 정수를 VTS_YSIZE_PIXELS입니다.

- VTS_XSIZE_HIMETRIC 32 비트 부호 없는 정수를 HIMETRIC 단위의 화면 개체의 너비를 나타내는 데 사용

- VTS_YSIZE_HIMETRIC 32 비트 부호 없는 정수를 HIMETRIC 단위의 화면 개체의 높이 나타내는 데 사용

    > [!NOTE]
    >  형식에 대 한 모든 변형, VTS_FONT 및 VTS_PICTURE를 제외 하 고 가변 데이터 상수에 대 한 포인터를 제공 하는 추가 variant 상수 정의 되었습니다. 이러한 상수는 VTS_P를 사용 하 여 명명 된`constantname` 규칙입니다. 예를 들어, VTS_PCOLOR VTS_COLOR 상수에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
