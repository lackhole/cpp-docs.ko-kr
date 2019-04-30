---
title: MFC 공용 컨트롤 라이브러리 격리
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
ms.openlocfilehash: 94700f850be62404f22974a1d5e76acad711555c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310866"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC 공용 컨트롤 라이브러리 격리

공용 컨트롤 라이브러리를 이제 격리 된 다른 모듈 (예: 사용자 Dll) 수 있도록 MFC 내의 해당 매니페스트 버전을 지정 하 여 다른 버전의 공용 컨트롤 라이브러리를 사용 합니다.

MFC 응용 프로그램 (또는 MFC를 호출한 사용자 코드) 호출로 래퍼 함수를 통해 Api 라는 공용 컨트롤 라이브러리 `Afx` *FunctionName*여기서 *FunctionName* 일반적인 이름 API 제어 합니다. 이러한 래퍼 함수는 afxcomctl32.h 및 afxcomctl32.inl이에서 정의 됩니다.

사용할 수는 [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) 하 고 [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) 공용 컨트롤 라이브러리를 호출 하는 대신 특정 API를 구현 하는지 확인 하려면 (에 정의 되었으므로 afxcomctl32.h) 매크로 [GetProcAddress](../build/getprocaddress.md)합니다.

래퍼 클래스를 통해 공용 컨트롤 라이브러리 Api에 대 한 호출을 수행한 기술적으로 `CComCtlWrapper` (되었으므로 afxcomctl32.h에 정의 됨). `CComCtlWrapper` 로드 및 언로드 comctl32.dll 담당 이기도 합니다. 인스턴스에 대 한 포인터를 포함 하는 MFC 모듈 상태 `CComCtlWrapper`합니다. 사용 하 여 래퍼 클래스에 액세스할 수 있습니다는 `afxComCtlWrapper` 매크로입니다.

호출 공통 컨트롤 API를 직접 (MFC 래퍼 함수를 사용 하지 않음)는 MFC에서 응용 프로그램 또는 사용자 DLL에서에서 작동 대부분의 경우, 사용자 DLL MFC 응용 프로그램 매니페스트에서 요청한 공용 컨트롤 라이브러리에 바인딩되기 때문에). 그러나 MFC 코드 자체는 래퍼를 사용 하 여 다른 공용 컨트롤 라이브러리 버전을 사용 하 여 사용자 Dll에서 MFC 코드를 호출할 수 있으므로 합니다.
