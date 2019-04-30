---
title: 'Serialization: Serializable 클래스 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: 995744381c8f82dc637e4aa0452e37af170b168b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308103"
---
# <a name="serialization-making-a-serializable-class"></a>Serialization: Serializable 클래스 만들기

5 가지 주요 단계 클래스를 직렬화 가능 해야 합니다. 아래 나열 되 고 다음 섹션에서 설명 합니다.

1. [CObject에서 클래스를 파생](#_core_deriving_your_class_from_cobject) (또는 일부 클래스에서 파생 된 `CObject`).

1. [직렬화 멤버 함수를 재정의](#_core_overriding_the_serialize_member_function)합니다.

1. [DECLARE_SERIAL 매크로 사용 하 여](#_core_using_the_declare_serial_macro) 클래스 선언에서.

1. [인수가 없는 생성자를 정의](#_core_defining_a_constructor_with_no_arguments)합니다.

1. [IMPLEMENT_SERIAL 매크로 사용 하 여 구현 파일에서](#_core_using_the_implement_serial_macro_in_the_implementation_file) 클래스에 대 한 합니다.

호출 하는 경우 `Serialize` 직접 통하지 않고는 >> 및 << 연산자 [CArchive](../mfc/reference/carchive-class.md), 마지막 세 단계를 serialization에 필요 하지 않습니다.

##  <a name="_core_deriving_your_class_from_cobject"></a> CObject에서 클래스를 파생합니다.

기본 serialization 프로토콜 및 기능에 정의 된는 `CObject` 클래스입니다. 클래스를 파생 시켜 `CObject` (또는에서 파생 된 클래스 `CObject`) 클래스의 다음 선언에 나와 있는 것 처럼 `CPerson`, serialization 프로토콜 및 기능에 액세스할 수 `CObject`합니다.

##  <a name="_core_overriding_the_serialize_member_function"></a> 재정의 멤버 함수를 Serialize 합니다.

합니다 `Serialize` 에 정의 된 멤버 함수는 `CObject` 클래스는 실제로 개체의 현재 상태를 캡처하는 데 필요한 데이터를 직렬화 하는 일을 담당 합니다. 합니다 `Serialize` 함수에는 `CArchive` 개체 데이터 읽기 및 쓰기에 사용 되는 인수입니다. [CArchive](../mfc/reference/carchive-class.md) 개체에는 멤버 함수가 `IsStoring`를 나타내는 여부를 `Serialize` (데이터 쓰기)를 저장 하거나 (데이터 읽기)을 로드 하는 합니다. 결과 사용 하 여 `IsStoring` 으로 하거나 삽입할 개체의 데이터에는 `CArchive` 삽입 연산자를 사용 하 여 개체 (**<\<**) (추출연산자를사용하여데이터를추출하거나 **>>**).

클래스에서 파생 되는 것이 좋습니다 `CObject` 형식의 두 개의 새 멤버 변수 있고 `CString` 하 고 **WORD**합니다. 다음 클래스 선언을 보여 줍니다 새 멤버 변수 및 재정의 된 선언 `Serialize` 멤버 함수:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>직렬화 멤버 함수를 재정의 하려면

1. 기본 클래스 버전을 호출 `Serialize` 개체의 상속 된 부분이 serialize 되도록 해야 합니다.

1. 삽입 또는 클래스에 관련 된 멤버 변수를 추출 합니다.

   읽기 및 쓰기 데이터 보관 클래스를 사용 하 여 삽입 및 추출 연산자 상호 작용 합니다. 다음 예제에서는 구현 하는 방법을 보여 줍니다 `Serialize` 에 대 한는 `CPerson` 위의 클래스 선언:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

사용할 수도 있습니다는 [CArchive::Read](../mfc/reference/carchive-class.md#read) 및 [CArchive::Write](../mfc/reference/carchive-class.md#write) 대량의 형식화 되지 않은 데이터를 읽고 하는 멤버 함수입니다.

##  <a name="_core_using_the_declare_serial_macro"></a> DECLARE_SERIAL 매크로 사용 하 여

DECLARE_SERIAL 매크로 다음과 같이 직렬화를 지 원하는 클래스의 선언에 필요 합니다.

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

##  <a name="_core_defining_a_constructor_with_no_arguments"></a> 인수가 없는 생성자를 정의합니다.

MFC (디스크에서 로드) deserialize 될 때 개체를 다시 만들 때 기본 생성자가 필요 합니다. Deserialization 프로세스를 다시 개체를 만드는 데 필요한 값을 사용 하 여 모든 멤버 변수에서 채워집니다.

Public, protected 또는 private이 생성자를 선언할 수 있습니다. 만들면 protected 또는 private는 것만 사용할 serialization 함수가 있는지 확인 하는 것이 도움이 됩니다. 생성자는 필요한 경우 삭제할 수 있도록 하는 상태 개체를 배치 해야 합니다.

> [!NOTE]
>  DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로 사용 하는 클래스에서 인수가 없는 생성자를 정의 하는 것을 잊지 경우 IMPLEMENT_SERIAL 매크로 사용 되는 줄에서 "사용할 수 있는 기본 생성자 없음" 컴파일러 경고를 받습니다.

##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> IMPLEMENT_SERIAL 매크로 사용 하 여 구현 파일에서

IMPLEMENT_SERIAL 매크로 필요한 경우 클래스를 파생 하는 직렬화 가능에서 다양 한 함수를 정의 하는 데 사용 됩니다 `CObject`합니다. 이 매크로 사용 하 여 구현 파일에서 (합니다. CPP) 클래스에 대 한 합니다. 매크로에 처음 두 인수는 클래스의 이름과 즉시 기본 클래스의 이름입니다.

이 매크로에 세 번째 인수는 스키마입니다. 스키마 번호가 클래스의 개체에 대 한 버전 번호입니다. 스키마 개수에 0 보다 크거나 같은 정수를 사용 합니다. (데이터베이스 용어를 사용 하 여이 스키마 숫자를 혼동 하지 마세요.)

MFC serialization 코드를 메모리에 개체를 읽을 때 스키마 수를 확인 합니다. 라이브러리 시킵니다 디스크에 있는 개체의 스키마 번호가 메모리에서 클래스의 스키마 수와 일치 하지 않는 경우는 `CArchiveException`, 프로그램 개체의 잘못 된 버전을 읽을 수 없도록 방지 합니다.

원하는 경우 프로그램 `Serialize` 멤버 함수를 여러 버전을 읽을 수-응용 프로그램의 다른 버전으로 작성 하는 파일 즉,-값을 사용할 수 있습니다 *VERSIONABLE_SCHEMA* 는 IMPLEMENT_SERIAL 인수로 매크로입니다. 사용 정보 및 예제에 대 한 참조를 `GetObjectSchema` 클래스의 멤버 함수 `CArchive`합니다.

다음 예제에서는 IMPLEMENT_SERIAL 클래스를 사용 하는 방법을 보여 줍니다 `CPerson`, 즉에서 파생 된 `CObject`:

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

문서에 설명 된 대로 클래스의 개체를 serialize 할 수는 serializable 클래스를 만든 후 [직렬화 합니다. 개체를 직렬화](../mfc/serialization-serializing-an-object.md)합니다.

## <a name="see-also"></a>참고자료

[serialization](../mfc/serialization-in-mfc.md)
