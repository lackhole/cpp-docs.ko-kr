---
title: ExitInstance 멤버 함수
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: c76f588b22ad8ffd1d3dae954c5113feffb62a3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405822"
---
# <a name="exitinstance-member-function"></a>ExitInstance 멤버 함수

합니다 [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 클래스의 멤버 함수 [CWinApp](../mfc/reference/cwinapp-class.md) 응용 프로그램의 복사본으로 종료 되 면 일반적으로 응용 프로그램을 종료 하는 사용자의 결과로 때마다 호출 됩니다.

재정의 `ExitInstance` 그래픽 장치 GDI (인터페이스) 리소스를 해제 또는 프로그램 실행 중에 사용 되는 메모리 할당 해제와 같은 특별 한 정리 처리 해야 합니다. 그러나 문서 및 뷰과 같은 표준 항목의 정리는 해당 개체에 특정 특별 한 정리를 수행 하기 위한 다른 재정의 가능 함수를 사용 하 여 framework에서 제공 됩니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
