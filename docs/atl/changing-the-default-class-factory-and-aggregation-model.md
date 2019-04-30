---
title: 기본 클래스 팩터리 및 집계 모델 변경
ms.date: 11/04/2016
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
ms.openlocfilehash: 94f9ecd85e09cb3916b518d71b904961042142e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223159"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>기본 클래스 팩터리 및 집계 모델 변경

ATL 사용 [CComCoClass](../atl/reference/ccomcoclass-class.md) 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 정의할 수 있습니다. `CComCoClass` 다음 두 매크로 지정합니다.

- [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) 선언 되도록 클래스 팩터리 [CComClassFactory](../atl/reference/ccomclassfactory-class.md)합니다.

- [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) 개체를 집계할 수 있도록 선언 합니다.

클래스 정의에서 다른 매크로 지정 하 여 이러한 기본값 중 하나를 재정의할 수 있습니다. 예를 사용 하려면 [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) 대신 `CComClassFactory`를 지정 합니다 [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) 매크로:

[!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]

클래스 팩터리를 정의 하는 다른 두 매크로 [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 하 고 [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton)합니다.

ATL 사용 합니다 **typedef** 기본 동작을 구현 하는 메커니즘입니다. 예를 들어 DECLARE_AGGREGATABLE 매크로 사용 하 여 **typedef** 라는 형식을 정의 하려면 `_CreatorClass`, ATL. 전체에서 참조 되는 파생된 클래스에서를 **typedef** 기본 클래스의 동일한 이름을 사용 하 여 **typedef** ATL 프로그램 정의 사용 하 고 기본 동작 재정의에서 발생 합니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)<br/>
[집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)
