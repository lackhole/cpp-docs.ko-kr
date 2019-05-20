---
title: 'TN058: MFC 모듈 상태 구현'
ms.date: 06/28/2018
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: d803dba36b7790173b21dacb6cb34241f27dfb96
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65610966"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC 모듈 상태 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트 "모듈 상태" MFC 구문 구현에 설명 합니다. MFC를 사용 하 여 DLL에서 Dll을 공유에 대 한 모듈 상태 구현에 대 한 이해는 중요 한 (또는 OLE에서 프로세스 서버).

이 읽기 전에 "관리는 데이터의 MFC 모듈 상태"에서 참조할 [새 문서 만들기, Windows, 뷰와](../mfc/creating-new-documents-windows-and-views.md)합니다. 이 문서에서는 중요 한 사용 정보 및이 주제에 대 한 개요 정보를 포함합니다.

## <a name="overview"></a>개요

MFC 상태 정보는 다음과 같은 세 가지 종류가 있습니다. 모듈 상태, 프로세스 상태 및 스레드 상태입니다. 경우에 따라 이러한 상태 형식은 결합할 수 있습니다. 예를 들어, MFC의 핸들 맵은 모듈을 로컬 및 스레드 로컬 모두입니다. 이렇게 하면 서로 다른 두 모듈에 해당 스레드의 각 지도 있습니다.

프로세스 상태 및 스레드 상태 비슷합니다. 이러한 데이터 항목은가 일반적으로 전역 변수 되었지만 지정된 된 프로세스 관련 되거나 적절 한 win32 지원에 대 한 지원이 필요 하거나 적절 한 다중 스레딩 스레드 해야 할 것입니다. 지정 된 데이터 항목에 적합 한 범주는 해당 항목 및 프로세스 및 스레드 경계와 관련 하 여 필요한 의미 체계에 따라 달라 집니다.

모듈 상태는 진정한 전역 상태 또는 로컬 프로세스 또는 스레드 로컬 상태 포함할 수 있습니다. 또한이 전환할 수 있습니다 신속 하 게 합니다.

## <a name="module-state-switching"></a>모듈 상태 전환

각 스레드에 "현재" 또는 "활성" 모듈 상태에 대 한 포인터를 포함 (당연히 포인터는 부분에서는 MFC의 스레드 로컬 상태). 이 포인터는 스레드 실행 OLE 컨트롤 또는 DLL에는 OLE 컨트롤 다시 호출 하는 응용 프로그램을 호출 하는 응용 프로그램과 같이 모듈 경계를 통과 하는 경우 변경 됩니다.

호출 하 여 현재 모듈 상태 전환 됩니다 `AfxSetModuleState`합니다. 대부분의 경우 API를 사용 하 여 직접 있습니다에서 처리 하는 것은 없습니다. MFC에서 대부분의 경우에서 라고 하 고 있습니다 (WinMain, OLE-진입점에서 `AfxWndProc`등.). 특별 한에 정적으로 연결 하 여 작성 하는 모든 구성 요소에서 이렇게 `WndProc`, 및 특수 `WinMain` (또는 `DllMain`) 모듈 상태는 현재 해야 알고 있는 합니다. DLLMODUL 확인 하 여이 코드를 볼 수 있습니다. CPP 또는 APPMODUL 합니다. CPP MFC\SRC 디렉터리에 있습니다.

모듈 상태를 설정 하 고 다음 하지 다시 설정 하려는 드문 것입니다. 대부분의 경우 "push" 자신만 모듈을 현재 상태 및 다음을 수행한 후 "pop" 원래 컨텍스트로 다시 합니다. 매크로 의해 이루어집니다 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) 특수 한 클래스 및 `AFX_MAINTAIN_STATE`합니다.

`CCmdTarget` 모듈 상태 전환을 지원 하기 위한 특별 한 기능이 있습니다. 특히는 `CCmdTarget` 진입점 OLE COM 및 OLE automation 루트 클래스를 사용 합니다. 다른 진입점와 같은 시스템에 노출, 이러한 진입점 상태를 설정 해야 올바른 모듈입니다. 어떻게 않습니다는 지정 된 `CCmdTarget` 어떤 "올바른" 모듈 상태 이어야 대답이 "를 기억 하 여" "무엇 현재" 모듈 상태가 생성 될 때를 설정할 수 있도록 현재 모듈 상태를 "기억" 이상 때 값이 호출 인지 알고 있어야 합니다. 결과적으로 모듈 상태를 지정 된 `CCmdTarget` 개체가 연결 되어 사용 하 여 개체를 생성 하는 경우 현재 모듈 상태입니다. INPROC 서버를 로드, 개체를 만들고, 해당 메서드를 호출 하는 간단한 예제를 수행 합니다.

1. OLE에서 DLL이 로드를 사용 하 여 `LoadLibrary`입니다.

2. `RawDllMain` 먼저 호출 됩니다. DLL에 대 한 모듈 상태 정적 모듈을 알려진된 상태로 설정합니다. 이러한 이유로 `RawDllMain` DLL에 정적으로 연결 됩니다.

1. 이 개체와 관련 된 클래스 팩터리에 대 한 생성자가 호출 됩니다. `COleObjectFactory` 파생 된 `CCmdTarget` 하 고 결과적으로,이 모듈 상태에서 인스턴스화됩니다. 이 중요-개체를 만드는 클래스 팩터리를 묻는 메시지가 나타나면 알고 이제을 현재 항목으로 모듈 상태입니다.

4. `DllGetClassObject` 클래스 팩터리를 얻기 위해 호출 됩니다. MFC는이 모듈에 연결 된 클래스 팩터리 목록을 검색 하 고 반환 합니다.

5. `COleObjectFactory::XClassFactory2::CreateInstance`가 호출된 경우 모듈 상태 3 단계에서 현재 모듈 상태를이 함수 개체를 만들고 반환 하기 전에 설정 (최신 상태 였던 경우 하나는 `COleObjectFactory` 인스턴스화된). 내에 이렇게 [METHOD_PROLOGUE](com-interface-entry-points.md)합니다.

1. 너무는 개체를 만들 때를 `CCmdTarget` 파생와 동일한 방식으로 `COleObjectFactory` 모듈 상태는 활성화 된 저장이 new-object 그렇습니다. 개체를 전환 하는 모듈 상태를 알고 있습니다. 이제 때마다 호출 됩니다.

1. 클라이언트에서 받은 OLE COM 개체에서 함수 호출의 `CoCreateInstance` 호출 합니다. 사용 하 여 개체를 호출할 때 `METHOD_PROLOGUE` 모듈 상태와 동일 하 게 전환할 `COleObjectFactory` 않습니다.

알 수 있듯이 메시지 만들어질 때 개체에 개체의 모듈 상태 전파 됩니다. 모듈 상태가 적절 하 게 설정 하는 것이 반드시 합니다. 설정 하지 않으면 DLL 또는 COM 개체 상호 작용할 수 잘못를 호출 하는 자체 리소스를 찾을 수 없습니다 또는 불쾌 한 다른 방법으로 실패할 수 있습니다 하는 MFC 응용 프로그램입니다.

특정 종류의 Dll, 특히 "MFC 확장명" Dll의 모듈 상태를 전환 하지 마세요 참고 자신의 `RawDllMain` (실제로 일반적으로 없어도 `RawDllMain`). "" 것 처럼 사용 하는 응용 프로그램에 실제로 있는 동작할 것 이기 때문입니다. 실행 중인 응용 프로그램의 부분 거의 이며 해당 의도를 해당 응용 프로그램의 전역 상태를 수정 합니다.

OLE 컨트롤 및 기타 Dll는 매우 다릅니다. 호출 응용 프로그램의 상태를 수정 하지 않으려는 것 호출 하는 응용 프로그램이 MFC 응용 프로그램에 아닐 수도 있고 수정할 수 없는 상태 수 있습니다. 모듈 상태 전환 고안 된 이유입니다.

DLL의 대화 상자를 시작 하는 것과 같은 DLL에서 내보낸된 함수에 대 한 함수의 시작 부분에 다음 코드를 추가 해야 합니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

반환 된 상태와 현재 모듈 상태 서로 바뀝니다 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) 현재 범위의 끝까지 합니다.

AFX_MODULE_STATE 매크로 사용 하지 않는 경우 리소스 Dll에서 문제가 발생 합니다. 기본적으로 MFC 리소스 템플릿을 로드 하는 기본 응용 프로그램의 리소스 핸들을 사용 합니다. 이 템플릿에 실제로 DLL에 저장 됩니다. 근본 원인을 MFC의 모듈 상태 정보 AFX_MODULE_STATE 매크로 의해 교체 되지 않은 경우 리소스 핸들을 MFC 모듈 상태에서 복구 됩니다. 모듈 상태를 전환 하지 않으면 잘못 된 리소스 핸들을 사용 하면 됩니다.

AFX_MODULE_STATE는 DLL의 모든 함수에 지정할 필요가 없습니다. 예를 들어 `InitInstance` MFC 모듈 상태 하기 전에 자동으로 이동 하기 때문에 MFC 코드 AFX_MODULE_STATE 없이 응용 프로그램에서 호출할 수 있습니다 `InitInstance` 한 후 다시 스위치 다음 `InitInstance` 반환 합니다. 모든 메시지 맵 처리기에도 마찬가지입니다. 기본 MFC Dll에는 실제로 메시지를 라우팅하기 전에 모듈 상태를 자동으로 전환 하는 특수 마스터 창 프로시저 경우

## <a name="process-local-data"></a>로컬 데이터 처리

로컬 데이터를 처리 하지 않는 것 같은 매우 위협적입니다 없습니다 되었을 경우 win32 DLL 모델의 어려움. Win32 Dll을 모두 여러 응용 프로그램에서 로드 하는 경우에 전역 데이터를 공유 합니다. 이 각 DLL의 DLL에 연결 하는 각 프로세스에서 해당 데이터 공간의 별도 복사본을 가져오는 위치는 "실제" Win32 DLL 데이터 모델에서 매우 다릅니다. 복잡성에 추가 하려면 win32 DLL에 힙에 할당 된 데이터는 사실상 특정 프로세스 (최소한으로 훨씬 소유권 지남에 따라). 다음 데이터와 코드를 고려 합니다.

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

위의 코드에서에 있는 경우 DLL 및 A와 B (, 사실 때문일 동일한 응용 프로그램의 두 인스턴스)의 두 프로세스에 의해 DLL이 로드 되는 어떤 일이 생기는 것이 좋습니다. 호출 `SetGlobalString("Hello from A")`합니다. 결과적으로, 할당 된 메모리를 `CString` A. 점을 염두 하는 프로세스의 컨텍스트에서 데이터를 염두에 두어야 하는 `CString` 자체는 전역 이며에 모두 표시와 B를 이제 호출 B `GetGlobalString(sz, sizeof(sz))`합니다. B는 설정 하는 데이터를 볼 수 있습니다. Win32는 같은 프로세스 간 없는 보호를 제공 하는 win32 때문입니다. 이것이 첫 번째 문제는; 대부분의 경우에서 하나의 응용 프로그램 소유자가 다른 응용 프로그램으로 간주 되는 전역 데이터에 영향을 바람직한 방법이 아닙니다.

추가 문제가 있습니다. 이제 종료 되는 경우를 가정해 봅니다. 종료 되는 경우를 사용 하는 메모리는 '`strGlobal`' 문자열 시스템 수-즉, 모든 메모리 할당 프로세스는 운영 체제에서 자동으로 해제 됩니다. 때문에 해제 되지 않습니다는 `CString` 소멸자가 호출 되 고, 아직 호출 되지 않았습니다. 단순히 해제 하기 할당 된 응용 프로그램을 떠난 장면 때문입니다. B를 호출 하는 경우 이제 `GetGlobalString(sz, sizeof(sz))`를 유효한 데이터를 얻지 못할 수 있습니다. 다른 응용 프로그램 일부는 다른 항목에 대 한 메모리를 사용 되었습니다.

명확 하 게 문제가 있습니다. MFC 3.x 스레드 로컬 저장소 (TLS) 라는 기술을 사용 합니다. MFC 3.x는 호출 되지 않습니다 하는 경우에 사용 되는 win32에서 실제로 프로세스 로컬 저장소 인덱스로 TLS 인덱스 할당 및 그런 다음 해당 TLS 인덱스를 기준으로 하는 모든 데이터를 참조 합니다. Win32에서 스레드 로컬 데이터를 저장 하는 데 사용 된 TLS 인덱스 비슷합니다 (주제에 대 한 자세한 내용은 아래 참조). 이 프로세스 마다 두 개 이상의 TLS 인덱스를 활용 하는 모든 MFC DLL 발생 합니다. OLE 컨트롤의 Dll (Ocx)를 로드 하기 위한 계정 신속 하 게 실행 하면 TLS 인덱스 (가지 64만 사용할 수 있습니다) 부족 합니다. 또한 MFC는 단일 구조에의 한 곳에서이 모든 데이터를 배치 해야 했습니다. 확장성이 우수 없습니다 하 고 TLS 인덱스의 용도 관련 하 여 이상적인 없습니다.

MFC 4.x이 문제를 래핑할 수 있습니다"" 로컬 처리 해야 하는 데이터에 대 한 클래스 템플릿 집합을 사용 하 여 해결 합니다. 예를 들어, 작성 하 여 위에서 언급 한 문제를 해결할 수 없습니다.

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC는 두 단계에서이 구현합니다. 먼저는 Win32 기반 계층 __Tls\*__  Api (**TlsAlloc**, **TlsSetValue**하십시오 **TlsGetValue**등)는 프로세스에 있는 Dll에 관계 없이 당 두 개의 TLS 인덱스를 사용 합니다. 두 번째는 `CProcessLocal` 템플릿을이 데이터에 액세스 하기 위해 제공 됩니다. 연산자를 재정의 하는, 직관적인 구문 위에서 볼 수 있습니다-> 합니다. 래핑한 개체를 모두 `CProcessLocal` 에서 파생 되어야 합니다 `CNoTrackObject`합니다. `CNoTrackObject` 하위 수준 할당자를 제공 (**LocalAlloc**/**LocalFree**) 및 가상 소멸자는 프로세스가 종료 될 때 MFC 프로세스 로컬 개체를 자동으로 제거할 수 있도록 합니다. 이러한 개체는 추가 정리 해야 하는 경우 사용자 정의 소멸자가 있습니다. 위의 예제에서는 컴파일러에서 포함 된 제거할 기본 소멸자를 생성 하므로, 필요 하지 않습니다 `CString` 개체입니다.

다른 흥미로운 이점이 있습니다.이 방법에 있습니다. 뿐만 아니라는 모두 `CProcessLocal` 자동으로 제거 하는 개체는 필요할 때까지 생성 되지 됩니다. `CProcessLocal::operator->` 연결된 된 개체가 처음으로 호출 되 고 이후에 인스턴스화합니다. 따라서 위의 예제에는 '`strGlobal`' 문자열 처음까지 생성 되지 것입니다 `SetGlobalString` 또는 `GetGlobalString` 라고 합니다. 일부 경우가 DLL의 시작 시간을 줄일 시킬 수 있습니다.

## <a name="thread-local-data"></a>스레드 로컬 데이터

로컬 데이터를 처리 하는 마찬가지로 스레드 로컬 데이터는 데이터 주어진된 스레드의 로컬 이어야 하는 경우. 즉, 해당 데이터에 액세스 하는 각 스레드에 대 한 데이터의 개별 인스턴스가 필요 합니다. 이 여러 번 사용할 수 있습니다 광범위 한 동기화 메커니즘 대신 합니다. 데이터는 여러 스레드에서 공유 될 필요가 없습니다, 하는 경우 비용이 많이 들고 불필요 한 메커니즘이 수 있습니다. 가정해를 `CString` 개체 (위의 예제와 비슷하게). 만들 수 있을 것 스레드 로컬를 사용 하 여 묶어서는 `CThreadLocal` 템플릿:

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

경우 `MakeRandomString` 호출 된 두 개의 서로 다른 스레드에서 각는 "shuffle" 문자열을 다양 한 방식 서로 간섭 하지 않고 있습니다. 있기 때문에 이것이 실제로 `strThread` 인스턴스당 하나의 전역 인스턴스 대신 스레드입니다.

캡처에 대 한 참조를은 사용 하는 방법의 `CString` 해결 되 면 대신 한 번 루프 반복 당 합니다. 루프 코드를 사용 하 여 작성 될 수도 `threadData->strThread` everywhere '`str`'를 사용 하지만 코드는 훨씬 느리게 실행 됩니다. 이러한 참조는 루프에서 발생 하는 경우 데이터에 대 한 참조를 캐시 하는 것이 좋습니다.

`CThreadLocal` 클래스 템플릿은 동일한 메커니즘을 사용 하는 `CProcessLocal` 않습니다 및 구현 방법입니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
