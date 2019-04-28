---
title: CArchive 개체를 만드는 두 가지 방법
ms.date: 11/04/2016
f1_keywords:
- CArchive
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 80e3e73840bce53691c3f5fdafb62c60bdb8f832
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181512"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive 개체를 만드는 두 가지 방법

두 가지 방법으로 만들려면를 `CArchive` 개체:

- [CArchive 개체 프레임 워크를 통해 암시적 생성](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive 개체의 명시적 만들기](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> CArchive 개체 프레임 워크를 통해 암시적 생성

가장 일반적이 고, 가장 쉬운 방법은 만드는 프레임 워크는 `CArchive` 저장, 다른 이름으로 저장 및 열기 명령을 파일 메뉴를 대신 하 여 문서에 대 한 개체입니다.

프레임 워크 응용 프로그램의 사용자 이름으로 저장 명령을 파일 메뉴에서를 실행 하는 경우는 다음과 같습니다.

1. 제공 된 **다른 이름으로 저장** 대화 상자 사용자 로부터 파일 이름을 가져옵니다.

1. 사용자에 게으로 라는 파일을 열어서를 `CFile` 개체입니다.

1. 만듭니다는 `CArchive` 이 가리키는 개체 `CFile` 개체입니다. 만드는 `CArchive` 개체에 "store" 모드를 설정 하는 프레임 워크 (쓰기, 직렬화) "로드" 달리 (읽기, 역직렬화) 합니다.

1. 호출을 `Serialize` 에 정의 된 함수에 `CDocument`-파생 클래스에 대 한 참조를 전달 합니다 `CArchive` 개체입니다.

문서의 `Serialize` 함수에는 다음 데이터를 쓰는 `CArchive` 곧 설명 했 듯이 개체입니다. 반환 될 때 사용자 `Serialize` 함수를 프레임 워크를 제거 합니다 `CArchive` 개체 차례로 `CFile` 개체.

따라서 만드는 프레임 워크를 사용 하는 경우는 `CArchive` 문서를 구현 하는 수행 해야 하는 모든 문서에 대 한 개체 `Serialize` 쓰고 보관 파일에서 읽고 함수입니다. 구현할 필요가 `Serialize` 에 대 한 `CObject`-파생 개체는 문서의 `Serialize` 함수는 다시 직접 또는 간접적으로 직렬화 합니다.

##  <a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive 개체의 명시적 만들기

프레임 워크를 통해 문서를 직렬화 하는 작업을 하는 것 외에도 다른 경우가 있습니다 필요할 때를 `CArchive` 개체입니다. 나타내는 클립보드에 데이터를 serialize 하려는 하는 예를 들어, 한 `CSharedFile` 개체입니다. 또는 프레임 워크에서 제공 하는 것과에서 다른 파일을 저장 하기 위한 사용자 인터페이스를 사용 하는 것이 좋습니다. 이 경우 명시적으로 만들면를 `CArchive` 개체입니다. 이렇게 하면 프레임 워크는 동일한 방식으로 다음 절차를 사용 합니다.

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive 개체를 명시적으로 만들려면

1. 생성 된 `CFile` 에서 파생 된 개체 또는 개체 `CFile`합니다.

1. 전달 된 `CFile` 개체에 대 한 생성자를 `CArchive`다음 예제에서와 같이:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   두 번째 인수는 `CArchive` 생성자는 저장 또는 로드 하거나 데이터 파일에 대 한 보관 파일을 사용할지 여부를 지정 하는 열거형된 값입니다. 합니다 `Serialize` 개체의 함수를 호출 하 여이 상태를 확인 합니다 `IsStoring` 보관 개체에 대 한 함수입니다.

마쳤으면 저장 하거나 데이터를 로드 하는 `CArchive` 개체를 닫아야 합니다. 하지만 합니다 `CArchive` (및 `CFile`) 개체는 자동으로 닫고 보관 파일 (파일), 명시적으로 쉽게 오류를 복구 하므로 이렇게 하는 것이 좋습니다. 오류 처리에 대 한 자세한 내용은 문서를 참조 하세요. [예외: 예외 catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.

#### <a name="to-close-the-carchive-object"></a>CArchive 개체

1. 다음 예제를 종결 하는 방법의 `CArchive` 개체:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>참고자료

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
