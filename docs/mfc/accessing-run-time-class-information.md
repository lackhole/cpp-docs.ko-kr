---
title: 런타임 클래스 정보 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
ms.openlocfilehash: 2e4f8685033fc7a8a2f49dafa7ef4e4e019d8989
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392949"
---
# <a name="accessing-run-time-class-information"></a>런타임 클래스 정보 액세스

이 문서에는 런타임에 개체의 클래스에 대 한 정보를 액세스 하는 방법을 설명 합니다.

> [!NOTE]
>  MFC를 사용 하지 않는 합니다 [런타임 형식 정보](../cpp/run-time-type-information.md) (RTTI) 지원 시각적 개체에 도입 된 C++ 4.0입니다.

클래스를 파생 시킨 경우 [CObject](../mfc/reference/cobject-class.md) 사용 합니다 **DECLARE**_**동적** 및 `IMPLEMENT_DYNAMIC`의 `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE`, 또는 `DECLARE_SERIAL` 하 고 `IMPLEMENT_SERIAL` 문서에 설명 된 매크로 [CObject에서 클래스를 파생](../mfc/deriving-a-class-from-cobject.md), `CObject` 클래스에는 런타임에 개체의 정확한 클래스를 결정 하는 기능.

이 기능은 추가 형식 함수 인수 검사가 필요할 때 및 개체의 클래스를 기반으로 하는 특수 한 용도의 코드를 작성 해야 하는 경우 가장 유용 합니다. 그러나이 방법은 권장 되지 않습니다 일반적으로 동일한 가상 함수의 기능 때문입니다.

합니다 `CObject` 멤버 함수 `IsKindOf` 특정 개체를 지정된 된 클래스에 속하는 경우 또는 특정 클래스에서 파생 되는 경우를 확인 하기 위해 사용할 수 있습니다. 인수 `IsKindOf` 은 `CRuntimeClass` 개체를 사용 하 여 가져올 수 있습니다는 `RUNTIME_CLASS` 클래스의 이름 사용 하 여 매크로입니다.

### <a name="to-use-the-runtimeclass-macro"></a>RUNTIME_CLASS 매크로 사용 하려면

1. 사용 하 여 `RUNTIME_CLASS` 클래스에 대 한 다음과 같은 클래스의 이름을 사용 하 여 `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

거의 런타임 클래스 개체를 직접 액세스 해야 합니다. 런타임 클래스 개체를 전달 하는 보다 일반적인 사용의 `IsKindOf` 다음 절차에 나와 있는 것 처럼 작동 합니다. `IsKindOf` 특정 클래스에 속해 있는지 확인 하는 개체를 테스트 하는 함수입니다.

#### <a name="to-use-the-iskindof-function"></a>IsKindOf 함수를 사용 하려면

1. 이 클래스에는 런타임 클래스 지원 해야 합니다. 즉, 클래스 해야에서 파생 된 직접 또는 간접적으로 `CObject` 사용 합니다 **DECLARE**_**동적** 및 `IMPLEMENT_DYNAMIC`의 `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE`, 또는 합니다 `DECLARE_SERIAL` 하 고 `IMPLEMENT_SERIAL` 문서에 설명 된 매크로 [CObject에서 클래스 파생 시키기](../mfc/deriving-a-class-from-cobject.md)합니다.

1. 호출 된 `IsKindOf` 클래스의 개체에 대 한 멤버 함수를 사용 하 여는 `RUNTIME_CLASS` 생성 하는 매크로 `CRuntimeClass` 인수를 다음과 같이:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  IsKindOf 반환 **TRUE** 개체가 지정된 된 클래스에서 파생 된 클래스 또는 지정된 된 클래스의 멤버인 경우. `IsKindOf` 필요한 경우 Microsoft Foundation 클래스 파생된에 대해 여러 상속을 사용할 수 있지만 여러 상속 이나 가상 기본 클래스를 지원 하지 않습니다.

런타임 클래스 정보 하나 사용 하는 동적 개체 만들기입니다. 이 프로세스는 문서에서 설명 하겠습니다 [동적 개체 만들기](../mfc/dynamic-object-creation.md)합니다.

Serialization에 대 한 정보 및 런타임 클래스 정보를 자세한 문서를 참조 하세요 [MFC의 파일](../mfc/files-in-mfc.md) 하 고 [Serialization](../mfc/serialization-in-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[CObject 사용](../mfc/using-cobject.md)
