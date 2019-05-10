---
title: ATL 소개
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM objects, creating in ATL
- ATL
ms.assetid: 77f565e8-c4ec-4a80-af4b-7278fcfe5c98
ms.openlocfilehash: 8c2dcab962cd9863acf0f8e7070727f3b18117d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261919"
---
# <a name="introduction-to-atl"></a>ATL 소개

ATL은 작고 빠른 콤포넌트 개체 모델(COM) 개체를 쉽게 만들 수 있는 템플릿 기반 C++ 클래스 집합인 액티브 템플릿 라이브러리입니다. [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory), [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) 및 `IDispatch`의 각자 구현을 포함하여 주요 COM 기능에 대한 특별한 지원을 제공합니다. 특별한 지원에는 이중 인터페이스, 표준 COM 열거자 인터페이스, 연결 지점, 분리 인터페이스(tear-off interfaces), 액티브X 컨트롤이 포함됩니다.

ATL 코드는 단일 스레드 개체로, 아파트 모델 개체, 자유 스레드 모델 개체 또는 자유 스레드 및 아파트 모델 개체를 만드는 데 사용할 수 있습니다.

이 섹션에서 다루는 항목은 다음과 같습니다.

- [템플릿 라이브러리](../atl/using-a-template-library.md)가 표준 라이브러리와 다른 점.

- [ATL로 할 수 있는 일과 할 수 없는 일](../atl/scope-of-atl.md)

- [ATL과 MFC 중 선택을 위한 권장 사항](../atl/recommendations-for-choosing-between-atl-and-mfc.md)

## <a name="see-also"></a>참고자료

[COM 및 ATL 소개](../atl/introduction-to-com-and-atl.md)
