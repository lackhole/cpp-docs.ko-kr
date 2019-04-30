---
title: 동적으로 MFC에 링크 된 기본 MFC Dll
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
ms.openlocfilehash: 3bfed5f75dab4c501708950fdb99f53c40ec142c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315003"
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>동적으로 MFC에 링크 된 기본 MFC Dll

일반 동적으로 MFC에 링크 된 MFC DLL은 MFC를 내부적으로 사용 하는 DLL 및 MFC 또는 비 MFC 실행 파일에서 DLL에서 내보낸된 함수를 호출할 수 있습니다. 이름에서 알 수 있듯이 이러한 종류의 DLL은 MFC (라고도 하는 MFC의 공유 버전)의 동적 연결 라이브러리 버전을 사용 하 여 빌드됩니다. 함수는 일반적으로 일반 표준 C 인터페이스를 사용 하 여 MFC DLL에서에서 내보내집니다.

추가 해야 합니다는 `AFX_MANAGE_STATE` 동적으로 MFC에 링크 한 DLL에 대 한 현재 모듈 상태를 설정 하는 기본 MFC Dll에서 내보낸된 모든 함수 시작 부분에는 매크로입니다. DLL에서 내보낸 함수 시작 부분에 다음 코드 줄을 추가 하면 됩니다.

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

일반 MFC DLL을 동적으로 MFC에 링크에 다음 기능이 있습니다.

- 시각적 개체에 의해 정의 된 DLL의 새 형식입니다 C++ 4.0입니다.

- 클라이언트 실행 파일은 Dll의 사용을 지 원하는 언어를 작성할 수 있습니다 (C C++, Pascal, Visual Basic 및 등); MFC 응용 프로그램 이어야 하는 것이 없습니다.

- 정적으로 연결 된 기본 MFC DLL 달리 이러한 종류의 DLL MFC DLL (라고도: 공유 MFC DLL)을 동적으로 연결 됩니다.

- 이 유형의 DLL에 연결 된 MFC 가져오기 라이브러리는 MFC 확장명 Dll 또는 MFC DLL을 사용 하 여 응용 프로그램에 사용 되는 것과 동일한: MFCxx(D).lib.

일반 MFC DLL을 동적으로 MFC에 링크 요구 사항은:

- 이러한 Dll은으로 컴파일된 **_AFXDLL** MFC DLL을 동적으로 연결 된 실행 파일 처럼 정의 합니다. 하지만 **_USRDLL** 정적으로 MFC에 링크는 기본 MFC DLL 마찬가지로 정의 되어 있습니다.

- 이 유형의 DLL 인스턴스화해야를 `CWinApp`-클래스를 파생 합니다.

- 이 유형의 DLL 사용의 `DllMain` MFC에서 제공 합니다. 모든 DLL 별 초기화 코드를 배치 합니다 `InitInstance` 멤버 함수, 종료 코드는 `ExitInstance` 일반적인 MFC 응용 프로그램과 같이 합니다.

이러한 종류의 DLL은 MFC의 동적 연결 라이브러리 버전을 사용 하므로 DLL에 대 한에 현재 모듈 상태를 명시적으로 설정 해야 합니다. 이 작업을 수행 하려면 사용 합니다 [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) DLL에서 내보낸 모든 함수 시작 부분에는 매크로입니다.

기본 MFC Dll 있어야를 `CWinApp`-파생 클래스 및 해당 응용 프로그램 클래스의 단일 개체 처럼 MFC 응용 프로그램입니다. 그러나 합니다 `CWinApp` DLL의 개체에는 기본 메시지 펌프와 마찬가지로 없는 `CWinApp` 응용 프로그램의 개체입니다.

`CWinApp::Run` 응용 프로그램 기본 메시지 펌프를 소유 하기 때문에 메커니즘을 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프를 호출 하는 DLL 내보낸 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자를 표시는 자체의 메인 프레임 창, `CWinApp::PreTranslateMessage`합니다.

배치에서 모든 DLL 별 초기화는 `CWinApp::InitInstance` 일반적인 MFC 응용 프로그램과 같이 멤버 함수입니다. 합니다 `CWinApp::ExitInstance` 멤버 함수에 `CWinApp` 파생된 클래스에서 제공 하는 MFC 라고 `DllMain` DLL 언로드되기 전에 함수입니다.

응용 프로그램을 사용 하 여 공유 Dll MFCx0.dll 및 Msvcr*0.dll (또는 유사한 파일)를 배포 해야 합니다.

동적으로 MFC에 링크 된 DLL을 MFC 또한 정적으로 연결할 수 없습니다. 기본 MFC Dll에 대 한 응용 프로그램 링크 동적으로 MFC에 링크 된 해당 다른 DLL과 마찬가지로 합니다.

기호는 일반적으로 일반 표준 C 인터페이스를 사용 하 여 MFC DLL에서에서 내보내집니다. 기본 MFC DLL에서 내보낸 함수 선언의 다음과 같습니다.

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

기본 MFC DLL 내의 모든 메모리 할당 DLL; 내에서 유지 해야 DLL에 전달 하지 할지 호출 실행에서 다음 중 하나를 수신 합니다.

- MFC 개체에 대 한 포인터

- MFC에서 할당 된 메모리에 대 한 포인터

위의 작업을 수행 해야 하거나 호출 실행 파일과 DLL 간에 MFC 파생 개체를 전달 하는 경우에 MFC 확장 DLL을 빌드해야 다음.

포인터에 전달할 할당 된 메모리를 C 런타임 라이브러리를 통해 응용 프로그램과 DLL 간에 데이터의 복사본을 확인 하는 경우에 안전 합니다. 삭제 또는 이러한 포인터의 크기를 조정 하거나 하며 메모리의 복사본을 만들지 않고 사용 합니다.

매크로 사용 해야 하는 기본 MFC DLL 빌드는 동적으로 MFC에 링크 하는 경우 [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) 올바르게 MFC 모듈 상태를 전환 합니다. DLL에서 내보낸 함수 시작 부분에 다음 코드 줄을 추가 하면 됩니다.

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

합니다 **AFX_MANAGE_STATE** 매크로 MFC 확장명 Dll 또는 정적으로 MFC에 링크 되는 기본 MFC Dll에서 사용할 수 없습니다. 자세한 내용은 [MFC 모듈 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)합니다.

작성, 빌드 및 기본 MFC DLL을 사용 하는 방법의 예로, 샘플을 참조 하세요 [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap)합니다. 동적으로 MFC에 링크 되는 기본 MFC Dll에 대 한 자세한 내용은 샘플에 대 한 추상에서 "변환 DLLScreenCap를 동적으로 링크와 MFC DLL은" 섹션을 참조 하세요.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [기본 MFC Dll 초기화](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [동적으로 MFC에 링크 된 기본 MFC DLL의 모듈 상태](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)

- [MFC 모듈 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)

- [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

## <a name="see-also"></a>참고자료

[DLL의 종류](kinds-of-dlls.md)
