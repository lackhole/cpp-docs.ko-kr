---
title: 프로그래밍 방식 인쇄
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
ms.openlocfilehash: eb8804610832f91f4b24487fddfe9c24a3799117
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342090"
---
# <a name="programmatic-printing"></a>프로그래밍 방식 인쇄

OLE 제공 영구 문서를 고유 하 게 식별 하는 방법 (`GetClassFile`) 해당 관련된 코드만으로 로드 하 고 (`CoCreateInstance`, `QueryInterface(IID_IPersistFile)`, `QueryInterface(IID_IPersistStorage)`를 `IPersistFile::Load`, 및 `IPersistStorage::Load`). 액티브 문서 포함 (원래 OLE 2.0 함께 제공 되지 않으며 기존 OLE 디자인을 사용 하 여) 소개 자료 표준 인쇄 인터페이스를 추가로 인쇄 문서를 사용 하도록 설정 하는 `IPrint`로드할 수 있는 모든 개체를 통해 일반 공급는 문서 종류의 영구 상태입니다. 활성 문서의 각 뷰를 지원할 필요에 따라 수는 `IPrint` 이러한 기능을 제공 하는 인터페이스입니다.

`IPrint` 인터페이스는 다음과 같이 정의 됩니다.

```
interface IPrint : IUnknown
    {
    HRESULT SetInitialPageNum([in] LONG nFirstPage);
    HRESULT GetPageInfo(
        [out] LONG *pnFirstPage,
        [out] LONG *pcPages);
    HRESULT Print(
        [in] DWORD grfFlags,
        [in,out] DVTARGETDEVICE **pptd,
        [in,out] PAGESET ** ppPageSet,
        [in,out] STGMEDIUM **ppstgmOptions,
        [in] IContinueCallback* pCallback,
        [in] LONG nFirstPage,
        [out] LONG *pcPagesPrinted,
        [out] LONG *pnPageLast);
    };
```

클라이언트와 컨테이너를 사용 하기만 하면 `IPrint::Print` 문서를 인쇄 하려면 페이지, 대상 장치, 인쇄 제어 플래그를 지정 하는 문서 로드 되 면 자체 인쇄를 하도록 지시 하려면 및 추가 옵션입니다. 클라이언트 인터페이스를 통해 인쇄의 연속 작업을 제어할 수도 있습니다 `IContinueCallback` (아래 참조).

또한 `IPrint::SetInitialPageNum` 번호 매기기 하 여 페이지 원활 하 게, 분명히 바인더와 같은 액티브 문서 컨테이너에 대 한 혜택으로 일련의 문서를 인쇄 하는 기능을 지원 합니다. `IPrint::GetPageInfo` 시작을 검색 하려면 호출자를 허용 하 여 간단한 페이지 매김 정보를 표시 하면 페이지에 이전에 전달 되는 숫자 `SetInitialPageNum` 또는 문서의 내부 기본 시작 페이지 번호 및 문서의 페이지 수입니다.

개체를 지 원하는 `IPrint` 레지스트리에 저장 된 개체의 CLSID "인쇄 가능" 키를 사용 하 여 표시 됩니다.

HKEY_CLASSES_ROOT\CLSID\\{...}\Printable

`IPrint` 일반적으로 하나를 지 원하는 동일한 개체에서 구현 `IPersistFile` 또는 `IPersistStorage`합니다. 호출자에 게 "인쇄 가능" 키에 대 한 레지스트리에서 확인 하 여 일부 클래스의 영구 상태를 프로그래밍 방식으로 인쇄 하는 기능을 확인 합니다. 현재 "인쇄 가능" 나타냅니다 지원 적어도 `IPrint`; 다른 인터페이스 정의 될 수 있습니다 나중에 살펴볼 되어 `QueryInterface` 여기서 `IPrint` 단순히 기본 수준의 지원 나타냅니다.

프로시저를 인쇄 하는 동안 클라이언트 또는 인쇄를 계속할지 여부를 제어 하는 인쇄를 시작 하는 컨테이너를 수도 있습니다. 예를 들어 컨테이너에는 인쇄 작업을 가능한 한 빨리 종료 해야 하는 "중지 Print" 명령을 지원할 수 있습니다. 이 기능을 지원 하려면 클라이언트 인쇄 가능한 개체의 인터페이스를 사용 하 여 작은 알림 싱크 개체를 구현할 수 `IContinueCallback`:

```
interface IContinueCallback : IUnknown
    {
    HRESULT FContinue(void);
    HRESULT FContinuePrinting(
        [in] LONG cPagesPrinted,
        [in] LONG nCurrentPage,
        [in] LPOLESTR pszPrintStatus);
    };
```

이 인터페이스는 Win32 API에서 다양 한 연속 절차 중 발생 하는 제네릭 연속 콜백 함수로 유용 하도록 설계 되었습니다 (같은 합니다 `AbortProc` 인쇄 및 `EnumMetafileProc` 메타 파일 열거형에 대 한). 따라서이 인터페이스 디자인 다양 한 시간이 오래 걸리는 프로세스에에서 유용합니다.

가장 일반적인 경우에는 `IContinueCallback::FContinue` 함수는 긴 프로세스에 의해 주기적으로 호출 됩니다. 싱크 개체 작업을 계속 하려면 S_OK와 절차를 가능한 한 빨리 중지 하는 S_FALSE를 반환 합니다.

`FContinue`그러나은의 컨텍스트에서 사용 하지 `IPrint::Print`; 대신 사용 하 여 인쇄 `IContinueCallback::FContinuePrint`합니다. 인쇄 개체는 주기적으로 호출 `FContinuePrinting` 가 인쇄 된 페이지 수, 인쇄, 페이지 번호 및 클라이언트 (예: "페이지를 사용자에 게 표시 하도록 선택할 수 있는 인쇄 상태를 설명 하는 추가 문자열을 전달 합니다. 5의 19")입니다.

## <a name="see-also"></a>참고자료

[액티브 문서 컨테이너](../mfc/active-document-containers.md)
