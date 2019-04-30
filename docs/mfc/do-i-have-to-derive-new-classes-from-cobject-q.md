---
title: CObject에서 새 클래스를 파생시켜야 합니까?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: 30eb3ce5bbb72ab685ed891644a478a36026ebea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352387"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject에서 새 클래스를 파생시켜야 합니까?

아니요, 수행하지 않습니다.

클래스를 파생 [CObject](../mfc/reference/cobject-class.md) serialization 또는 동적 creatability 같은 제공 해야 합니다. 많은 데이터 클래스는 파일에 대해 serialize되어야 하므로 `CObject`에서 해당 클래스를 파생하는 것이 좋습니다. 파생 된 클래스의 예로 `CObject`를 참조 합니다 [Scribble 샘플](../overview/visual-cpp-samples.md)합니다.

## <a name="see-also"></a>참고자료

[CObject 클래스: 자주 묻는 질문](../mfc/cobject-class-frequently-asked-questions.md)
