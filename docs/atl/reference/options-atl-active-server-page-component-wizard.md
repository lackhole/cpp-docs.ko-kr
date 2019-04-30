---
title: 옵션, ATL Active Server Page 구성 요소 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.options
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
ms.openlocfilehash: 7e9740a67f265484c349a4df644be882dba30c13
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197369"
---
# <a name="options-atl-active-server-page-component-wizard"></a>옵션, ATL Active Server Page 구성 요소 마법사

ATL Active Server 페이지 구성 요소 마법사의이 페이지를 사용 하 여 효율성 및 개체에 대 한 오류 지원을 위한 디자인.

ATL 프로젝트가 ATL COM 클래스에 대 한 자세한 내용은 참조 하세요. [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)합니다.

- **스레딩 모델**

   스레드를 관리 하기 위한 메서드를 나타냅니다. 프로젝트에서 기본적으로 다음을 사용 합니다. **아파트** 스레딩 합니다.

   참조 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md) 자세한 내용은 합니다.

   |옵션|설명|
   |------------|-----------------|
   |**Single**|개체는 단일 스레딩 모델을 지정 합니다. 단일 스레딩 모델에서 개체는 항상 기본 COM 스레드에서만에서 실행 됩니다. 참조 [단일 스레드 아파트](/windows/desktop/com/single-threaded-apartments) 하 고 [InprocServer32](/windows/desktop/com/inprocserver32) 자세한 내용은 합니다.|
   |**Apartment**|개체 아파트 스레딩을 사용 하도록 지정 합니다. 해당 단일 스레드 아파트 합니다. 아파트 스레드 구성 요소의 각 개체는 개체의 수명 동안 해당 스레드의 아파트에 할당 됩니다. 그러나 여러 개체에 대 한 여러 스레드를 사용할 수 있습니다. 각 아파트 특정 스레드에 연결 되어 있고 Windows 메시지 펌프 (기본값).<br /><br /> 참조 [단일 스레드 아파트](/windows/desktop/com/single-threaded-apartments) 자세한 내용은 합니다.|
   |**Both**|개체 수 또는 사용 하 여 아파트 자유 스레딩 생성 되는 스레드의 종류에 따라 지정 합니다.|
   |**무료**|개체는 자유 스레딩 지정 합니다. 자유 스레딩 다중 스레드 아파트 모델에는 것과 결과가 같습니다. 참조 [다중 스레드 아파트](/windows/desktop/com/multithreaded-apartments) 자세한 내용은 합니다.|
   |**Neutral**|개체는 다중 스레드 아파트에 대 한 지침을 따릅니다 하지만 모든 종류의 스레드에서 실행 될 수 있는지를 지정 합니다.|

- **집계**

   개체를 사용 하는지 여부를 나타냅니다 [집계](/windows/desktop/com/aggregation)합니다. 집계 개체를 클라이언트에 노출할 인터페이스를 선택 하 고 집계 개체에서 구현 된 것 처럼 인터페이스를 노출 합니다. 집계 개체의 클라이언트는 집계 개체와만 통신합니다.

   |옵션|설명|
   |------------|-----------------|
   |**예**|개체를 집계할 수 있도록 지정 합니다. 기본값입니다.|
   |**No**|개체는 집계 되지 않습니다 지정 합니다.|
   |**만**|개체를 집계 해야를 지정 합니다.|

- **지원**

   추가 지원 옵션:

   |옵션|설명|
   |------------|-----------------|
   |**ISupportErrorInfo**|지원 만듭니다는 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) 인터페이스 개체는 클라이언트에 오류 정보를 반환할 수 있도록 합니다.|
   |**연결 지점**|개체의 클래스에서 파생 하 여 개체에 대 한 연결점을 사용 하도록 설정 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)합니다.|
   |**자유 스레드된 마샬러**|동일한 프로세스에서 스레드 간에 효율적으로 마샬링 인터페이스 포인터에 대 한 자유 스레드된 마샬러 개체를 만듭니다. 중 하나를 지정 하는 개체를 사용 가능 **둘 다** 또는 **무료** 스레딩 모델로 합니다.|

## <a name="see-also"></a>참고자료

[ATL Active Server Page 구성 요소 마법사](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page 구성 요소](../../atl/reference/adding-an-atl-active-server-page-component.md)
