---
title: 컴파일러 경고(수준 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: a3f29cb895da8c06ed43dd5c9956426f3f6014f1
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810720"
---
# <a name="compiler-warning-level-1-c4910"></a>컴파일러 경고(수준 1) C4910

'\<identifier > ': ' __declspec (dllexport) ' 및 ' extern '은 (는) 명시적 인스턴스화에 호환 되지 않습니다.

*\<identifier >* 라는 명시적 템플릿 인스턴스화는 `__declspec(dllexport)` 및 `extern` 키워드 모두에 의해 수정 됩니다. 그러나 이러한 키워드는 함께 사용할 수 없습니다. `__declspec(dllexport)` 키워드는 템플릿 클래스의 인스턴스화를 의미하는 반면, `extern` 키워드는 템플릿 클래스를 자동으로 인스턴스화하지 않음을 의미합니다.

## <a name="see-also"></a>참조

[명시적 인스턴스화](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[일반 규칙 및 제한 사항](../../cpp/general-rules-and-limitations.md)