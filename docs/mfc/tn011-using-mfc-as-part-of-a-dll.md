---
title: 'TN011: DLL의 일부로 MFC 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 753612fae101708dd4f8294db121980b62af30b3
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65610953"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: DLL의 일부로 MFC 사용

이 Windows 동적 연결 라이브러리 (DLL)의 일부로 MFC 라이브러리를 사용할 수 있는 기본 MFC Dll에 설명 합니다. Windows Dll 및 빌드하는 방법을 잘 알고 있다고 가정 합니다. MFC 확장명 Dll에 대 한 정보를 사용 하 여 만들 수 있는 MFC 라이브러리에 대 한 확장 참조 [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)합니다.

## <a name="dll-interfaces"></a>DLL 인터페이스

기본 MFC Dll 응용 프로그램과 DLL 인터페이스는 C와 같은 함수 또는 명시적으로 내보낸된 클래스에 지정 된 것을 가정 합니다. MFC 클래스 인터페이스를 내보낼 수 없습니다.

MFC를 사용 하는 응용 프로그램과 DLL을 원하는 경우 MFC 라이브러리의 공유 버전을 사용 하거나 또는 라이브러리의 복사본에 정적으로 링크를 선택 하는 둘입니다. 응용 프로그램 및 DLL 둘 다 사용할 수 MFC 라이브러리의 표준 버전 중 하나입니다.

기본 MFC Dll 있는 몇 가지 이점이 있습니다.

- 응용 프로그램 DLL을 사용 하는 MFC를 사용 하지 않아도 및 시각적 개체를 사용할 필요가 없습니다 C++ 응용 프로그램입니다.

- 정적으로 MFC에 링크 되는 기본 MFC Dll에 DLL의 크기를 사용 하 고 연결 하는 MFC 및 C 런타임 루틴에만 따라 달라 집니다.

- 동적으로 MFC에 링크 되는 기본 MFC Dll을 사용 하 여 공유 버전의 MFC 사용 하 여 메모리를 절약 중요할 수 있습니다. 공유 Dll에서 Mfc를 배포 해야 하는 반면\<*버전*>.dll 및 Msvvcrt\<*버전*> DLL 사용 하 여.dll입니다.

- DLL 디자인은 독립적 클래스를 구현 하는 방법입니다. DLL 디자인 하려는 Api에만 내보냅니다. 결과적으로 구현이 변경 되 면 기본 MFC Dll는 여전히 유효 합니다.

- 정적으로 MFC에 링크 되는 기본 MFC Dll을 사용 하 여 응용 프로그램과 DLL MFC를 사용 하는 경우 문제가 없는 응용 프로그램을 다른 버전의 MFC DLL 보다 또는 그 반대의 경우도 마찬가지가 됩니다. MFC 라이브러리는 각 DLL 또는 EXE에 정적으로 연결 되어, 때문에 있는 버전에 대 한 어떠한 질문 이라도 방법이 있습니다.

## <a name="api-limitations"></a>API 제한 사항

일부 MFC 기능 기술 제한으로 인해 DLL 버전에 적용 되지 않습니다 없거나 해당 서비스 응용 프로그램에서 일반적으로 제공 됩니다. 적용할 수 없는 유일한 함수는 현재 버전의 MFC 사용 하 여 `CWinApp::SetDialogBkColor`입니다.

## <a name="building-your-dll"></a>DLL 빌드

정적으로 MFC 기호에 연결 된 기본 MFC Dll을 컴파일하는 경우 `_USRDLL` 고 `_WINDLL` 정의 해야 합니다. 다음과 같은 컴파일러 스위치를 사용 하 여 DLL 코드를 컴파일할 수도 해야 합니다.

- **/ D_WINDLL** 컴파일이 DLL에 대 한 의미

- **/ D_USRDLL** 기본 MFC DLL을 작성 하는 지정

또한 이러한 기호를 정의 하 고 동적으로 MFC에 링크 되는 기본 MFC Dll을 컴파일하는 경우 이러한 컴파일러 스위치를 사용 해야 합니다. 또한 기호 `_AFXDLL` 정의 해야 합니다 및 DLL 코드를 사용 하 여 컴파일해야 합니다.

- **/ D_AFXDLL** 동적으로 MFC에 링크 된 기본 MFC DLL을 작성할 수 있도록 지정 합니다.

응용 프로그램과 DLL 인터페이스 (Api)를 명시적으로 내보내야 합니다. 낮은 대역폭 되도록 사용자 인터페이스를 정의 하 고 가능 하면 C 인터페이스만 사용 하 여 하는 것이 좋습니다. 직접 보다 더 복잡 한 유지 관리 하기가 C 인터페이스는 C++ 클래스입니다.

C에서 포함 될 수 있는 별도 헤더에 Api를 배치 하 고 C++ 파일입니다. MFC 고급 개념 샘플에서 ScreenCap.h 헤더를 참조 하세요 [DLLScreenCap](../overview/visual-cpp-samples.md) 예입니다. 함수를 내보내려면에 입력 합니다 `EXPORTS` 모듈 정의 파일의 섹션 (합니다. DEF) 하거나 포함 `__declspec(dllexport)` 함수 정의에 있습니다. 사용 하 여 `__declspec(dllimport)` 클라이언트 실행 파일에 이러한 함수를 가져오려고 합니다.

동적으로 MFC에 링크 되는 기본 MFC Dll에서 내보낸된 모든 함수 시작 부분에 AFX_MANAGE_STATE 매크로 추가 해야 합니다. 이 매크로 DLL에 대 한 현재 모듈 상태를 설정합니다. 이 매크로 사용 하려면 DLL에서 내보낸 함수의 시작 부분에 코드의 다음 줄을 추가 합니다.

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain -> DllMain

MFC 라이브러리는 표준 Win32 정의 `DllMain` 초기화 하는 진입점 하 [CWinApp](../mfc/reference/cwinapp-class.md) 같이 일반적인 MFC 응용 프로그램 개체를 파생 합니다. 배치에서 모든 DLL 별 초기화 된 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 일반적인 MFC 응용 프로그램 에서처럼 메서드.

이때 합니다 [cwinapp:: Run](../mfc/reference/cwinapp-class.md#run) 응용 프로그램 기본 메시지 펌프를 소유 하기 때문에 메커니즘을 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프를 호출 하는 DLL 내보낸 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자를 표시 합니다. 자체의 메인 프레임 창, [경우](../mfc/reference/cwinapp-class.md#pretranslatemessage)합니다.

이 함수에 대 한 DLLScreenCap 샘플을 참조 하세요.

합니다 `DllMain` MFC는 호출을 제공 하는 함수를 [CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 에서 파생 된 클래스의 메서드로 `CWinApp` DLL 언로드되기 전에 합니다.

## <a name="linking-your-dll"></a>DLL에 링크

정적으로 MFC에 링크 되는 기본 MFC Dll을 사용 하 여 DLL Nafxcwd.lib 또는 Nafxcw.lib와 Libcmt.lib 라는 C 런타임의 버전을 사용 하 여 연결 해야 합니다. 이러한 라이브러리는 미리 작성 된 및 시각적 개체를 실행 하는 경우 지정 하 여 설치할 수 있습니다 C++ 설치 합니다.

## <a name="sample-code"></a>샘플 코드

전체 샘플 DLLScreenCap 프로그램 MFC 고급 개념 샘플을 참조 하세요. 이 샘플에서 몇 가지 흥미로운 작업은 다음과 같습니다.

- 응용 프로그램의 DLL의 컴파일러 플래그와 다릅니다.

- 링크 줄 고 합니다. DLL에 대 한 정의 파일 및 응용 프로그램에 대 한 서로 다릅니다.

- DLL을 사용 하는 응용 프로그램에 있이 필요가 없습니다 C++입니다.

- 응용 프로그램과 DLL 인터페이스는 C에서 사용할 수 있는 API 또는 C++ 고 DLLScreenCap.def를 사용 하 여 내보내집니다.

다음 예제에서는 일반 정적으로 MFC에 링크 MFC DLL에에서 정의 된 API를 보여 줍니다. 이 예제에서는 선언에 포함 되어는 `extern "C" { }` 차단 C++ 사용자입니다. 이 몇 가지 이점이 있습니다. 먼저 DLL Api 사용 가능 하 여 수행할 수 비-C++ 클라이언트 응용 프로그램입니다. 때문에 DLL 오버 헤드가 감소 하는 두 번째로, C++ 이름 변환을 적용 되지 것입니다 내보낸 이름입니다. 마지막으로 쉽게를 명시적으로 추가 하는 합니다. DEF 파일 이름 관리에 대해 걱정할 필요 없이 내보내기 서 수로) 하는 것 (입니다.

```
#ifdef __cplusplus
extern "C" {
#endif  /* __cplusplus */

struct TracerData
{
    BOOL bEnabled;
    UINT flags;
};

BOOL PromptTraceFlags(TracerData FAR* lpData);

#ifdef __cplusplus
}
#endif
```

API 사용 되는 구조는 MFC 클래스에서 파생 되지 않은 및 API 헤더에 정의 됩니다. 이 응용 프로그램과 DLL 간의 인터페이스의 복잡성이 줄어들고 C 프로그램에서 DLL을 사용할 수 있도록 만듭니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
