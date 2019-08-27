---
title: 'OLE 백그라운드: Linking and Embedding'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
ms.openlocfilehash: 02607df2a8fa086c5751f2b446e349a3efdbcd20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186804"
---
# <a name="ole-background-linking-and-embedding"></a>OLE 백그라운드: Linking and Embedding

컨테이너 애플리케이션에서 붙여넣기 명령을 사용하면 포함된 구성 요소 또는 포함된 항목을 만들 수 있습니다. 포함된 항목에 대한 소스 데이터는 이를 포함하는 OLE 문서의 일부로 저장됩니다. 이 방식으로 워드 프로세서 문서에 대한 문서 파일은 텍스트를 포함하고, 비트맵, 그래프, 공식 또는 다른 모든 종류의 데이터를 포함할 수도 있습니다.

OLE는 다른 애플리케이션의 데이터를 포함할 수 있는 또 다른 방법인 링크된 구성 요소 또는 링크된 항목 또는 링크를 만드는 방법을 제공합니다. 링크된 항목을 만드는 단계는 붙여넣기 명령 대신 링크 붙여넣기 명령을 사용하는 것을 제외하고는 포함된 항목을 만들 때와 비슷합니다. 포함된 구성 요소와 달리 링크된 구성 요소는 종종 개별 파일로 존재하는 원본 데이터에 대한 경로를 저장합니다.

예를 들어 워드 프로세서 문서를 작업 중일 때 일부 스프레드시트 셀에 대한 링크된 항목을 만들면, 링크된 항목에 대한 데이터가 원본 스프레드시트 문서에 저장됩니다. 워드프로세서 문서에는 해당 항목을 찾을 수 있는 위치를 지정하는 정보만 포함됩니다. 즉, 원본 스프레드시트 문서에 대한 링크가 포함됩니다. 셀을 두 번 클릭하면 스프레드시트 애플리케이션이 실행되고 원본 스프레드시트 문서가 원래 저장되었던 위치에서 로드됩니다.

포함 또는 링크 여부에 관계없이 모든 OLE 항목은 해당 항목을 만든 애플리케이션에 따라 연결된 형식을 갖습니다. 예를 들어 Microsoft 그림판 항목과 Microsoft Excel 항목은 각자 다른 한 가지 항목 형식입니다. 하지만 일부 애플리케이션에서는 두 개 이상의 항목 형식을 만들 수 있습니다. 예를 들어 Microsoft Excel은 워크시트 항목, 차트 항목 및 매크로시트 항목을 만들 수 있습니다. 클래스 식별자를 사용 하 여 시스템에서 고유 하 게 식별할 수 이러한 각 항목 또는 **CLSID**합니다.

## <a name="see-also"></a>참고자료

[OLE 백그라운드](../mfc/ole-background.md)<br/>
[OLE 백그라운드: 컨테이너 및 서버](../mfc/ole-background-containers-and-servers.md)<br/>
[컨테이너: 클라이언트 항목](../mfc/containers-client-items.md)<br/>
[서버: 서버 항목](../mfc/servers-server-items.md)
