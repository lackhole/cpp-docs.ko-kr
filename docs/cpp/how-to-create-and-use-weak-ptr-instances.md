---
title: '방법: weak_ptr 인스턴스 만들기 및 사용'
ms.custom: how-to
ms.date: 07/12/2018
ms.topic: conceptual
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
ms.openlocfilehash: 1a0e2880e97a77a0c9975553631a6024072745f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184703"
---
# <a name="how-to-create-and-use-weakptr-instances"></a>방법: weak_ptr 인스턴스 만들기 및 사용

개체의 기본 개체에 액세스 하는 방법을 저장 해야 경우에 따라는 `shared_ptr` 참조 횟수를 증가 시킬 없이 합니다. 사이 순환 참조가 있는 경우 이러한 상황이 발생 하는 일반적으로 `shared_ptr` 인스턴스.

가장 적합 한 디자인 가능할 때마다 포인터의 공유 소유권을 방지 하기 위해서입니다. 그러나 소유권을 공유 해야 하는 경우 `shared_ptr` 인스턴스 간의 순환 참조를 방지 합니다. 사용 하 여 경우 순환 참조를 피할 수 없거나 더 적합할 이유로 `weak_ptr` 소유자 중 하나 이상을 다른에 대 한 약한 참조를 제공 `shared_ptr`합니다. 사용 하 여는 `weak_ptr`를 만들 수 있습니다는 `shared_ptr` 기본 메모리 리소스가 여전히 유효한 경우만 관련 인스턴스의 기존 집합에 조인 하 합니다. `weak_ptr` 자체 참조 횟수에 참여 하지 않습니다 하 고 따라서이를 0으로 이동 참조 횟수를 막을 수 없습니다. 사용할 수 있습니다는 `weak_ptr` 의 새 복사본을 얻으려고 시도 하는 `shared_ptr` 초기화 되었습니다. 메모리가 이미 삭제 된 경우는 `bad_weak_ptr` 예외가 throw 됩니다. 메모리가 계속 유효한 경우 새 공유 포인터가 참조 횟수를 증가 하 고 메모리 유효한 되도록 보장으로 `shared_ptr` 변수 범위에 유지 됩니다.

## <a name="example"></a>예제

다음 코드 예제에서는 경우를 보여 줍니다. 여기서 `weak_ptr` 순환 종속성이 있는 개체의 적절 한 삭제를 확인 하는 데 사용 됩니다. 예를 살펴보면 대체 솔루션으로 간주 된 후에 생성 된 것으로 가정 합니다. `Controller` 개체는 컴퓨터 프로세스의 일부 측면을 나타내고 독립적으로 작동할 것입니다. 각 컨트롤러는 언제 든 지 다른 컨트롤러의 상태를 쿼리할 수 있어야 합니다. 포함 하 고 각 하나의 개인 `vector<weak_ptr<Controller>>` 이 목적입니다. 각 벡터에 순환 참조가 포함 되어 있으므로 `weak_ptr` 인스턴스가 대신 사용 됩니다 `shared_ptr`합니다.

[!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]

```Output
Creating Controller0
Creating Controller1
Creating Controller2
Creating Controller3
Creating Controller4
push_back to v[0]: 1
push_back to v[0]: 2
push_back to v[0]: 3
push_back to v[0]: 4
push_back to v[1]: 0
push_back to v[1]: 2
push_back to v[1]: 3
push_back to v[1]: 4
push_back to v[2]: 0
push_back to v[2]: 1
push_back to v[2]: 3
push_back to v[2]: 4
push_back to v[3]: 0
push_back to v[3]: 1
push_back to v[3]: 2
push_back to v[3]: 4
push_back to v[4]: 0
push_back to v[4]: 1
push_back to v[4]: 2
push_back to v[4]: 3
use_count = 1
Status of 1 = On
Status of 2 = On
Status of 3 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 2 = On
Status of 3 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 1 = On
Status of 3 = On
Status of 4 = On
use_count = 1
Status of 0 = O
nStatus of 1 = On
Status of 2 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 1 = On
Status of 2 = On
Status of 3 = On
Destroying Controller0
Destroying Controller1
Destroying Controller2
Destroying Controller3
Destroying Controller4
Press any key
```

삼아 벡터를 수정 `others` 되도록를 `vector<shared_ptr<Controller>>`, 그리고 출력에서 없는 소멸자를 호출 하는 경우 `TestRun` 반환 합니다.

## <a name="see-also"></a>참고자료

[스마트 포인터(모던 C++)](../cpp/smart-pointers-modern-cpp.md)
