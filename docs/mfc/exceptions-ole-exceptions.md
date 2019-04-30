---
title: '예외: OLE 예외'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: e404005a88398ec909e3043cfa55c7e8fbe2f594
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405966"
---
# <a name="exceptions-ole-exceptions"></a>예외: OLE 예외

기술 및 OLE의 예외 처리 기능 다른 예외를 처리 하는 것에 대 한 것과 동일 합니다. 예외 처리에 대 한 추가 내용은 문서 참조 [ C++ 예외 처리](../cpp/cpp-exception-handling.md)합니다.

모든 예외 개체의 추상 기본 클래스에서 파생 된 `CException`합니다. MFC는 OLE 예외를 처리 하기 위한 두 개의 클래스를 제공 합니다.

- [COleException](../mfc/reference/coleexception-class.md) 일반 OLE 예외를 처리 합니다.

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) 생성 및 처리 OLE 디스패치 (자동화) 예외에 대 한 합니다.

이 두 클래스 간의 차이점은 제공 및 사용 되는 정보량입니다. `COleException` 예외에 대 한 OLE 상태 코드를 포함 하는 공용 데이터 멤버가 있습니다. `COleDispatchException` 다음을 비롯 한 자세한 내용은 제공 합니다.

- 응용 프로그램별 오류 코드

- "디스크 꽉 참"와 같은 오류 설명,

- 응용 프로그램 사용자에 대 한 추가 정보를 제공 하는 데 사용할 수 있는 도움말 컨텍스트

- 응용 프로그램의 도움말 파일의 이름

- 예외를 생성 하는 응용 프로그램의 이름

`COleDispatchException` Microsoft Visual Basic과 같은 제품을 사용 하 여 사용할 수 있도록 자세한 정보를 제공 합니다. 메시지 상자 또는 기타 알림은;에서 사용할 수 구두 오류 설명 도움말 정보를 사용자 예외를 발생 시킨 조건에 응답 하는 데 사용할 수 있습니다.

두 가지 전역 함수는 두 OLE 예외 클래스에 해당 합니다. [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) 하 고 [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception)합니다. 각각 일반 OLE 예외와 OLE 디스패치 예외를 throw 하려면 사용 합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)
