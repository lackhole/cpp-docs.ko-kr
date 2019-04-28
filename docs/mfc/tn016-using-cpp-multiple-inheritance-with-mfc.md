---
title: 'TN016: 사용 하 여 C++ MFC 사용 하 여 다중 상속'
ms.date: 06/28/2018
f1_keywords:
- vc.inheritance
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
ms.openlocfilehash: 76dc2e856ca7db783ee542aa2dbb498fd4c1a769
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306131"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016: 사용 하 여 C++ MFC 사용 하 여 다중 상속

이 이는 Microsoft Foundation Classes를 사용 하 여 다중 상속 (MI)을 사용 하는 방법에 설명 합니다. MI 사용 MFC를 사용 하 여 필요 하지 않습니다. MI는 MFC 클래스에서 사용 되지 않으며 클래스 라이브러리를 작성할 필요가 없습니다.

다음 하위 항목 MI 일반적인 MFC 관용구와 MI의 제한 중 일부를 다루는 사용에 미치는 영향을 설명 합니다. 이러한 제한 사항 중 일부는 일반 C++ 제한 합니다. 다른 MFC 아키텍처에서 적용 됩니다.

이 기술 노트의 끝에서 MI를 사용 하는 전체 MFC 응용 프로그램을 찾을 수 있습니다.

## <a name="cruntimeclass"></a>CRuntimeClass

동적 개체 만들기 메커니즘 MFC 사용 고 지 속성을 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 데이터 구조를 고유 하 게 클래스를 식별 합니다. MFC 응용 프로그램에서 각 동적 및/또는 serializable 클래스를 사용 하 여 이러한 구조 중 하나를 연결합니다. 이러한 구조 형식의 특수 한 정적 개체를 사용 하 여 응용 프로그램이 시작 될 때 초기화 됩니다 `AFX_CLASSINIT`합니다.

현재 구현은 `CRuntimeClass` MI 런타임 형식 정보를 지원 하지 않습니다. MI MFC 응용 프로그램에서 사용할 수 없습니다 것은 아닙니다. 그러나 둘 이상의 기본 클래스에 있는 개체를 사용 하 여 작업할 때 특정 책임을 해야 합니다.

합니다 [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) 메서드는 올바르게 형식을 확인할 개체의 기본 클래스를 여러 개 있는 경우. 따라서 사용할 수 없습니다 [CObject](../mfc/reference/cobject-class.md) 가상 기본 클래스와 모든 호출이 `CObject` 멤버와 같은 함수 [cobject:: Serialize](../mfc/reference/cobject-class.md#serialize) 고 [CObject::operator 새](../mfc/reference/cobject-class.md#operator_new)범위 한정자가 있어야 합니다. 있도록 C++ 적절 한 함수 호출을 구분할 수 있습니다. 프로그램에서는 MI MFC 내의 클래스 포함 된 때를 `CObject` 기본 클래스의 기본 클래스 목록에서 가장 왼쪽에 클래스를 해야 합니다.

대신 사용 하는 것은 `dynamic_cast` 연산자입니다. MI 해당 기본 클래스 중 하나를 사용 하 여 개체를 캐스팅 합니다. 제공 된 기본 클래스의 함수를 사용 하도록 컴파일러에 강제로 됩니다. 자세한 내용은 [dynamic_cast 연산자](../cpp/dynamic-cast-operator.md)합니다.

## <a name="cobject---the-root-of-all-classes"></a>CObject-모든 클래스의 루트

모든 중요 한 클래스 클래스에서 직접 또는 간접적으로 파생 `CObject`합니다. `CObject` 에 어떤 멤버 데이터도 들어 있지만 몇 가지 기본 기능입니다. MI를 사용 하는 경우는 일반적으로 상속 하는 두 개 이상에서 `CObject`-클래스를 파생 합니다. 다음 예제에서 상속 하는 방법을 보여 줍니다.는 [CFrameWnd](../mfc/reference/cframewnd-class.md) 와 [CObList](../mfc/reference/coblist-class.md):

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

이 경우 `CObject` 두 번 포함 됩니다. 즉,에 대 한 모든 참조를 구분 하는 방법을 할 `CObject` 메서드나 연산자입니다. 합니다 **new 연산자** 하 고 [delete 연산자](../mfc/reference/cobject-class.md#operator_delete) 을 명확히 구분 하는 연산자는 합니다. 또 다른 예로, 다음 코드는 컴파일 타임 오류가 발생 합니다.

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>인해야 CObject 메서드

두 개 이상에 새 클래스를 만들 때 `CObject` 기본 클래스를 파생 다시 구현 해야 합니다 `CObject` 다른 사용자가 사용 하는 메서드. 연산자 **새** 하 고 **삭제** 필수가 및 [덤프](../mfc/reference/cobject-class.md#dump) 것이 좋습니다. 다음 예제에서는 reimplements 합니다 **새** 하 고 **삭제** 연산자 및 `Dump` 메서드:

```cpp
class CListWnd : public CFrameWnd, public CObList
{
public:
    void* operator new(size_t nSize)
    {
        return CFrameWnd:: operator new(nSize);
    }
    void operator delete(void* p)
    {
        CFrameWnd:: operator delete(p);
    }
    void Dump(CDumpContent& dc)
    {
        CFrameWnd::Dump(dc);
        CObList::Dump(dc);
    }
    // ...
};
```

## <a name="virtual-inheritance-of-cobject"></a>CObject의 가상 상속

가상으로 상속 하는 것 처럼 보일 수 `CObject` 함수 모호성 문제를 해결 하는 하지만에서는 다릅니다. 멤버 데이터가 없는 이므로 `CObject`, 기본 클래스 멤버 데이터의 여러 복사본을 방지 하기 위해 가상 상속 필요가 없습니다. 이전에 표시 된 첫 번째 예제에서는 `Dump` 에서 다르게 구현 되므로 가상 메서드는 여전히 모호한 `CFrameWnd` 및 `CObList`합니다. 모호성을 제거 하는 가장 좋은 방법은 이전 섹션에 제공 된 권장 사항을 따르는 경우

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject::IsKindOf 및 런타임 입력

MFC에서 지 원하는 런타임 입력 메커니즘 `CObject` DECLARE_DYNAMIC, IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로 사용 합니다. 이러한 매크로 안전 하 게 다운 캐스트를 보장 하기 위해 런타임 형식 검사를 수행할 수 있습니다.

이러한 매크로 단일 기본 클래스에만 적용 하는 지원 및 곱하기 상속 된 클래스에 대 한 제한 된 방식으로 작동 합니다. IMPLEMENT_DYNAMIC 또는 IMPLEMENT_SERIAL 지정 하는 기본 클래스에는 첫 번째 (또는 가장 왼쪽) 기본 클래스 이어야 합니다. 이 배치를 사용 하면 형식을 가장 왼쪽에 기본 클래스만 검사할 수 있습니다. 런타임 형식 시스템에는 추가 기본 클래스에 대해 알게 됩니다. 다음 예제에서는 런타임 시스템에서는 작업 형식에 대해 검사 `CFrameWnd`는 전혀 알지 있지만 `CObList`합니다.

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd 및 메시지 맵

제대로 작동 하려면 MFC 메시지 맵에 시스템에 대 한 두 가지 추가 요구 사항이 있습니다.

- 하나만 있어야 `CWnd`-기본 클래스를 파생 합니다.

- `CWnd`-파생 된 기본 클래스에는 첫 번째 (또는 가장 왼쪽) 기본 클래스 여야 합니다.

작동 하지 않는 몇 가지 예는 다음과 같습니다.

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>MI를 사용 하는 샘플 프로그램

다음 샘플은 하나의 클래스에서 파생 된 구성 된 독립 실행형 응용 프로그램 `CFrameWnd` 하 고 [CWinApp](../mfc/reference/cwinapp-class.md)합니다. 이런 방식으로 응용 프로그램을 구성 하는 하나의 클래스에 있는 가장 작은 MFC 응용 프로그램의 한 예로이 권장 하지 않습니다.

```cpp
#include <afxwin.h>

class CHelloAppAndFrame : public CFrameWnd, public CWinApp
{
public:
    CHelloAppAndFrame() {}

    // Necessary because of MI disambiguity
    void* operator new(size_t nSize)
        { return CFrameWnd::operator new(nSize); }
    void operator delete(void* p)
        { CFrameWnd::operator delete(p); }

    // Implementation
    // CWinApp overrides
    virtual BOOL InitInstance();
    // CFrameWnd overrides
    virtual void PostNcDestroy();
    afx_msg void OnPaint();

    DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)
    ON_WM_PAINT()
END_MESSAGE_MAP()

// because the frame window is not allocated on the heap, we must
// override PostNCDestroy not to delete the frame object
void CHelloAppAndFrame::PostNcDestroy()
{
    // do nothing (do not call base class)
}

void CHelloAppAndFrame::OnPaint()
{
    CPaintDC dc(this);
    CRect rect;
    GetClientRect(rect);

    CString s = "Hello, Windows!";
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));
    dc.SetBkMode(TRANSPARENT);
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);
}

// Application initialization
BOOL CHelloAppAndFrame::InitInstance()
{
    // first create the main frame
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",
        WS_OVERLAPPEDWINDOW, rectDefault))
        return FALSE;

    // the application object is also a frame window
    m_pMainWnd = this;
    ShowWindow(m_nCmdShow);
    return TRUE;
}

CHelloAppAndFrame theHelloAppAndFrame;
```

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
