---
title: Windows Vista 공용 컨트롤의 빌드 요구 사항
ms.date: 11/04/2016
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: 1a2e79d91a41ea178eeb6f74ec7fa7b22588b277
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386254"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Windows Vista 공용 컨트롤의 빌드 요구 사항

MFC(Microsoft Foundation Class) 라이브러리는 Windows 공용 컨트롤 버전 6.1을 지원합니다. 공용 컨트롤은 Windows Vista에 포함 및 라이브러리는 Visual Studio SDK에 포함 되어 있습니다. 라이브러리는 기존 클래스와 새 클래스를 향상 하는 새로운 방법 및 Windows Vista 공용 컨트롤을 지 원하는 메서드를 제공 합니다. 응용 프로그램을 빌드할 때는 다음 섹션에 설명된 컴파일 및 마이그레이션 요구 사항을 따라야 합니다.

## <a name="compilation-requirements"></a>컴파일 요구 사항

### <a name="supported-versions"></a>지원되는 버전

일부 새 클래스 및 메서드만 Windows Vista 지원 및 나중에 다른 메서드 또한 이전 버전의 운영 체제를 지원 합니다. 에 `Requirements` 각 메서드 항목의 경우 필요한 최소 운영 체제는 Windows Vista를 지정 합니다.

컴퓨터는 Windows Vista에서 실행 되지 하는 경우에 컴퓨터에 버전 6.1 MFC 헤더 파일을 사용 하는 경우 Windows Vista에서 실행 되는 MFC 응용 프로그램을 빌드할 수 있습니다. 그러나 Windows Vista에 맞게 설계 된 공용 컨트롤 해당 시스템에 대해서만 작동 하 고 이전 운영 체제에서 무시 됩니다.

### <a name="supported-character-sets"></a>지원되는 문자 집합

새로운 Windows 공용 컨트롤에서는 ANSI 문자 집합이 아닌 유니코드 문자 집합만 지원됩니다. 명령 줄에서 응용 프로그램을 빌드할 때는 다음 정의 컴파일러 옵션(/D)을 모두 사용해서 기본 문자 집합으로 유니코드를 지정합니다.

```
/D_UNICODE /DUNICODE
```

Visual Studio 통합된 개발 환경 (IDE)에서 응용 프로그램을 작성 하는 경우 지정는 **유니코드 문자 집합** 옵션을 **문자 집합** 속성에는 **일반**  프로젝트 속성의 노드.

ANSI 버전으로 된 일부 MFC 메서드는 Windows 공용 컨트롤 버전 6.1부터 더 이상 사용되지 않습니다. 자세한 내용은 [사용 되지 않는 ANSI Api](../mfc/deprecated-ansi-apis.md)합니다.

## <a name="migration-requirements"></a>마이그레이션 요구 사항

Visual Studio IDE를 사용해서 Windows 공용 컨트롤 버전 6.1을 사용하는 새로운 MFC 응용 프로그램을 빌드할 경우, IDE가 적절한 매니페스트를 자동으로 선언합니다. 하지만 이전 버전의 Visual Studio에서 기존 MFC 응용 프로그램을 마이그레이션하고 새로운 공용 컨트롤을 사용하려는 경우에는 IDE가 응용 프로그램을 업그레이드하기 위한 매니페스트 정보를 자동으로 제공하지 않습니다. 다음 소스 코드를 수동으로 삽입 해야 대신에 **stdafx.h** 파일:

```
#ifdef UNICODE
#if defined _M_IX86
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_IA64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_X64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#else
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")
#endif
#endif
```

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[계층 구조 차트](../mfc/hierarchy-chart.md)<br/>
[사용되지 않는 ANSI API](../mfc/deprecated-ansi-apis.md)
