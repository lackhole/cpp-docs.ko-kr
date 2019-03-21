---
title: nonextensible 특성
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: cc57acb8bd7bc3e32c764606da651f57316ceabf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811851"
---
# <a name="nonextensible-attribute"></a>nonextensible 특성

런타임 시 이중 인터페이스를 확장 하지는 경우 (메서드 또는 속성을 통해 제공 하지 않습니다, `IDispatch::Invoke` vtable을 통해 사용할 수 없는)를 적용 해야 합니다 **nonextensible** 특성을 사용자 인터페이스 정의 합니다. 이 특성을 사용 하면 컴파일 시간에 전체 코드가 확인을 사용 하도록 설정 하는 클라이언트 언어 (예: Visual Basic)를 설명 합니다. 이 특성을 제공 하지 않으면 런타임까지 버그 클라이언트 코드에서 숨김 상태로 유지 될 수 있습니다.

에 대 한 자세한 합니다 **nonextensible** 특성과 예제를 참조 하십시오 [nonextensible](../windows/nonextensible.md)합니다.

## <a name="see-also"></a>참고자료

[이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)
