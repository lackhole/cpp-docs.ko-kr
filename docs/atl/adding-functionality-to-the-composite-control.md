---
title: 복합 컨트롤에 기능 추가
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 9ad7ef3d80579804ac614fbefac1a042a9cf2fba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252496"
---
# <a name="adding-functionality-to-the-composite-control"></a>복합 컨트롤에 기능 추가

사용자가 복합 컨트롤에 필요한 모든 컨트롤을 삽입 한 후 다음 단계는 새 기능을 추가 해야 합니다. 이 새로운 기능은 일반적으로 두 가지 범주로 나누어 집니다.

- 추가 인터페이스를 지원 하 고 특정 추가 기능을 사용 하 여 복합 컨트롤의 동작을 사용자 지정 합니다.

- 포함 된 ActiveX 컨트롤 (또는 컨트롤)에서 보낸 이벤트를 처리 합니다.

용도이 문서의 범위에 대 한이 섹션의 나머지 부분에서는 ActiveX 컨트롤에서 보낸 이벤트 처리에 중점을 둡니다.

> [!NOTE]
>  Windows 컨트롤에서 메시지를 처리 하는 경우 참조 [창 구현](../atl/implementing-a-window.md) ATL에서 처리 하는 메시지에 대 한 자세한 내용은

ActiveX 컨트롤을 대화 상자 리소스에서를 삽입 한 후 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이벤트 처리기 추가**합니다. 이벤트를 처리 하 고 클릭 하려는 선택 **추가 및 편집**합니다. 이벤트 처리기 코드를 컨트롤의.h 파일에 추가 됩니다.

복합 컨트롤의 ActiveX 컨트롤에 대 한 연결 지점을 자동으로 연결 되 고 호출을 통해 연결 끊김 [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)합니다.

## <a name="see-also"></a>참고자료

[복합 컨트롤 기본 사항](../atl/atl-composite-control-fundamentals.md)
