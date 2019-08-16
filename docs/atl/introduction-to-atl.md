---
title: ATL 소개
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM objects, creating in ATL
- ATL
ms.assetid: 77f565e8-c4ec-4a80-af4b-7278fcfe5c98
ms.openlocfilehash: 5eba816bc87eeebea2c41489a5d15c48645739e8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492103"
---
# <a name="introduction-to-atl"></a>ATL 소개

ATL은 작고 빠른 콤포넌트 개체 모델(COM) 개체를 쉽게 만들 수 있는 템플릿 기반 C++ 클래스 집합인 액티브 템플릿 라이브러리입니다. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown), [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory), [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) 및 `IDispatch`의 각자 구현을 포함하여 주요 COM 기능에 대한 특별한 지원을 제공합니다. 특별한 지원에는 이중 인터페이스, 표준 COM 열거자 인터페이스, 연결 지점, 분리 인터페이스(tear-off interfaces), 액티브X 컨트롤이 포함됩니다.

ATL 코드를 사용 하 여 단일 스레드 개체, 아파트 모델 개체, 자유 스레드된 모델 개체 또는 자유 스레드된 모델과 아파트 모델 개체를 만들 수 있습니다.

이 섹션에서 다루는 항목은 다음과 같습니다.

- [템플릿 라이브러리](../atl/using-a-template-library.md)가 표준 라이브러리와 다른 점.

- [ATL로 할 수 있는 일과 할 수 없는 일](../atl/scope-of-atl.md)

- [ATL과 MFC 중 선택을 위한 권장 사항](../atl/recommendations-for-choosing-between-atl-and-mfc.md)

## <a name="see-also"></a>참고자료

[COM 및 ATL 소개](../atl/introduction-to-com-and-atl.md)
