---
title: 'TN038: MFC-OLE IUnknown 구현'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- aggregation macros [MFC]
- COM interfaces, base interface
- IUnknown interface
- END_INTERFACE_MAP macro [MFC]
- TN038
- BEGIN_INTERFACE_PART macro [MFC]
- DECLARE_INTERFACE_MAP macro [MFC]
- BEGIN_INTERFACE_MAP macro [MFC]
- OLE [MFC], implementing IUnknown interface
- METHOD_PROLOGUE macro [MFC]
- STDMETHOD macro [MFC]
- END_INTERFACE_PART macro [MFC]
- INTERFACE_PART macro
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
ms.openlocfilehash: 0722ce294e6a088446b8ba681810cf3f7885f122
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305478"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038: MFC/OLE IUnknown 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

OLE 2의 핵심에는 "OLE 구성 요소 개체 모델" 즉, COM이 있습니다. COM은 협동 개체가 서로 통신하는 방법에 대한 표준을 정의합니다. 여기에는 메서드가 개체에서 디스패치되는 방법을 포함하여 “개체"의 모양에 대한 세부 정보가 포함됩니다. 또한 COM은 모든 COM 호환 클래스가 파생되는 기본 클래스를 정의합니다. 이 기본 클래스는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)합니다. 하지만 합니다 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 인터페이스 라고는 C++ 클래스를 COM 모든 언어에 한정 되지 않습니다.-C, PASCAL 또는 COM 개체의 이진 레이아웃을 지원할 수 있는 다른 언어에서 구현할 수 있습니다.

OLE에서 파생 된 모든 클래스를 가리킵니다 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) "인터페이스로." 이 중요 한 차이 이후의 "인터페이스"와 같은 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 구현이 함께 전달 합니다. 해당 구현에서 수행하는 구체적인 작업이 아니라 개체가 통신하는 데 필요한 프로토콜만 정의하면 됩니다. 따라서 최대 유연성을 허용하는 시스템에 적합합니다. MFC의 역할은 MFC/C++ 프로그램의 기본 동작을 구현하는 것입니다.

MFC 구현을 이해 하기 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 란이 인터페이스를 먼저 이해 해야 합니다. 간단한 형태의 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 아래 정의 되어 있습니다.

```cpp
class IUnknown
{
public:
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;
    virtual ULONG AddRef() = 0;
    virtual ULONG Release() = 0;
};
```

> [!NOTE]
> 필요한 특정 호출 규칙 세부 정보, 같은 `__stdcall`과 같이 필요한 특정 호출 규칙 정보는 이 그림에서 제외됩니다.

합니다 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) 하 고 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 멤버 함수는 개체의 메모리 관리를 제어 합니다. COM은 참조 개수 계산 스키마를 사용하여 개체를 추적합니다. C++에서처럼 개체가 직접 참조되지 않습니다. 대신 COM 개체는 항상 포인터를 통해 참조됩니다. 소유자가 완료 되 면 개체를 해제 하려면 사용 된 개체의 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 멤버 라고 (것과 기존에 대 한 연산자 delete를 사용 하 여 달리 C++ 개체). 참조 개수 계산 메커니즘에서는 단일 개체에 대한 여러 참조를 관리할 수 있습니다. 구현의 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) 하 고 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 개체에 대 한 참조 횟수를 유지 관리-개체 참조 개수가 0에 도달할 때까지 삭제 되지 않습니다.

[AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) 하 고 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 구현 측면에서 보면 매우 간단 합니다. 다음은 간단한 구현입니다.

```cpp
ULONG CMyObj::AddRef()
{
    return ++m_dwRef;
}

ULONG CMyObj::Release()
{
    if (--m_dwRef == 0)
    {
        delete this;
        return 0;
    }
    return m_dwRef;
}
```

합니다 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 멤버 함수는 약간 더 흥미롭습니다. 개체 멤버 함수만 해당 그리 흥미롭지 않습니다 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) 하 고 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) -좋을 것 보다 많은 작업을 수행 하려면 개체에 알리는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 이 옵션을 제공 합니다. 이 경우 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 유용 합니다. 동일한 개체에서 다른 "인터페이스"를 가져올 수 있습니다. 이러한 인터페이스는 일반적으로에서 파생 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 새 멤버 함수를 추가 하 여 추가 기능을 추가 합니다. COM 인터페이스는 인터페이스에 선언된 멤버 변수를 사용하지 않으며, 모든 멤버 함수가 pure-virtual로 선언됩니다. 예를 들면 다음과 같습니다.

```cpp
class IPrintInterface : public IUnknown
{
public:
    virtual void PrintObject() = 0;
};
```

하나만 있는 경우 IPrintInterface를 가져오려면는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)를 호출 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 사용 하 여는 `IID` 의 `IPrintInterface`합니다. `IID`는 인터페이스를 고유하게 식별하는 128비트 숫자입니다. 사용자나 OLE에서 정의하는 각 인터페이스에 대해 `IID`가 있습니다. 하는 경우 *pUnk* 에 대 한 포인터는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 개체에서 IPrintInterface를 검색 하는 코드 수 있습니다.

```cpp
IPrintInterface* pPrint = NULL;
if (pUnk->QueryInterface(IID_IPrintInterface, (void**)&pPrint) == NOERROR)
{
    pPrint->PrintObject();
    pPrint->Release();
    // release pointer obtained via QueryInterface
}
```

상당히 쉽게 보이지만 IPrintInterface 모두를 지 원하는 개체는 구현 방법 및 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 인터페이스가 경우에 간단한 IPrintInterface에서 직접 파생 되며 이후 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) -IPrintInterface를 구현 하 여 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 자동으로 지원 됩니다. 예를 들어:

```cpp
class CPrintObj : public CPrintInterface
{
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
    virtual ULONG AddRef();
    virtual ULONG Release();
    virtual void PrintObject();
};
```

구현은 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) 하 고 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 는 동일 정확 하 게 구현 된 위의. `CPrintObj::QueryInterface` 다음과 같이 표시 됩니다.

```cpp
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)
{
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)
    {
        *ppvObj = this;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}
```

IID(인터페이스 식별자)가 인식되면 포인터가 개체에 반환되고, 그렇지 않으면 오류가 발생합니다. 또한 성공적인 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 암시적인 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)합니다. 물론 CEditObj::Print도 구현해야 합니다. IPrintInterface에서 직접 파생 되었기 때문에 간단 하 여 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 인터페이스입니다. 그러나 두 가지 다른 인터페이스를 지원 하려는 경우 둘 다에서 파생 된 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), 다음 사항을 고려 합니다.

```cpp
class IEditInterface : public IUnkown
{
public:
    virtual void EditObject() = 0;
};
```

C++ 다중 상속 사용을 포함하여 다양한 방법으로 IEditInterface와 IPrintInterface를 모두 지원하는 클래스를 구현할 수 있지만 여기서는 중첩 클래스를 사용하여 이 기능을 구현하는 데 집중합니다.

```cpp
class CEditPrintObj
{
public:
    CEditPrintObj();

    HRESULT QueryInterface(REFIID iid, void**);
    ULONG AddRef();
    ULONG Release();
    DWORD m_dwRef;

    class CPrintObj : public IPrintInterface
    {
    public:
        CEditPrintObj* m_pParent;
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
        virtual ULONG AddRef();
        virtual ULONG Release();
    } m_printObj;

    class CEditObj : public IEditInterface
    {
    public:
        CEditPrintObj* m_pParent;
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);
        virtual ULONG AddRef();
        virtual ULONG Release();
    } m_editObj;
};
```

다음은 전체 구현입니다.

```cpp
CEditPrintObj::CEditPrintObj()
{
    m_editObj.m_pParent = this;
    m_printObj.m_pParent = this;
}

ULONG CEditPrintObj::AddRef()
{
    return ++m_dwRef;
}

CEditPrintObj::Release()
{
    if (--m_dwRef == 0)
    {
        delete this;
        return 0;
    }
    return m_dwRef;
}

HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)
    {
        *ppvObj = &m_printObj;
        AddRef();
        return NOERROR;
    }
    else if (iid == IID_IEditInterface)
    {
        *ppvObj = &m_editObj;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}

ULONG CEditPrintObj::CEditObj::AddRef()
{
    return m_pParent->AddRef();
}

ULONG CEditPrintObj::CEditObj::Release()
{
    return m_pParent->Release();
}

HRESULT CEditPrintObj::CEditObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}

ULONG CEditPrintObj::CPrintObj::AddRef()
{
    return m_pParent->AddRef();
}

ULONG CEditPrintObj::CPrintObj::Release()
{
    return m_pParent->Release();
}

HRESULT CEditPrintObj::CPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}
```

대부분은 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 구현은 CEditPrintObj 클래스에 배치 됩니다:: Ceditobj 및 ceditprintobj:: Cprintobj에서 코드를 복제 하는 대신 합니다. 따라서 코드의 양을 줄이고 버그를 방지할 수 있습니다. 여기에서 핵심 하다는 IUnknown 인터페이스에서 호출할 수 있습니다 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 모든 인터페이스를 검색할 개체 수를 지원 하 고 각 인터페이스에서 동일한 작업을 수행할 수 있기 합니다. 즉, 모든 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 각 인터페이스에서 사용할 수 있는 함수 동일 하 게 동작 해야 합니다. 이러한 포함된 개체가 "외부 개체"에서 구현을 호출할 수 있도록 하려면 후방 포인터(m_pParent)를 사용합니다. m_pParent 포인터는 CEditPrintObj 생성자 중 초기화됩니다. 그런 다음 CEditPrintObj::CPrintObj::PrintObject 및 CEditPrintObj::CEditObj::EditObject도 구현합니다. 개체를 편집하는 한 가지 기능을 추가하기 위해 약간의 코드가 추가되었습니다. 다행히 인터페이스에서 단일 멤버 함수만 사용하는 것은 매우 특수하지만 발생하는 경우이며, 이런 경우 EditObject 및 PrintObject가 일반적으로 단일 인터페이스로 결합됩니다.

따라서 이러한 간단한 시나리오에 대해서도 설명과 코드가 많습니다. MFC/OLE 클래스는 보다 간단한 대안을 제공합니다. MFC 구현에서는 Windows 메시지가 메시지 맵을 사용하여 래핑되는 방식과 유사한 기술을 사용합니다. 이 기능 이라고 *인터페이스 맵* 이며 다음 섹션에서 설명 합니다.

## <a name="mfc-interface-maps"></a>MFC 인터페이스 맵

MFC/OLE에는 개념과 실행 측면에서 MFC의 "메시지 맵" 및 “디스패치 맵"과 유사한 “인터페이스 맵"의 구현이 포함됩니다. MFC 인터페이스 맵의 핵심 기능은 다음과 같습니다.

- 표준 구현을 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)빌드에 `CCmdTarget` 클래스입니다.

- 유지 관리 하 여 수정 하 고 참조 횟수 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) 고 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)

- 데이터 기반 구현 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))

또한 인터페이스 맵은 다음과 같은 고급 기능을 지원합니다.

- 집계할 수 있는 COM 개체 만들기 지원

- COM 개체의 구현에서 집계 개체 사용 지원

- 연결 및 확장 가능한 구현

집계에 대 한 자세한 내용은 참조는 [집계](/windows/desktop/com/aggregation) 항목입니다.

MFC의 인터페이스 맵 지원은 `CCmdTarget` 클래스를 기반으로 합니다. `CCmdTarget` "*에는*" 수 뿐만 아니라 멤버 함수는 관련 된 모든 참조는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 구현 (참조 횟수를 예를 들어는 `CCmdTarget`). OLE COM을 지원하는 클래스를 만들려면 `CCmdTarget`에서 클래스를 파생시키고 다양한 매크로 및 `CCmdTarget`의 멤버 함수를 사용하여 원하는 인터페이스를 구현합니다. MFC의 구현에서는 중첩 클래스를 사용하여 위의 예제와 매우 유사하게 각 인터페이스 구현을 정의합니다. IUnknown의 표준 구현 및 반복되는 코드 일부를 제거하는 다양한 매크로를 사용하면 더 간단해집니다.

## <a name="interface-map-basics"></a>인터페이스 맵 기본 사항

### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>MFC의 인터페이스 맵을 사용하는 클래스를 구현하려면

1. `CCmdTarget`에서 직접적으로나 간접적으로 클래스를 파생시킵니다.

2. 파생 클래스 정의에서 `DECLARE_INTERFACE_MAP` 함수를 사용합니다.

3. 지원 하려는 각 인터페이스에 대 한 클래스 정의에서 BEGIN_INTERFACE_PART 및 END_INTERFACE_PART 매크로 사용 합니다.

4. 구현 파일에서 BEGIN_INTERFACE_MAP 및 END_INTERFACE_MAP 매크로 사용 하 여 클래스의 인터페이스 맵을 정의 합니다.

5. 지원 되는 각 IID에 대 한 특정 "부품" 클래스의 해당 IID를 매핑할 BEGIN_INTERFACE_MAP 및 END_INTERFACE_MAP 매크로 사이 INTERFACE_PART 매크로 사용 합니다.

6. 지원하는 인터페이스를 나타내는 각 중첩 클래스를 구현합니다.

7. METHOD_PROLOGUE 매크로 사용 하 여 부모 액세스 `CCmdTarget`-파생 개체입니다.

8. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), 및 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 을 위임할 수는 `CCmdTarget` 이러한 함수의 구현 형태가 (`ExternalAddRef`를 `ExternalRelease`, 및 `ExternalQueryInterface`).

위의 CPrintEditObj 예제는 다음과 같이 구현할 수 있습니다.

```cpp
class CPrintEditObj : public CCmdTarget
{
public:
    // member data and member functions for CPrintEditObj go here

// Interface Maps
protected:
    DECLARE_INTERFACE_MAP()

    BEGIN_INTERFACE_PART(EditObj, IEditInterface)
        STDMETHOD_(void, EditObject)();
    END_INTERFACE_PART(EditObj)

    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)
        STDMETHOD_(void, PrintObject)();
    END_INTERFACE_PART(PrintObj)
};
```

위의 선언은 `CCmdTarget`에서 파생 클래스를 만듭니다. DECLARE_INTERFACE_MAP 매크로이 클래스는 사용자 지정 인터페이스 맵이 있는 프레임 워크에 지시 합니다. 또한 BEGIN_INTERFACE_PART 및 END_INTERFACE_PART 매크로 중첩된 클래스를 정의이 경우 CEditObj 및 cprintobj 이름을 (X는 데만 전역 클래스는 "C" 및 인터페이스는 시작 클래스에서 중첩된 클래스를 구분 합니다. 시작 "I"). 이러한 클래스의 두 중첩 멤버, 각각 m_CEditObj와 m_CPrintObj가 만들어집니다. 매크로 자동으로 선언 된 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), 및 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 함수 따라서 있습니다만 함수를 선언 된이 인터페이스: EditObject 및 PrintObject (STDMETHOD는 OLE 매크로 되도록 **_stdcall** virtual 키워드가 대상 플랫폼에 적합 하 게 제공 됩니다).

이 클래스에 대해 인터페이스 맵을 구현하려면

```cpp
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)
END_INTERFACE_MAP()
```

각각 IID_IPrintInterface IID는 m_CPrintObj와 연결하고 IID_IEditInterface는 m_CEditObj와 연결합니다. 합니다 `CCmdTarget` 구현의 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) (`CCmdTarget::ExternalQueryInterface`)이이 맵을 사용 하 여 요청 시 m_CPrintObj 및 m_CEditObj에 대 한 포인터를 반환 합니다. `IID_IUnknown`에 대한 항목은 포함할 필요가 없습니다. `IID_IUnknown`을 요청하는 경우 프레임워크는 맵의 첫 번째 인터페이스(이 경우 m_CPrintObj)를 사용합니다.

BEGIN_INTERFACE_PART 매크로 자동으로 선언 하는 경우에 합니다 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 및 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 함수를 여전히 구현 해야 합니다.

```cpp
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return pThis->ExternalAddRef();
}

ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return pThis->ExternalRelease();
}

HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);
}

void FAR EXPORT CEditPrintObj::XEditObj::EditObject()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    // code to "Edit" the object, whatever that means...
}
```

CEditPrintObj::CPrintObj에 대한 구현은 CEditPrintObj::CEditObj에 대한 위의 정의와 유사합니다. 이러한 함수를 자동으로 생성하는 데 사용할 수 있는 매크로를 만들 수 있었지만(MFC/OLE 개발 초기에 해당) 매크로에서 두 줄 이상의 코드를 생성하는 경우 중단점을 설정하기가 어려워집니다. 따라서 이 코드를 수동으로 확장합니다.

메시지 맵의 프레임워크 구현을 사용하면 다음과 같은 많은 작업을 수행할 필요가 없습니다.

- QueryInterface 구현

- AddRef 및 Release 구현

- 두 인터페이스 모두에서 이러한 기본 제공 메서드 중 하나 선언

또한 프레임워크는 메시지 맵을 내부적으로 사용합니다. 따라서 이미 특정 인터페이스를 지원하고 프레임워크에서 제공하는 인터페이스에 대체 또는 추가 작업을 제공하는 프레임워크 클래스 `COleServerDoc`에서 파생시킬 수 있습니다. 프레임워크는 기본 클래스에서 인터페이스 맵 상속을 완벽하게 지원하기 때문에 가능합니다. 이것이 왜 BEGIN_INTERFACE_MAP 변수로 두 번째 매개 변수는 기본 클래스의 이름을 이유입니다.

> [!NOTE]
> 일반적으로 MFC 버전에서 해당 인터페이스의 포함된 특수화를 상속하는 것만으로는 MFC의 OLE 인터페이스 기본 제공 구현의 구현을 다시 사용할 수 없습니다. 이것이 불가능 때문에 포함 된 액세스 METHOD_PROLOGUE 매크로 사용 `CCmdTarget`-파생된 개체를 의미를 *고정된 오프셋* 에서 포함된 된 개체의는 `CCmdTarget`-파생 개체입니다. 예를 들어 `COleClientItem::XAdviseSink`의 MFC 구현에서 포함된 XMyAdviseSink를 파생시킬 수 없는데, XAdviseSink는 `COleClientItem` 개체의 맨 위로부터 특정 오프셋에 있기 때문입니다.

> [!NOTE]
> 그러나 MFC의 기본 동작을 원하는 모든 함수에 대한 MFC 구현에 위임할 수 있습니다. 이 작업은 `COleFrameHook` 클래스(많은 함수에서 m_xOleInPlaceUIWindow에 위임)에서 `IOleInPlaceFrame`(XOleInPlaceFrame)의 MFC 구현으로 수행합니다. 이 디자인은 여러 인터페이스를 구현하는 개체의 런타임 크기를 줄이기 위해 선택되었으며, 이전 섹션에서 사용된 m_pParent 같은 후방 포인터가 필요하지 않습니다.

### <a name="aggregation-and-interface-maps"></a>집계 및 인터페이스 맵

MFC는 독립 실행형 COM 개체뿐만 아니라 집계도 지원합니다. 자체 집계는 여기서 설명 하는 너무 복잡 한 항목 참조 된 [집계](/windows/desktop/com/aggregation) 집계에 대 한 자세한 내용은 항목입니다. 여기서는 프레임워크 및 인터페이스 맵에 기본 제공되는 집계에 대한 지원에 대해 간략하게 설명합니다.

집계를 사용 하는 방법은 두 가지 있습니다. (1)-집계를 지 원하는 COM 개체를 사용 하는 중 및 (2)-다른 집계할 수 있는 개체를 구현 하는 중입니다. 이러한 기능을 "집계 개체 사용" 및 “개체를 집계할 수 있도록 만들기"라고 합니다. MFC는 둘 다를 지원합니다.

### <a name="using-an-aggregate-object"></a>집계 개체 사용

집계 개체를 사용하려면 집계를 QueryInterface 메커니즘에 연결할 수 있는 몇 가지 방법이 있어야 합니다. 즉, 집계 개체는 개체의 네이티브 요소인 것처럼 동작해야 합니다. 그렇다면이 동률 INTERFACE_PART 매크로 외에도 MFC의 인터페이스 맵 메커니즘에는 중첩된 개체가 IID에 매핑된 경우 선언할 수도 있습니다 집계 개체의 일부로 프로그램 `CCmdTarget` 클래스를 파생 합니다. 이렇게 하려면 INTERFACE_AGGREGATE 매크로 사용 됩니다. 멤버 변수를 지정할 수 있습니다 (에 대 한 포인터 이어야 합니다는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 또는 파생 클래스)에서 인터페이스 맵 메커니즘에 통합 되어야 하는 합니다. 포인터가 NULL이 아닌 경우 시기 `CCmdTarget::ExternalQueryInterface` 가 호출 프레임 워크를 자동으로 호출 집계 개체의 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 멤버 함수를 합니다 `IID` 요청 중 하나가 아닌 네이티브 `IID`s 지 원하는 `CCmdTarget` 개체 자체입니다.

#### <a name="to-use-the-interfaceaggregate-macro"></a>INTERFACE_AGGREGATE 매크로를 사용하려면

1. 집계 개체에 대한 포인터를 포함할 멤버 변수(`IUnknown*`)를 선언합니다.

2. 멤버 변수를 이름으로 참조 하는 인터페이스 맵에, INTERFACE_AGGREGATE 매크로 포함 합니다.

3. 특정 지점(일반적으로 `CCmdTarget::OnCreateAggregates` 중)에서 멤버 변수를 NULL이 아닌 다른 값으로 초기화합니다.

예를 들어:

```cpp
class CAggrExample : public CCmdTarget
{
public:
    CAggrExample();

protected:
    LPUNKNOWN m_lpAggrInner;
    virtual BOOL OnCreateAggregates();

    DECLARE_INTERFACE_MAP()
    // "native" interface part macros may be used here
};

CAggrExample::CAggrExample()
{
    m_lpAggrInner = NULL;
}

BOOL CAggrExample::OnCreateAggregates()
{
    // wire up aggregate with correct controlling unknown
    m_lpAggrInner = CoCreateInstance(CLSID_Example,
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)
        return FALSE;
    // optionally, create other aggregate objects here
    return TRUE;
}

BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)
    // native "INTERFACE_PART" entries go here
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)
END_INTERFACE_MAP()
```

m_lpAggrInner 변수는 생성자에서 NULL로 초기화됩니다. 프레임 워크의 기본 구현에서 NULL 멤버 변수를 무시 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))합니다. `OnCreateAggregates`는 실제로 집계 개체를 만들 수 있는 좋은 위치입니다. `COleObjectFactory`의 MFC 구현 외부에서 개체를 만드는 경우 명시적으로 호출해야 합니다. `CCmdTarget::GetControllingUnknown`의 사용뿐만 아니라 `CCmdTarget::OnCreateAggregates`에서 집계를 만드는 이유는 집계할 수 있는 개체 만들기에 대해 설명할 때 명확해집니다.

이 기술은 집계 개체가 지원하는 모든 인터페이스와 네이티브 인터페이스에 개체에 제공합니다. 집계에서 지원하는 인터페이스의 하위 집합만 원하는 경우 `CCmdTarget::GetInterfaceHook`을 재정의할 수 있습니다. 이렇게 하면 매우 낮아집니다, 비슷합니다 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))합니다. 일반적으로 집계에서 지원하는 모든 인터페이스를 원합니다.

### <a name="making-an-object-implementation-aggregatable"></a>개체 구현을 집계할 수 있도록 만들기

개체를 집계할 수 있도록 구현의 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)를 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), 및 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 를 "제어 알 수 없습니다."를 위임 해야 합니다 즉, 한 개체의 일부가 되도록 위임 해야 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)하십시오 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), 및 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 를 다른 개체에서 파생 되기도 [ IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)합니다. 이 "제어 알 수 없음"은 개체가 생성될 때 개체에 제공됩니다. 즉, `COleObjectFactory`의 구현에 제공됩니다. 이 구현에는 약간의 오버헤드가 수반되므로 경우에 따라 바람직하지 않으므로 MFC에서는 선택 사항으로 만듭니다. 개체를 집계할 수 있도록 하려면 개체의 생성자에서 `CCmdTarget::EnableAggregation`을 호출합니다.

개체도 집계를 사용하는 경우 올바른 “제어 알 수 없음"을 집계 개체에도 전달해야 합니다. 일반적으로 다음과 같습니다 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 포인터는 집계를 만들 때 개체에 전달 됩니다. 예를 들어 pUnkOuter 매개 변수는 `CoCreateInstance`를 사용하여 만든 개체에 대한 “제어 알 수 없음"입니다. 올바른 “제어 알 수 없음" 포인터는 `CCmdTarget::GetControllingUnknown`을 호출하여 검색할 수 있습니다. 그러나 해당 함수에서 반환된 값은 생성자 중 올바르지 않습니다. 따라서 `CCmdTarget::OnCreateAggregates`의 재정의에서만 집계를 만드는 것이 좋습니다. 여기서 `GetControllingUnknown`의 반환 값은 `COleObjectFactory` 구현에서 만들어진 경우에도 신뢰할 수 있습니다.

또한 개체는 인공 참조 개수를 추가하거나 해제하는 경우 올바른 참조 개수를 조작해야 합니다. 이렇게 하려면 항상 `InternalRelease` 및 `InternalAddRef` 대신 `ExternalAddRef` 및 `ExternalRelease`를 호출합니다. 집계를 지원하는 클래스에서는 `InternalRelease` 또는 `InternalAddRef`를 거의 호출하지 않습니다.

## <a name="reference-material"></a>참조 자료

고유한 인터페이스 정의 또는 프레임워크의 OLE 인터페이스 구현 재정의 같은 고급 OLE 사용에서는 기본 인터페이스 맵 메커니즘을 사용해야 합니다.

이 섹션에서는 이러한 고급 기능을 구현하는 데 사용되는 각 매크로 및 API에 대해 설명합니다.

### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation — 함수 설명

```cpp
void EnableAggregation();
```

#### <a name="remarks"></a>설명

이 형식의 개체에 대해 OLE 집계를 지원하려면 파생 클래스의 생성자에서 이 함수를 호출합니다. 이 함수는 집계할 수 있는 개체에 필요한 특수 IUnknown 구현을 준비합니다.

### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface — 함수 설명

```cpp
DWORD ExternalQueryInterface(
    const void FAR* lpIID,
    LPVOIDFAR* ppvObj
);
```

#### <a name="parameters"></a>매개 변수

*lpIID*<br/>
IID(QueryInterface 첫 번째 인수)에 대한 far 포인터

*ppvObj*<br/>
IUnknown*(QueryInterface의 두 번째 인수)에 대한 포인터

#### <a name="remarks"></a>설명

클래스가 구현하는 각 인터페이스에 대해 IUnknown 구현에서 이 함수를 호출합니다. 이 함수는 개체의 인터페이스 맵에 기반을 둔 QueryInterface의 표준 데이터 기반 구현을 제공합니다. 반환 값을 HRESULT에 캐스팅해야 합니다. 개체가 집계되는 경우 이 함수는 로컬 인터페이스 맵을 사용하는 대신 "controlling IUnknown"을 호출합니다.

### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef — 함수 설명

```cpp
DWORD ExternalAddRef();
```

#### <a name="remarks"></a>설명

클래스가 구현하는 각 인터페이스에 대해 IUnknown::AddRef 구현에서 이 함수를 호출합니다. 반환 값은 CCmdTarget 개체에 대한 새 참조 개수입니다. 개체가 집계되는 경우 이 함수는 로컬 참조 개수를 조작하는 대신 "controlling IUnknown"을 호출합니다.

### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease — 함수 설명

```cpp
DWORD ExternalRelease();
```

#### <a name="remarks"></a>설명

클래스가 구현하는 각 인터페이스에 대해 IUnknown::Release 구현에서 이 함수를 호출합니다. 반환 값은 개체에 대한 새 참조 개수를 나타냅니다. 개체가 집계되는 경우 이 함수는 로컬 참조 개수를 조작하는 대신 "controlling IUnknown"을 호출합니다.

### <a name="declareinterfacemap--macro-description"></a>DECLARE_INTERFACE_MAP — 매크로 설명

```cpp
DECLARE_INTERFACE_MAP
```

#### <a name="remarks"></a>설명

이 매크로는 인터페이스 맵이 포함될 `CCmdTarget`에서 파생 클래스에서 사용합니다. 거의 동일한 방식으로 DECLARE_MESSAGE_MAP 사용 합니다. 이 매크로 호출은 일반적으로 헤더(.H) 파일에 있는 클래스 정의에 배치해야 합니다. DECLARE_INTERFACE_MAP 클래스 구현 파일에서 인터페이스 맵을 정의 해야 합니다 (합니다. CPP) BEGIN_INTERFACE_MAP 및 END_INTERFACE_MAP 매크로 사용 하 여 합니다.

### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>BEGIN_INTERFACE_PART 및 END_INTERFACE_PART — 매크로 설명

```cpp
BEGIN_INTERFACE_PART(localClass, iface);
END_INTERFACE_PART(localClass)
```

#### <a name="parameters"></a>매개 변수

*localClass*<br/>
인터페이스를 구현하는 클래스의 이름

*iface*<br/>
이 클래스에서 구현하는 인터페이스의 이름

#### <a name="remarks"></a>설명

클래스에서 구현할 각 인터페이스에 대해 BEGIN_INTERFACE_PART 및 END_INTERFACE_PART 쌍을 지정 해야 합니다. 이러한 매크로는 정의하는 OLE 인터페이스에서 파생된 로컬 클래스뿐만 아니라 해당 클래스의 포함된 멤버 변수를 정의합니다. 합니다 [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)를 [릴리스](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), 및 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 멤버는 자동으로 선언 합니다. 구현할 인터페이스의 일부인 다른 멤버 함수에 대 한 선언을 포함 해야 합니다 (해당 선언 사이 위치한 BEGIN_INTERFACE_PART 및 END_INTERFACE_PART 매크로).

합니다 *iface* 인수는 같은 구현 하려는 OLE 인터페이스 `IAdviseSink`, 또는 `IPersistStorage` (또는 사용자 고유의 사용자 지정 인터페이스).

합니다 *localClass* 인수는 정의 될 로컬 클래스의 이름입니다. 'X'는 이름 앞에 자동으로 추가됩니다. 이 명명 규칙은 이름이 동일한 전역 클래스와의 충돌을 방지하는 데 사용됩니다. 또한 동일 포함된 된 멤버의 이름 합니다 *localClass* 'm_x'이 접두사로 점을 제외 하 고 이름을 지정 합니다.

예를 들어:

```cpp
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)
    STDMETHOD_(void, OnDataChange)(LPFORMATETC, LPSTGMEDIUM);
    STDMETHOD_(void, OnViewChange)(DWORD, LONG);
    STDMETHOD_(void, OnRename)(LPMONIKER);
    STDMETHOD_(void, OnSave)();
    STDMETHOD_(void, OnClose)();
END_INTERFACE_PART(MyAdviseSink)
```

IAdviseSink에서 파생된 XMyAdviseSink라는 로컬 클래스와 이 로컬 클래스가 선언되는 클래스의 멤버인 m_xMyAdviseSink.Note를 정의합니다.

> [!NOTE]
> 사용 하 여 시작 하는 줄 `STDMETHOD`_ OLE2에서 기본적으로 복사 됩니다. H 약간 수정 합니다. OLE2에서 복사하면 해결하기 어려운 오류를 줄일 수 있습니다.

### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>BEGIN_INTERFACE_MAP 및 END_INTERFACE_MAP — 매크로 설명

```cpp
BEGIN_INTERFACE_MAP(theClass, baseClass)
END_INTERFACE_MAP
```

#### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 정의할 클래스

*baseClass*<br/>
클래스 *theClass* 에서 파생 됩니다.

#### <a name="remarks"></a>설명

BEGIN_INTERFACE_MAP 및 END_INTERFACE_MAP 매크로 실제로 인터페이스 맵을 정의 하는 구현 파일에서 사용 됩니다. 구현 되는 각 인터페이스에 대 한 하나 이상의 INTERFACE_PART 매크로 호출이 있습니다. 클래스를 사용 하는 각 집계에 대 한 하나의 INTERFACE_AGGREGATE 매크로 호출이 있습니다.

### <a name="interfacepart--macro-description"></a>INTERFACE_PART — 매크로 설명

```cpp
INTERFACE_PART(theClass, iid, localClass)
```

#### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 포함하는 클래스의 이름

*iid*<br/>
포함된 클래스에 매핑될 `IID`

*localClass*<br/>
로컬 클래스의 이름('X' 제외)

#### <a name="remarks"></a>설명

이 매크로 개체에서 지원할 각 인터페이스에 대 한 BEGIN_INTERFACE_MAP 매크로 및 END_INTERFACE_MAP 매크로 간에 사용 됩니다. 에 의해 표시 되는 클래스의 멤버에 IID를 매핑할 수 있습니다 *theClass* 하 고 *localClass*합니다. 'M_x'에 추가할 합니다 *localClass* 자동으로 합니다. 단일 멤버에 둘 이상의 `IID`를 연결할 수 있습니다. 이 기능은 "최다 파생" 인터페이스만 구현하고 모든 중간 인터페이스도 제공하려는 경우에 매우 유용합니다. 좋은 예로 `IOleInPlaceFrameWindow` 인터페이스가 있습니다. 해당 계층 구조는 다음과 같습니다.

```Hierarchy
IUnknown
    IOleWindow
        IOleUIWindow
            IOleInPlaceFrameWindow
```

개체를 구현 하는 경우 `IOleInPlaceFrameWindow`, 클라이언트는 `QueryInterface` 이러한 인터페이스 중 하나: `IOleUIWindow`를 `IOleWindow`, 또는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), "최다 파생된" 인터페이스 외에도 `IOleInPlaceFrameWindow` (것은 실제로 구현). 이 처리 하려면 각 기본 인터페이스를 매핑할 둘 이상의 INTERFACE_PART 매크로 사용할 수 있습니다는 `IOleInPlaceFrameWindow` 인터페이스:

클래스 정의 파일:

```cpp
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)
```

클래스 구현 파일:

```cpp
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)
END_INTERFACE_MAP
```

프레임워크는 항상 필요한 IUnknown을 관리합니다.

### <a name="interfacepart--macro-description"></a>INTERFACE_PART — 매크로 설명

```cpp
INTERFACE_AGGREGATE(theClass, theAggr)
```

#### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 포함하는 클래스의 이름

*theAggr*<br/>
집계될 멤버 변수의 이름

#### <a name="remarks"></a>설명

이 매크로는 클래스에서 집계 개체를 사용하고 있음을 프레임워크에 알리는 데 사용됩니다. BEGIN_INTERFACE_PART 및 END_INTERFACE_PART 매크로 사이 나타나야 합니다. 집계 개체는 별도 개체에서 파생 된 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)합니다. 집계 및 INTERFACE_AGGREGATE 매크로 사용 하 여 집계에서 지 원하는 표시 개체에 의해 직접 지원 되는 모든 인터페이스를 만들 수 있습니다. 합니다 *theAggr* 인수는 이름에서 파생 된 클래스의 멤버 변수의 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) (직접 또는 간접적으로). 모든 INTERFACE_AGGREGATE 매크로 INTERFACE_PART 매크로 인터페이스 맵에 배치 되는 경우 수행 해야 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
