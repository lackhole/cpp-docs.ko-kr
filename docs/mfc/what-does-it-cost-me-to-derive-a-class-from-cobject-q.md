---
title: CObject에서 클래스를 파생시키는 비용
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: de760a2fd2908595314dc09cf5a317da3581e3bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186051"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject에서 클래스를 파생시키는 비용

클래스에서 파생 하는 오버 헤드 [CObject](../mfc/reference/cobject-class.md) 최소화 됩니다. 파생된 클래스는 4 개의 가상 함수 및 단일 상속 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 개체입니다.

## <a name="see-also"></a>참고자료

[CObject 클래스: 자주 묻는 질문](../mfc/cobject-class-frequently-asked-questions.md)
