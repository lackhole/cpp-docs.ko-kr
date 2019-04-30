---
title: 템플릿 기반 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
ms.openlocfilehash: 40633c8b2b09d27e97443364ed3ce711ee217e18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306394"
---
# <a name="template-based-classes"></a>템플릿 기반 클래스

이 문서에서는 MFC 버전 3.0 이상에 형식이 안전한 템플릿 기반 컬렉션 클래스를 설명 합니다. 이러한 템플릿을 사용 하 여 형식이 안전한 컬렉션을 만드는 것이 더 편리 하 고 형식 안전성을 템플릿 기반 컬렉션 클래스를 사용 하 여 보다 효율적으로 제공할 수 있습니다.

MFC는 두 가지 범주의 템플릿 기반 컬렉션을 미리 정의 합니다.

- [단순 배열, 목록 및 맵 클래스](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [배열, 목록 및 형식화 된 포인터의 맵을](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

간단한 컬렉션 클래스는 모든 클래스에서 파생 됩니다 `CObject`serialization, 동적 생성 및 다른 속성을 상속 하므로 `CObject`합니다. 형식화 된 포인터 컬렉션 클래스에서 파생 하는 클래스를 지정 해야-같은 MFC에서 미리 정의 된 비템플릿 포인터 컬렉션 중 하나인 `CPtrList` 또는 `CPtrArray`합니다. 지정된 된 기본 클래스에서 상속 되는 새 컬렉션 클래스 및 형식 안전성을 적용 하는 기본 클래스 멤버에 캡슐화 된 호출을 사용 하는 새 클래스의 멤버 함수입니다.

에 대 한 자세한 내용은 C++ 을 참조 하십시오 [템플릿](../cpp/templates-cpp.md) 에  *C++ 언어 참조*.

##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> 단순 배열, 목록 및 맵 템플릿을 사용 하 여

템플릿을 사용 하 여 간단한 컬렉션을 알아야 컬렉션 선언에서 사용할 매개 변수 및 데이터 종류에 따라 이러한 컬렉션에 저장할 수 있습니다.

###  <a name="_core_simple_array_and_list_usage"></a> 간단한 배열 및 목록 사용

간단한 배열 및 목록 클래스 [CArray](../mfc/reference/carray-class.md) 하 고 [CList](../mfc/reference/clist-class.md), 두 개의 매개 변수: *형식* 고 `ARG_TYPE`입니다. 이러한 클래스에서 지정 하는 모든 데이터 형식에 저장할 수는 *형식* 매개 변수:

- 기본 C++ 와 같은 데이터 형식을 **int**합니다 **char**, 및 **float**

- C++구조체와 클래스

- 정의 하는 다른 형식

편의성 및 효율성을 사용할 수 있습니다 합니다 *ARG_TYPE* 함수 인수의 형식을 지정 하려면 매개 변수입니다. 일반적으로 지정할 *ARG_TYPE* 에 명명 된 형식에 대 한 참조를 *형식* 매개 변수입니다. 예를 들어:

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

첫 번째 예제에서는 배열 컬렉션을 선언 `myArray`를 포함 하는 **int**s입니다. 두 번째 예에서는 목록 컬렉션을 선언 `myList`를 저장 하는 `CPerson` 개체입니다. 지정 된 형식의 인수를 사용 하는 컬렉션 클래스의 특정 멤버 함수는 *ARG_TYPE* 템플릿 매개 변수입니다. 예를 들어 합니다 `Add` 클래스의 멤버 함수 `CArray` 사용을 *ARG_TYPE* 인수:

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

###  <a name="_core_simple_map_usage"></a> 단순 맵 사용

단순 맵 클래스 [CMap](../mfc/reference/cmap-class.md), 4 개의 매개 변수를 사용 합니다. *키*, *ARG_KEY*합니다 *값*, 및 *ARG_VALUE*합니다. Array와 list 클래스와 마찬가지로 맵 클래스에는 모든 데이터 형식을 저장할 수 있습니다. 배열 및 인덱스를 저장 하는 데이터를 정렬 하는 목록과 달리 맵은 키와 값: 값의 연결 된 키를 지정 하 여 지도에 저장 된 값에 액세스할 수 있습니다. 합니다 *키* 매개 변수는 맵에 저장 된 데이터에 액세스 하는 데 사용 하는 키의 데이터 형식을 지정 합니다. 경우 유형의 *키* 구조체 또는 클래스는 *ARG_KEY* 매개 변수는 일반적으로 지정 된 형식에 대 한 참조가 *키*합니다. 합니다 *값* 매개 변수는 맵에 저장 된 항목의 형식을 지정 합니다. 경우 유형의 *ARG_VALUE* 구조체 또는 클래스는 *ARG_VALUE* 매개 변수는 일반적으로 지정 된 형식에 대 한 참조가 *값*합니다. 예를 들어:

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

첫 번째 예제에서는 저장소 `MY_STRUCT` 값, 액세스 하 여 이들 **int** 키 및 액세스 하는 반환 `MY_STRUCT` 참조 항목입니다. 두 번째 예제에서는 저장소 `CPerson` 값, 액세스 하 여 `CString` 키 및 액세스 한 항목에 대 한 참조를 반환 합니다. 이 예제를 보면 사람을 성을 기준으로 간단한 주소록을 나타낼 수 있습니다.

때문에 합니다 *키* 매개 변수는 형식 `CString` 하며 *KEY_TYPE* 매개 변수는 형식 `LPCSTR`, 키 항목 유형으로 map에 저장 됩니다 `CString` 되지만에서 참조 됩니다 와 같은 함수 `SetAt` 형식의 포인터를 통해 `LPCSTR`합니다. 예를 들어:

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> 형식화 된 포인터 컬렉션 템플릿을 사용 하 여

템플릿을 사용 하 여 형식화 된 포인터 컬렉션을 이러한 컬렉션에 저장할 수 어떤 종류의 데이터 및 컬렉션 선언에서 사용할 매개 변수를 지정 해야 합니다.

###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> 형식화 된 포인터 배열 및 목록 사용

형식화 된 포인터 배열 및 목록 클래스 [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) 하 고 [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), 두 개의 매개 변수: *BASE_CLASS* 하 고 *형식*합니다. 이러한 클래스에서 지정 하는 모든 데이터 형식에 저장할 수는 *형식* 매개 변수입니다. 포인터를 저장 하는 비템플릿 컬렉션 클래스 중 하나에서 파생 되므로 이 기본 클래스를 지정할 *BASE_CLASS*합니다. 배열에 대 한 중 하나를 사용 `CObArray` 또는 `CPtrArray`합니다. 목록에 대 한 중 하나를 사용 `CObList` 또는 `CPtrList`합니다.

기반으로 하는 컬렉션을 선언 하는 경우 가정해 실제로 `CObList`, 새 클래스 뿐 아니라, 기본 클래스의 멤버를 상속 하지만 함수 및 연산자를 캡슐화 하 여 형식 안전성을 제공 하는 데 도움이 되는 다양 한 추가 형식이 안전한 멤버 선언 기본 클래스 멤버를 호출 합니다. 모든 필요한 형식 변환을 관리 하는 이러한 캡슐화 합니다. 예를 들어:

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

첫 번째 예제는 형식화 된 포인터 배열 선언 `myArray`에서 파생 된 `CObArray`합니다. 저장 하 고에 대 한 포인터를 반환 하는 배열 `CPerson` 개체 (여기서 `CPerson` 클래스에서 파생 `CObject`). 호출할 수 있습니다 `CObArray` 멤버 함수 또는 하면 새 형식이 안전한을 호출할 수 `GetAt` 및 `ElementAt` 함수 또는 형식이 안전한을 사용 하 여 **[ ]** 연산자입니다.

두 번째 예에서는 형식화 된 포인터 목록을 선언 `myList`에서 파생 된 `CPtrList`합니다. 저장 하 고에 대 한 포인터를 반환 하는 목록 `MY_STRUCT` 개체입니다. 클래스에 따라 `CPtrList` 에서 파생 되지 않은 개체에 대 한 포인터를 저장 하는 데는 `CObject`합니다. `CTypedPtrList` 형식이 안전한 멤버 함수의 번호가: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`를 `GetPrev`, 및 `GetAt`합니다.

###  <a name="_core_typed.2d.pointer_map_usage"></a> 형식화 된 포인터 맵 사용

형식화 된 포인터 map 클래스 [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), 세 개의 매개 변수를 사용 합니다. *BASE_CLASS*하십시오 *키*, 및 *값*합니다. *BASE_CLASS* 새 클래스를 파생할 클래스를 지정 하는 매개 변수: `CMapPtrToWord`, `CMapPtrToPtr`를 `CMapStringToPtr`를 `CMapWordToPtr`, `CMapStringToOb`등. *키* 비슷합니다 *키* 에서 `CMap`: 조회에 사용 된 키의 형식을 지정 합니다. *값* 비슷합니다 *값* 에서 `CMap`: Map에 저장 하는 개체의 형식을 지정 합니다. 예를 들어:

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

첫 번째 예제는 기준으로 지도 `CMapPtrToPtr` -사용 하 여 `CString` 에 대 한 포인터에 매핑된 키 `MY_STRUCT`합니다. 형식 안전을 호출 하 여 저장 된 포인터를 조회할 수 있습니다 `Lookup` 멤버 함수입니다. 사용할 수는 **[ ]** 연산자를 저장 된 포인터를 조회 하 고 추가 찾을 수 없는 경우. 형식이 안전한을 사용 하 여 지도 반복할 수 있습니다 및 `GetNextAssoc` 함수입니다. 또한 함수를 호출할 수 다른 멤버 클래스의 `CMapPtrToPtr`합니다.

두 번째 예제는 기준으로 지도 `CMapStringToOb` -에 대 한 저장 된 포인터에 매핑된 문자열 키를 사용 하 여 `CMyObject` 개체입니다. 이전 단락에서 설명 하는 동일한 형식이 안전한 멤버를 사용할 수 있습니다 하거나 클래스의 멤버를 호출할 수 있습니다 `CMapStringToOb`합니다.

> [!NOTE]
>  지정 하는 경우는 **클래스** 또는 **구조체** 입력 합니다 *값* 매개 변수 대신 포인터 또는 형식, 클래스 또는 구조체에 대 한 참조는 복사 생성자가 있어야 합니다.

자세한 내용은 [형식이 안전한 컬렉션을 만드는 방법](../mfc/how-to-make-a-type-safe-collection.md)합니다.

## <a name="see-also"></a>참고자료

[컬렉션](../mfc/collections.md)
