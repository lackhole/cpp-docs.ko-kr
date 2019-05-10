---
title: 보관을 통해 CObject 저장 및 로드
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 591ce7032aa3d70b1e5a020cd9173ed4c9d0fa9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306771"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>보관을 통해 CObject 저장 및 로드

저장 및 로드 `CObject`보관 저장소를 통해 추가 고려 사항이 필요 합니다. 특정 경우에 호출 해야 합니다 `Serialize` 함수 개체의 위치를 `CArchive` 개체가 매개 변수를 `Serialize` 호출을 사용 하 여 달리를 **< \<** 또는 **>>** 운영자는 `CArchive`합니다. 중요 한 사실에 유의 합니다 `CArchive` **>>** 연산자 구문을 합니다 `CObject` 기반으로 메모리에 `CRuntimeClass` 보관 파일을 저장 하 여 파일에 이전에 기록 된 정보.

따라서 사용할지는 `CArchive` **< \<** 하 고 **>>** 호출 비교 연산자 `Serialize`, 여부에 따라 달라 집니다 있습니다 *필요* 개체를 다시 생성할 때 동적으로 로드 보관 파일을 기반으로 이전에 저장 된 `CRuntimeClass` 정보입니다. 사용 된 `Serialize` 다음과 같은 경우에는 함수:

- 개체를 역직렬화 하는 경우 개체의 정확한 클래스 미리 알고 있습니다.

- 개체를 역직렬화 하는 경우 할당 된 메모리를 이미 있습니다.

> [!CAUTION]
>  사용 하 여 개체를 로드 하는 경우는 `Serialize` 함수를 사용 하 여 개체도 저장 해야 합니다 `Serialize` 함수. 사용 하 여 저장 하지는 `CArchive` **<<** 연산자 및 사용 하 여 다음 부하를 `Serialize` 함수를 사용 하 여 저장소 또는 합니다 `Serialize` 함수를 사용 하 여를 로드 한 다음 `CArchive >>` 연산자.

다음 예에서는 사례를 보여 줍니다.

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

요약 하자면, serializable 클래스 정의 포함 하는 경우 `CObject` 해야를 멤버로 *하지* 사용 합니다 `CArchive` **< \<** 및 **>>** 해당 개체에 대 한 연산자 호출 해야 하지만 `Serialize` 함수를 대신 합니다. 또한 serializable 클래스에 대 한 포인터를 정의 하는 경우는 `CObject` (에서 파생 된 개체 또는 `CObject`) 멤버 하지만 구문 자체 생성자에서이 다른 개체도 호출 해야 `Serialize`합니다.

## <a name="see-also"></a>참고자료

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
