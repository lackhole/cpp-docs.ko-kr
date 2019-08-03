---
title: 템플릿 라이브러리 (ATL)를 사용
ms.date: 11/04/2016
helpviewer_keywords:
- template libraries
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
ms.openlocfilehash: 7b1a6b0befcfd7ecf0a150653b5c32239b7f9543
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195133"
---
# <a name="using-a-template-library"></a>템플릿 라이브러리를 사용

템플릿은 다소 매크로와 유사합니다. 매크로와 같이 템플릿을 호출하면 적절한 매개변수로 대체되어 확장됩니다. 그러나 템플릿은 여기서 더 나아가 개발자가 전달한 매개변수 형식을 기반으로 새로운 클래스를 생성합니다. 이러한 새로운 클래스들은 템플릿 코드로 표현한 작업수행을 위한 타입에 안전한 방법을 구현합니다.

ATL 같은 템플릿 라이브러리는 일반적으로 소스코드로만 제공되며(또는 런타임 코드를 지원하는 약간의 소스코드) 본질적으로 또는 반드시 계층적 구조는 아니라는 점에서 기존의 다른 C++ 클래스 라이브러리와 다릅니다. 원하는 기능을 활용하기 위해 클래스에서 파생하는 방법이 아니라 대신 클래스 템플릿을 인스턴스화 합니다.

## <a name="see-also"></a>참고자료

[ATL 소개](../atl/introduction-to-atl.md)
