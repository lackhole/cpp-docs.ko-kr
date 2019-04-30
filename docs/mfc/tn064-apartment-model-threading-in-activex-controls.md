---
title: 'TN064: 아파트 모델 ActiveX 컨트롤의 스레딩'
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: d6f02b2106693226f6380e935a54e04e10d5b4f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351828"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: 아파트 모델 ActiveX 컨트롤의 스레딩

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트는 ActiveX 컨트롤의 아파트 모델 스레딩 사용 하도록 설정 하는 방법에 설명 합니다. 아파트 모델 스레딩는 지원 시각적 개체의 C++ 버전 4.2 이상.

## <a name="what-is-apartment-model-threading"></a>아파트 모델 스레딩 하는 것이 무엇입니까

아파트 모델은 다중 스레드 컨테이너 응용 프로그램 내에서 ActiveX 컨트롤과 같은 포함 된 개체를 지 원하는 방법. 응용 프로그램이 여러 스레드를 가질 수 있습니다, 있지만 하나의 "아파트" 하나의 스레드에서 실행 되는에 포함된 된 개체의 각 인스턴스에 할당 됩니다. 즉, 컨트롤의 인스턴스에 대 한 모든 호출이 동일한 스레드에서 발생 합니다.

그러나 컨트롤의 동일한 형식의 다른 인스턴스는 서로 다른 아파트에 할당할 수 있습니다. 따라서 컨트롤의 여러 인스턴스 (예: 전역 또는 정적 데이터) 공통에서 데이터를 공유 하는 경우이 공유 데이터에 대 한 액세스에서 중요 섹션과 같이 동기화 개체를 보호 해야 합니다.

아파트 모델 스레딩에 대 한 자세한 내용은 참조 하십시오 [프로세스 및 스레드에](/windows/desktop/ProcThread/processes-and-threads) 에 *OLE 프로그래머 참조*합니다.

## <a name="why-support-apartment-model-threading"></a>아파트 모델 스레딩 지원 이유

아파트 모델 스레딩 지 원하는 컨트롤에 아파트 모델을 지 원하는 다중 스레드 컨테이너 응용 프로그램에서 사용할 수 있습니다. 아파트 모델 스레딩을 사용 하지 않을 경우 컨테이너 컨트롤을 사용할 수 있는 잠재적인 집합을 제한 됩니다.

아파트 모델 스레딩 사용 하도록 설정 하는 것은 거의 또는 전혀 공유 데이터가 있어야 하는 경우에 특히 대부분의 컨트롤에 대 한 쉽습니다.

## <a name="protecting-shared-data"></a>공유 데이터 보호

컨트롤에 공유 데이터를 사용 하는 경우 정적 멤버 변수인 같은 대 한 액세스 둘 이상의 스레드가 동시에 데이터를 수정 하지 못하도록 중요 섹션을 사용 하 여 데이터를 보호 되어야 합니다. 임계 영역을이 용도로 설정 하려면 클래스의 정적 멤버 변수를 선언 `CCriticalSection` 컨트롤의 클래스에 있습니다. 사용 합니다 `Lock` 및 `Unlock` 중요 한이 섹션의 멤버 함수 코드에는 공유 데이터에 액세스 하는 위치 개체입니다.

예를 들어, 모든 인스턴스에서 공유 되는 문자열로 유지 관리 해야 하는 컨트롤 클래스를 고려 합니다. 이 문자열 정적 멤버 변수에서 유지 관리 하 고 중요 섹션에 의해 보호 수 있습니다. 컨트롤의 클래스 선언 다음이 포함 됩니다.

```
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

이러한 변수에 대 한 정의 클래스에 대 한 구현이 포함 합니다.

```
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

에 대 한 액세스는 `_strShared` 정적 멤버는 중요 한 섹션에서 다음 보호할 수 있습니다.

```
void CSampleCtrl::SomeMethod()
{
    _critSect.Lock();
if (_strShared.Empty())
    _strShared = "<text>";
    _critSect.Unlock();

...
}
```

## <a name="registering-an-apartment-model-aware-control"></a>아파트 모델 인식 컨트롤을 등록합니다.

아파트 모델 스레딩 지 원하는 컨트롤에서 해당 클래스 ID 레지스트리 항목의 "아파트" 값을 사용 하 여 명명 된 값 "ThreadingModel"를 추가 하 여 레지스트리의이 기능에 지정 해야 합니다 *클래스 id* \\ **InprocServer32** 키입니다. 컨트롤에 자동으로 등록 하려면이 키를 전달 합니다 *afxRegApartmentThreading* 여섯 번째 매개 변수를 플래그 `AfxOleRegisterControlClass`:

```
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)
{
    if (bRegister)
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(),
    m_clsid,
    m_lpszProgID,
    IDS_SAMPLE,
    IDB_SAMPLE,
    afxRegApartmentThreading,
    _dwSampleOleMisc,
    _tlid,
    _wVerMajor,
    _wVerMinor);

else
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}
```

컨트롤 프로젝트 시각적 개체의 컨트롤에 의해 생성 된 경우 C++ 버전 4.1 이상에서는이 플래그는 이미 있을 코드에서. 스레딩 모델을 등록 하는 데 필요한 변경은 하지 않습니다.

프로젝트가 컨트롤의 이전 버전에서 생성 된 경우 기존 코드 여섯 번째 매개 변수로 부울 값을 갖습니다. 기존 매개 변수가 TRUE 인 경우 변경 되도록 *afxRegInsertable | afxRegApartmentThreading*합니다. 기존 매개 변수가 FALSE 인 경우 변경 되도록 *afxRegApartmentThreading*합니다.

컨트롤이 아파트 모델 스레딩에 대 한 규칙을 따르지 않으면을 전달 하면 안 *afxRegApartmentThreading* 이 매개 변수입니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
