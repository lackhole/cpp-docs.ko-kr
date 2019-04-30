---
title: 이미지 목록에서 이미지 그리기
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
ms.openlocfilehash: e2058c727620c9aae4ccd9a3fbeaae02c78ce8c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262803"
---
# <a name="drawing-images-from-an-image-list"></a>이미지 목록에서 이미지 그리기

이미지를 그리기 위해 사용 합니다 [CImageList::Draw](../mfc/reference/cimagelist-class.md#draw) 멤버 함수입니다. 장치 컨텍스트 개체를 그릴 위치에서 이미지를 그릴 디바이스 컨텍스트에서 이미지의 인덱스 및 그리기 스타일을 표시 하기 위해 플래그 집합이에 대 한 포인터를 지정 합니다.

지정 하는 경우는 **ILD_TRANSPARENT** 스타일 `Draw` 2 단계 프로세스를 사용 하 여 마스킹된 이미지를 그립니다. 먼저 논리 수행-및 이미지의 비트 마스크의 비트에는 작업입니다. 그런 다음 첫 번째 작업의 결과와 대상 장치 컨텍스트의 백그라운드 비트 논리적 XOR 작업을 수행합니다. 이 프로세스는 결과 이미지에서 투명 한 영역을 만듭니다. 즉, 각 흰색 비트 마스크의 투명 하 게 결과 이미지에 해당 비트를 발생 합니다.

단색 배경에서 마스크 된 이미지를 그리기를 전에 사용 해야 합니다 [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) 멤버 함수를 대상으로 동일한 색으로 이미지 목록의 배경색을 설정 합니다. 이미지에서 투명 한 영역을 만들 필요가 없습니다 색을 설정 및 사용 하도록 설정 `Draw` 이미지 결과 성능이 크게 향상 하 고 대상 장치 컨텍스트를 단순히 복사할 합니다. 이미지를 그릴 지정 된 **ILD_NORMAL** 호출 하는 경우 스타일 `Draw`합니다.

마스크 된 이미지 목록에 대 한 배경색을 설정할 수 있습니다 ([CImageList](../mfc/reference/cimagelist-class.md)) 언제 든 지 있도록 한다는 올바르게 모든 단색 배경을 그립니다. 배경색을 설정 **CLR_NONE** 하면 기본적으로 투명 하 게 그릴 이미지입니다. 이미지 목록의 배경색을 검색 하려면 사용 합니다 [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) 멤버 함수입니다.

합니다 **ILD_BLEND25** 하 고 **ILD_BLEND50** 스타일 디더링 시스템 강조 색을 사용 하 여 이미지입니다. 이러한 스타일은 마스크 된 이미지를 사용 하 여 사용자가 선택할 수 있는 개체를 나타내는 경우에 유용 합니다. 예를 들어 사용할 수 있습니다 합니다 **ILD_BLEND50** 스타일 이미지를 그릴 사용자가이 선택 합니다.

마스크 되지 않은 이미지를 사용 하 여 대상 장치 컨텍스트에 복사할는 `SRCCOPY` 래스터 작업 합니다. 이미지의 색상 장치 컨텍스트의 배경색에 관계 없이 동일 하 게 표시 합니다. 에 지정 된 그리기 스타일 `Draw` 수도 마스크 되지 않은 이미지의 모양에 영향을 주지 않습니다.

멤버 함수 Draw에 다른 함수 외에도 [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), 이미지를 렌더링 하는 기능을 확장 합니다. `DrawIndirect` 매개 변수로 사용 된 [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) 구조입니다. 래스터 연산 (ROP) 코드의 사용을 포함 하 여 현재 이미지의 렌더링을 사용자 지정이 구조를 사용할 수 있습니다. ROP 코드에 대 한 자세한 내용은 참조 하세요. [래스터 연산 코드](/windows/desktop/gdi/raster-operation-codes) 하 고 [브러시로 비트맵](/windows/desktop/gdi/bitmaps-as-brushes) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CImageList 사용](../mfc/using-cimagelist.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
