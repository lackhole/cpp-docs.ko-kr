---
title: 이미지 목록 형식
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: 939aad78b7cf8cca9c940bae11892d23dbb659cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180852"
---
# <a name="types-of-image-lists"></a>이미지 목록 형식

이미지 목록에 두 종류가 있습니다 ([CImageList](../mfc/reference/cimagelist-class.md)): 마스크 되지 않은 및 마스크입니다. "마스크 되지 않은 이미지 목록" 하나 이상의 이미지를 포함 하는 색 비트맵 이루어져 있습니다. "마스킹된 이미지 목록" 동일한 크기의 두 비트맵으로 구성 됩니다. 첫 번째 이미지를 포함 하는 색 비트맵 이며 두 번째 일련의 마스크를 포함 하는 단색 비트맵을-첫 번째 비트맵의 각 이미지에 대 한 합니다.

오버 로드 중 하나는 `Create` 멤버 함수는 이미지 목록을 마스킹 되었는지 여부를 표시 하는 플래그를 사용 합니다. (다른 오버 로드에 마스크 된 이미지 목록을 만듭니다.)

마스크 되지 않은 이미지를 그릴 때 단순히 대상 장치 컨텍스트를에 복사 됩니다. 즉, 장치 컨텍스트의 기존 배경색 위에 그려집니다. 마스크 된 이미지를 그릴 때 일반적으로 비트맵에서 투명 한 영역 생성을 통해 대상 장치 컨텍스트의 배경색을 표시 하는 위치를 마스크의 비트를 사용 하 여 이미지의 비트 결합 됩니다. 마스크 된 이미지를 그릴 때 여러 그리기 스타일을 지정할 수 있습니다. 예를 들어, 선택한 개체를 나타내기 위해 이미지가 디더링는 지정할 수 있습니다.

## <a name="see-also"></a>참고자료

[CImageList 사용](../mfc/using-cimagelist.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
