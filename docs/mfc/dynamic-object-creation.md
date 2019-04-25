---
title: 동적 개체 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 3478e5481c177e0ebca1e6b5c2cd07509371c5ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173361"
---
# <a name="dynamic-object-creation"></a>동적 개체 만들기

이 문서에는 런타임에 동적으로 개체를 만드는 방법을 설명 합니다. 프로시저 런타임 클래스 정보를 사용 하 여 문서에 설명 된 대로 [런타임 클래스 정보 액세스](../mfc/accessing-run-time-class-information.md)합니다.

#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>런타임 클래스를 지정 된 개체를 동적으로 만들려면

1. 동적으로 사용 하 여 개체를 만드는 다음 코드를 사용 합니다 `CreateObject` 함수는 `CRuntimeClass`합니다. 실패 시 유의 `CreateObject` 반환 **NULL** 예외를 발생 시키는 대신:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>참고자료

[CObject 사용](../mfc/using-cobject.md)
