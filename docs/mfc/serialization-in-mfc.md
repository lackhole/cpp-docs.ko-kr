---
title: MFC의 Serialization
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 5c7dec140635b6d83bdae936d1bb0cef144f825b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308215"
---
# <a name="serialization-in-mfc"></a>MFC의 Serialization

이 문서는 프로그램의 실행에 MFC Microsoft Foundation Class 라이브러리 () 개체 사이 지속할 수 있도록 제공 하는 serialization 메커니즘을 설명 합니다.

Serialization은 쓰거나 읽을 하거나 개체 디스크 파일과 같은 영구 저장 매체에서의 프로세스입니다. Serialization은 구조화 된 데이터의 상태를 유지 하기 위해 필요한 경우에 이상적 (같은 C++ 클래스 또는 구조체) 중 이나 후 프로그램을 실행 합니다. MFC에서 제공 된 serialization 개체를 사용 하 여이 사용자의 파일 작업을 수동으로 수행 해야 하므로 표준 및 일관 된 방식으로 발생할 수 있습니다.

MFC 클래스의 serialization에 대 한 기본 제공 지원을 제공 `CObject`합니다. 모든 클래스에서 파생 되는 따라서 `CObject` 활용 `CObject`의 serialization 프로토콜입니다.

Serialization의 기본 개념 된다는 개체는 일반적으로 영구 저장소에 자체 멤버 변수를 값으로 표시 된 현재 상태를 기록할 수 있습니다. 나중에 개체는 읽거나 저장소에서 개체의 상태를 역직렬화 하 여 다시 만들 수 있습니다. Serialization은 개체 포인터 및 개체를 serialize 할 때 사용 되는 개체에 대 한 순환 참조의 모든 세부 정보를 처리 합니다. 요점은 개체 자체는 읽기 및 자체의 상태를 작성 하는 일을 담당 합니다. 따라서 직렬화 가능 하 게 클래스에 대 한 기본 serialization 작업을 구현 해야 합니다. 문서의 Serialization 그룹에 표시 된 것과 같이 클래스에이 기능을 추가 하기 쉽습니다.

MFC의 개체를 사용 하는 `CArchive` serialize 될 개체 및 저장소 매체 간의 중개자로 클래스입니다. 이 개체는 항상 연결을 `CFile` 읽기 또는 쓰기 요청된 된 작업 인지 및 파일 이름을 포함 하는 serialization에 대 한 필요한 정보를 얻을 수 있는 개체입니다. Serialization 작업을 수행 하는 개체를 사용할 수는 `CArchive` 저장소 매체의 특성에 관계 없이 개체입니다.

A `CArchive` 오버 로드 된 삽입을 사용 하 여 개체 (**<\<**) 및 추출 (**>>**) 쓰기 및 읽기 작업을 수행 하는 연산자입니다. 자세한 내용은 [저장 및 보관을 통해 Cobject 로드](../mfc/storing-and-loading-cobjects-via-an-archive.md) Serialization 문서에서: 개체를 직렬화 합니다.

> [!NOTE]
>  혼동 하지 마십시오는 `CArchive` 클래스는 범용 iostream 클래스를 사용 하 여 서식 있는 텍스트만 합니다. `CArchive` 클래스는 이진 형식의 serialize 된 개체입니다.

원하는 경우에 영구 데이터 저장소에 대 한 사용자 고유의 메커니즘을 만들기 위한 MFC serialization을 무시할 수 있습니다. 사용자의 명령 직렬화를 시작 하는 클래스 멤버 함수를 재정의 해야 합니다. 설명을 참조 하세요 [Technical Note 22](../mfc/tn022-standard-commands-implementation.md) ID_FILE_OPEN, ID_FILE_SAVE, 및 ID_FILE_SAVE_AS 표준 명령입니다.

다음 문서를 직렬화 하는 데 필요한 두 가지 주요 작업을 설명 합니다.

- [Serialization: 직렬화할 수 있는 클래스 만들기](../mfc/serialization-making-a-serializable-class.md)

- [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)

문서 [직렬화 합니다. Serialization 및 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md) 경우 직렬화는 데이터베이스 응용 프로그램에 적절 한 입/출력 기술에 설명 합니다.

## <a name="see-also"></a>참고자료

[개념](../mfc/mfc-concepts.md)<br/>
[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CArchive 클래스](../mfc/reference/carchive-class.md)<br/>
[CObject 클래스](../mfc/reference/cobject-class.md)<br/>
[CDocument 클래스](../mfc/reference/cdocument-class.md)<br/>
[CFile 클래스](../mfc/reference/cfile-class.md)
