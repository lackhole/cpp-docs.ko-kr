---
title: 프로젝트의 스레딩 모델 지정(ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 69c1c80bba0b09ce69e0b9b9b27296ef2508e60b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275219"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>프로젝트의 스레딩 모델 지정(ATL)

다음 매크로 ATL 프로젝트의 스레딩 모델을 지정할 수 있습니다.

|매크로|사용 하기 위한 지침|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|개체의 모든 단일 스레딩 모델을 사용 하는 경우 정의 합니다.|
|_ATL_APARTMENT_THREADED|아파트 스레딩 개체 중 하나 이상을 사용 하는 경우를 정의 합니다.|
|_ATL_FREE_THREADED|개체의 하나 이상의 무료 또는 중립 스레딩을 사용 하는 경우 정의 합니다. 기존 코드에 해당 하는 매크로에 대 한 참조가 포함 될 수 있습니다 [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded)합니다.|

이러한 매크로의 모든 프로젝트에 대 한 정의 하지 않는 경우 _ATL_FREE_THREADED 적용 됩니다.

매크로 성능에 영향을 런타임에 다음과 같습니다.

- 프로젝트의 개체에 해당 하는 매크로 지정 하면 런타임 성능을 개선할 수 있습니다.

- 예를 들어 경우 개체의 모든 단일 스레드 _ATL_APARTMENT_THREADED를 지정 하는 경우 매크로의 상위 수준 지정 런타임 성능이 약간 저하 됩니다.

- _ATL_SINGLE_THREADED 하나를 지정할 경우 아파트 스레딩 또는 자유 스레딩 사용 하는 개체의 더 낮은 수준의 매크로, 예를 들어,를 지정 하면 응용 프로그램이 런타임에 실패할 발생할 수 있습니다.

참조 [옵션, ATL 단순 개체 마법사](../atl/reference/options-atl-simple-object-wizard.md) 에 대 한 설명은 스레딩 모델 ATL 개체에 대해 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)
