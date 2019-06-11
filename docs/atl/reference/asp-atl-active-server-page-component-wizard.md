---
title: ASP, ATL Active Server Page 구성 요소 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: b88dffe2874d29918315af65c6ea093c24695f97
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503404"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL Active Server Page 구성 요소 마법사

ATL Active Server 페이지 구성 요소 마법사의이 페이지를 사용 하 여 ASP 구성 요소와 관련 된 상태 및 정보 처리에 대 한 선택적 설정을 지정 합니다.

- **선택적 메서드**

   선택적 ASP 메서드 추가 **OnStartPage** 하 고 **OnEndPage**, 개체입니다. Active Server Pages 내장 개체를 설정 하려면이 옵션을 선택 해야 합니다. 기본적으로 선택 됩니다.

- **OnStartPage/OnEndPage**

   [OnStartPage](/previous-versions//ms691624\(v=vs.85\)) 스크립트 개체에 액세스 하려고 처음으로 호출 됩니다. **OnEndPage** 개체가 완료 되 면 호출 되는 스크립트를 처리 합니다.

- **내장 개체**

   선택 해야 합니다 **OnStartPage/OnEndPage** ASP 내장 개체를 설정 하는 옵션입니다.

|옵션|설명|
|------------|-----------------|
|**요청**|Active Server Pages 내장 함수에 액세스할 **요청** 개체입니다. 요청 개체는 HTTP 요청을 전달 됩니다.|
|**응답**|Active Server Pages 내장 함수에 액세스할 **응답** 개체입니다. 요청에 대 한 응답으로 응답 개체 브라우저에 사용자에 게 표시할 정보를 보냅니다.|
|**세션**|Active Server Pages 내장 함수에 액세스할 **세션** 개체입니다. 합니다 **세션** 개체 저장 및 상태 정보 검색을 포함 하 여 현재 사용자 세션에 대 한 정보를 유지 합니다.|
|**애플리케이션**|Active Server Pages 내장 함수에 액세스할 **응용 프로그램** 개체입니다. 합니다 **응용 프로그램** 여러 ASP 개체 간에 공유 되는 상태를 관리 하는 개체입니다.|
|**서버**|Active Server Pages 내장 함수에 액세스할 **Server** 개체입니다. 합니다 **Server** 개체를 사용 하면 다른 ASP 개체를 만들 수 있습니다.|

## <a name="see-also"></a>참고자료

[ATL Active Server Page 구성 요소 마법사](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page 구성 요소](../../atl/reference/adding-an-atl-active-server-page-component.md)
