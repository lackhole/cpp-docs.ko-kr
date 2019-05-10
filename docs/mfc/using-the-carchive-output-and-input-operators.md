---
title: CArchive를 사용 하 여 &lt; &lt; 하 고 &gt; &gt; 연산자
ms.date: 11/04/2016
f1_keywords:
- CArchive
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 9b4192e79b68388e45eb9837e056bbd881de2933
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411502"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive를 사용 하 여 &lt; &lt; 하 고 &gt; &gt; 연산자

`CArchive` 제공 <\< 고 >>를 쓰고 읽는 단순 데이터 형식에 대 한 연산자와 `CObject`의파일에서 합니다.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>보관을 통해 파일에 개체를 저장 하려면

1. 다음 예제에서는 보관을 통해 파일에 개체를 저장 하는 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>파일에서 이전에 저장 된 값에서 개체를 로드 하려면

1. 다음 예제에서는 이전에 파일에 저장 된 값에서 개체를 로드 하는 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

저장 하 고에서 보관을 통해 파일에서 데이터를 로드 하는 일반적으로 `Serialize` 함수의 `CObject`-파생 클래스에 DECLARE_SERIALIZE 매크로 사용 하 여 선언 해야 합니다. 에 대 한 참조를 `CArchive` 개체를 전달 하 여 `Serialize` 함수입니다. 호출 하는 `IsLoading` 함수는 `CArchive` 결정 하는 개체 있는지 여부를 `Serialize` 파일에서 데이터를 로드 하거나 파일로 데이터를 저장 기능을 호출 했습니다.

합니다 `Serialize` 직렬화 가능한 함수의 `CObject`-파생된 클래스에는 일반적으로 다음과 같은 형식을 갖습니다.

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

위의 코드 템플릿을 같습니다 정확 하 게 응용 프로그램 마법사에 대 한 만든 합니다 `Serialize` 문서의 함수 (클래스에서 파생 된 `CDocument`). 이 코드 템플릿 코드를 저장 및 로드 코드는 다음 예제와 같이 병렬 항상 해야 하기 때문에 검토 하기 쉬운 코드를 작성할 수 있습니다.

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

라이브러리 정의 **< \<** 하 고 **>>** 연산자에 대 한 `CArchive` 첫 번째 피연산자 다음 데이터 형식 및 두 번째 피연산자와 클래스 형식 :

||||
|-|-|-|
|`CObject*`|**크기** 및 `CSize`|**float**|
|**WORD**|`CString`|**지점** 및 `CPoint`|
|`DWORD`|**BYTE**|`RECT` 및 `CRect`|
|**Double**|**LONG**|`CTime` 및 `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  저장 및 로드 `CObject`보관 저장소를 통해 추가 고려 사항이 필요 합니다. 자세한 내용은 [저장 및 보관을 통해 Cobject 로드](../mfc/storing-and-loading-cobjects-via-an-archive.md)합니다.

**CArchive <\<**  및 **>>** 연산자에 대 한 참조를 항상 반환는 `CArchive` 개체 첫 번째 피연산자입니다. 이렇게 하면 아래 그림과 같이 연산자를 연결할 수 있습니다.

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>참고자료

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
