---
title: 파일로/파일에서 데이터 Serialize
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: af3cde9445ae4b128e7e54a5f154db01b2eecd3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308073"
---
# <a name="serializing-data-to-and-from-files"></a>파일로/파일에서 데이터 Serialize

지 속성의 기본 개념은 개체의 영구 저장소에 자체 멤버 변수를 값으로 표시 된 현재 상태를 쓸 수 있어야 합니다. 나중에 개체는 읽거나 "역직렬화," 영구 저장소에서 개체의 상태에서 다시 만들 수 있습니다. 여기서 중요 한 점은 점 개체 자체가 읽기 및 쓰기 자체의 상태에 대 한 책임입니다. 따라서 유지 하는 클래스에 대 한 기본 serialization 작업을 구현 해야 합니다.

프레임 워크에 대 한 응답에 디스크 파일에 문서를 저장 하는 것에 대 한 기본 구현을 제공 하 고 디스크 파일 열기 명령에 대 한 응답에서에서 문서를 로드 한 파일 메뉴에서 다른 이름으로 저장 명령을 합니다. 매우 적은 노력을 사용 하 여 파일에서 해당 데이터를 읽고 쓰는 데는 문서의 기능을 구현할 수 있습니다. 해야 할 중요 한 점은 재정의가 합니다 [직렬화](../mfc/reference/cobject-class.md#serialize) 문서 클래스에서 멤버 함수입니다.

MFC 응용 프로그램 마법사의 기본 재정의 저장 합니다 `CDocument` 멤버 함수 `Serialize` 문서 클래스를 만듭니다. 응용 프로그램의 멤버 변수를 구현한 후 채울 수 있습니다 프로그램 `Serialize` "보관 개체" 파일에 연결 된 데이터를 전송 하는 코드를 사용 하 여 재정의 합니다. [CArchive](../mfc/reference/carchive-class.md) 개체는 비슷합니다는 **cin** 및 **cout** 입/출력에서 개체를 C++ iostream 라이브러리. 그러나 `CArchive` 이진 형식으로 포맷된 되지 않은 텍스트를 읽고 씁니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [serialization](../mfc/serialization-in-mfc.md)

- [Serialization의 문서 역할](#_core_the_document.92.s_role_in_serialization)

- [Serialization에서 데이터의 역할](#_core_the_data.92.s_role_in_serialization)

- [Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)

##  <a name="_core_the_document.92.s_role_in_serialization"></a> Serialization의 문서 역할

저장 및 다른 이름으로 저장 명령 문서를 호출 하 여 프레임 워크의 파일 메뉴 열기를 자동으로 응답 `Serialize` 구현 되는 경우 멤버 함수입니다. ID_FILE_OPEN 명령 예를 들어, 응용 프로그램 개체의 처리기 함수를 호출합니다. 이 과정에서 사용자에 게 표시 하 고 파일 열기 대화 상자에 응답 하 고 프레임 워크는 사용자가 선택한 파일 이름을 가져옵니다. 프레임 워크 만듭니다는 `CArchive` 개체 설정 문서에 데이터를 로드 하 고 보관 파일을 전달 `Serialize`합니다. 프레임 워크에 이미 파일을 열었습니다. 문서에 코드 `Serialize` 멤버 함수는 필요에 따라 데이터 개체를 다시 구성, 보관 저장소를 통해 데이터를 읽습니다. Serialization에 대 한 자세한 내용은 문서를 참조 하세요 [Serialization](../mfc/serialization-in-mfc.md)합니다.

##  <a name="_core_the_data.92.s_role_in_serialization"></a> Serialization에서 데이터의 역할

일반적으로 클래스 형식의 데이터 자체를 serialize 할 수 있어야 합니다. 즉, 보관 파일에 개체를 전달 하면 개체 자체 보관 파일에 작성 하는 방법 및 보관 파일에서 읽는 방법을 알고 있어야 합니다. MFC는 클래스를 이러한 방식으로 직렬화 하기 위한 지원을 제공 합니다. Serialization에 대 한 데이터 형식을 정의 하는 클래스를 디자인할 경우 해당 형식의 데이터를 직렬화 하려는 디자인 합니다.

## <a name="see-also"></a>참고자료

[문서 사용](../mfc/using-documents.md)
