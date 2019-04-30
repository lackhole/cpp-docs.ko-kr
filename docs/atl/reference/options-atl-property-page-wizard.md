---
title: 옵션, ATL 속성 페이지 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: c92c7a3f03c3ddedbea02647e2317d77a7655609
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275401"
---
# <a name="options-atl-property-page-wizard"></a>옵션, ATL 속성 페이지 마법사

마법사의이 페이지를 사용 하 여 만드는 속성 페이지의 스레딩 모델 및 집계 수준을 정의 합니다.

- **스레딩 모델**

   속성 페이지에서 사용 되는 스레딩 모델을 지정 합니다.

   참조 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md) 자세한 내용은 합니다.

   |옵션|설명|
   |------------|-----------------|
   |**Single**|속성 페이지를 기본 COM 스레드에서만에서 실행합니다.|
   |**Apartment**|모든 단일 스레드 아파트에서 속성 페이지를 만들 수 있습니다. 기본값입니다.|

- **집계**

   만들 속성 페이지에 대 한 집계 지원을 추가 합니다. 참조 [집계](../../atl/aggregation.md) 자세한 내용은 합니다.

   |옵션|설명|
   |------------|-----------------|
   |**예**|집계할 수 있는 속성 페이지를 만듭니다.|
   |**No**|집계 될 수 없는 속성 페이지를 만듭니다.|
   |**만**|집계를 통해만 인스턴스화할 수 있는 속성 페이지를 만듭니다.|

## <a name="see-also"></a>참고자료

[ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)<br/>
[문자열, ATL 속성 페이지 마법사](../../atl/reference/strings-atl-property-page-wizard.md)
