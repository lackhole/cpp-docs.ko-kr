---
title: 참조 횟수 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: fa160cb40af632321e1b14fd3ca88a4dd578b972
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249654"
---
# <a name="reference-counting"></a>참조 계산

COM 자체는 더 이상 사용되지 않는다고 판단하는 경우 자동으로 메모리에서 개체를 제거하는 것을 시도하지 않습니다. 대신 개체 프로그래머가 사용되지 않는 개체를 제거해야 합니다. 프로그래머는 참조 횟수에 따라 개체 제거 여부를 결정합니다.

COM은 개체의 인터페이스 참조 횟수 관리를 위해 `IUnknown` 메서드인 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)와 [Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)를 사용합니다. 이러한 메서드를 호출하는 것에 대한 일반 규칙은 다음과 같습니다.

- 클라이언트가 인터페이스 포인터를 받을 때마다 인터페이스에서 `AddRef`를 호출해야 합니다.	

- 클라이언트는 인터페이스 포인터 사용을 완료한 후 `Release`를 호출해야 합니다.

이는 간단한 구현 사항으로, `AddRef`를 호출할 경우 개체 내의 카운터 변수가 증가하고 `Release`의 경우는 감소합니다. 카운트가 0이 되면 인터페이스를 사용하는 사람이 없다는 것이므로 메모리에서 자신을 제거할 수 있습니다.

개체(개별 인터페이스가 아닌)에 대한 각 참조가 계산되도록 참조 카운팅을 구현할 수도 있습니다. 이 경우 각 `AddRef` 및 `Release`는 개체의 중앙 구현에 대리자를 호출하고 `Release`는 참조 횟수가 0이 될 때 전체 개체를 제거합니다.	

> [!NOTE]

> **new** 연산자를 사용하여 `CComObject`-파생 개체를 생성하면 참조 횟수는 0입니다. 따라서 `CComObject`-파생 개체를 성공적으로 만든 후 `AddRef`를 호출해야 합니다.


## <a name="see-also"></a>참고자료

[COM 소개](../atl/introduction-to-com.md)<br/>
[참조 횟수를 통해 개체 수명 관리](/windows/desktop/com/managing-object-lifetimes-through-reference-counting)
