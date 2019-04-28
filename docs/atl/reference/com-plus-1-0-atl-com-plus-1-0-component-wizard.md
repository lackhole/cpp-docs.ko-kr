---
title: COM+ 1.0, ATL COM+ 1.0 구성 요소 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: 0fa649ba41a684be6ed18bd05d48954503c5db16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278594"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0 구성 요소 마법사

인터페이스 유형 및 인터페이스를 추가로 지원 되는 데 지정 하 여 ATL COM + 1.0 구성 요소 마법사의이 페이지를 사용 합니다.

ATL 프로젝트가 ATL COM 클래스에 대 한 자세한 내용은 참조 하세요. [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)합니다.

- **Interface**

   개체가 지 원하는 인터페이스의 형식을 나타냅니다. 개체는 기본적으로 이중 인터페이스를 지원합니다.

   |옵션|설명|
   |------------|-----------------|
   |**이중**|개체에 이중 인터페이스 지원 하도록 지정 (해당 vtable에 인터페이스를 사용자 지정 함수 및 런타임에 바인딩 `IDispatch` 메서드). COM 클라이언트와 Automation 컨트롤러 개체에 액세스할 수 있습니다.|
   |**사용자 지정**|개체에서 사용자 지정 인터페이스 (해당 사용자 지정 인터페이스 함수)를 지원 하는지 지정 합니다. 프로세스 경계를 넘어 특히 사용자 지정 인터페이스는 이중 인터페이스 보다 빠를 수 있습니다.<br /><br /> - **Automation 호환** 자동화 지원을 사용자 지정 인터페이스를 추가 합니다. 특성 사용된 프로젝트에 대 한 설정 합니다 **oleautomation** coclass 특성입니다.|

- **Queueable**

   클라이언트에서 비동기적으로 메시지 큐를 사용 하 여이 구성 요소를 호출할 수 있음을 나타냅니다. .H 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 특성을 사용 하는 구성 요소 매크로 사용자 지정 (TLBATTR_QUEUEABLE, 0)을 추가합니다.

- **지원**

   오류 처리 및 개체 컨트롤에 대 한 추가 지원을 나타냅니다.

   |옵션|설명|
   |------------|-----------------|
   |**ISupportErrorInfo**|지원 만듭니다는 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) 인터페이스 개체는 클라이언트에 오류 정보를 반환할 수 있도록 합니다.|
   |**IObjectControl**|세 가지 개체 액세스 제공 [IObjectControl](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectcontrol) 메서드: [활성화](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-activate)하십시오 [CanBePooled](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled), 및 [비활성화](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate)합니다.|
   |**IObjectConstruct**|에 대 한 지원을 만듭니다는 [IObjectConstruct](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectconstruct) 다른 메서드 또는 개체의 매개 변수에서 전달 관리 하는 인터페이스입니다.|

- **트랜잭션**

   개체 트랜잭션 지원함을 나타냅니다. 파일 mtxattr.h.idl 파일 (하지 않는 프로젝트)를 포함합니다.

   |옵션|설명|
   |------------|-----------------|
   |**지원됨**|개체 루트가 되지 트랜잭션 스트림의.h 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 구성 요소 특성 매크로 custom(TLBATTR_TRANS_SUPPORTED,0)를 추가 하 여 지정 합니다.|
   |**필수**|사용자 지정 하는 개체 되거나.h 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 구성 요소 특성 매크로 custom(TLBATTR_TRANS_REQUIRED,0)를 추가 하 여 트랜잭션 스트림의 루트 되지 않을 수 있습니다.|
   |**지원되지 않음**|개체 제외 트랜잭션이 있는지를 지정 합니다. .H 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 구성 요소 특성 매크로 tlbattr_trans_notsupp, 0을 추가합니다.|
   |**Requiresnew**|개체는 항상 루트 트랜잭션 스트림의.h 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 구성 요소 특성 매크로 tlbattr_trans_reqnew, 0을 추가 하 여 지정 합니다.|

## <a name="see-also"></a>참고자료

[ATL COM+ 1.0 구성 요소 마법사](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[ATL COM + 1.0 구성 요소](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
