---
title: 개체에 연결 지점 추가
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
ms.openlocfilehash: 7341e69852ed804122e0196b51d305f5af0c35b9
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772946"
---
# <a name="adding-connection-points-to-an-object"></a>개체에 연결 지점 추가

합니다 [ATL 자습서](../atl/active-template-library-atl-tutorial.md) 연결점에 대 한 지원을 사용 하 여 컨트롤을 만드는 방법, 이벤트를 추가 하는 방법 및 연결 지점 구현 하는 방법을 보여 줍니다. ATL 연결 지점 구현 된 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 클래스입니다.

연결 지점을 구현 하는 두 가지 옵션이 있습니다.

- 컨트롤이 나 개체 연결점을 추가 하 여 사용자 고유의 나가는 이벤트 소스를 구현 합니다.

- 다른 형식 라이브러리에 정의 된 연결 지점 인터페이스를 다시 사용 합니다.

두 경우 모두 연결 지점 구현 마법사 형식 라이브러리를 사용 하 여 작업을 수행 합니다.

### <a name="to-add-a-connection-point-to-a-control-or-object"></a>컨트롤 또는 개체에는 연결점을 추가 하려면

1. .Idl 파일의 라이브러리 블록에는 dispinterface를 정의 합니다. ATL 컨트롤 마법사를 사용 하 여 컨트롤을 만들 때 연결 지점에 대 한 지원을 설정한 경우 dispinterface 이미 만들어질 수 있습니다. 컨트롤을 만들 때 연결 지점에 대 한 지원을 사용 하지 않은, 경우.idl 파일에는 dispinterface을 수동으로 추가 해야 합니다. 다음은 dispinterface의 예입니다. 나가는 인터페이스 디스패치 인터페이스로 필요 하지 않지만이 예제에서는 두 dispinterface를 사용 하므로이 VBScript 및 JScript와 같은 많은 스크립팅 언어 요구 합니다.

   [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]

   Uuidgen.exe 또는 guidgen.exe 유틸리티를 사용 하 여 GUID를 생성 합니다.

2. 으로 dispinterface를 추가 합니다 `[default,source]` coclass 프로젝트의.idl 파일에 있는 개체에 대 한 인터페이스입니다. 다시 설정한 경우 연결 지점에 대 한 지원을 컨트롤을 만들 때, ATL 컨트롤 마법사 만들어집니다는 `[default,source`] 항목입니다. 이 항목을 수동으로 추가 하려면 굵게 표시 된 줄을 추가 합니다.

   [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]

   .Idl 파일을 참조 합니다 [Circ](../overview/visual-cpp-samples.md) 예로 ATL 샘플입니다.

3. 이벤트 인터페이스에 메서드 및 속성을 추가할 클래스 뷰를 사용 합니다. 클래스 뷰에서 클래스를 마우스 오른쪽 **추가** 바로 가기 메뉴를 클릭 **연결점 추가**합니다.

4. 에 **소스 인터페이스** 연결 지점 구현 마법사, 선택 목록 상자 **프로젝트의 인터페이스**합니다. 누릅니다 서버 컨트롤에 대 한 인터페이스를 선택 하는 경우 **확인**를 해야 합니다.

   - 이벤트에 대 한 나가는 호출 하 게 하는 코드를 구현 하는 이벤트 프록시 클래스를 사용 하 여 헤더 파일을 생성 합니다.

   - 연결 지점 지도에 항목을 추가 합니다.

   또한 컴퓨터에 형식 라이브러리의 모든 목록이 나타납니다. 다른 형식 라이브러리에 있는 정확히 같은 나가는 인터페이스를 구현 하려는 경우 연결 지점과 정의 하려면 이러한 다른 형식 라이브러리 중 하나를 사용 해야 합니다.

### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>다른 형식 라이브러리에 정의 된 연결 지점 인터페이스를 다시 사용

1. 구현 하는 클래스를 마우스 오른쪽 단추로 클릭 클래스 뷰에서 **BEGIN_COM_MAP** 매크로 가리킵니다 **추가** 바로 가기 메뉴를 클릭 **연결점 추가**합니다.

2. 연결 지점 구현 마법사에서 형식 라이브러리에서 형식 라이브러리 및 인터페이스를 선택 하 고 클릭 **추가**합니다.

3. .Idl 파일을 편집 합니다.

   - 이벤트 소스를 사용 하는 개체의.idl 파일에서 dispinterface를 복사 합니다.

   - 사용 된 **importlib** 해당 형식 라이브러리에서 명령입니다.

## <a name="see-also"></a>참고자료

[연결 지점](../atl/atl-connection-points.md)
