---
title: 'TN033: MFC의 DLL 버전'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.dll
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
ms.openlocfilehash: 4bfc60e20a073dd34945b91dd48ba82cdf4ab9f3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767784"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC의 DLL 버전

이 방법을 설명 MFCxx.DLL를 사용할 수 있습니다 MFCxxD.DLL (여기서 x는 MFC 버전 번호) MFC 응용 프로그램 및 MFC 확장명 Dll 사용 하 여 동적 연결 라이브러리를 공유 합니다. 기본 MFC Dll에 대 한 자세한 내용은 참조 하세요. [DLL의 일부로 MFC 사용 하 여](../mfc/tn011-using-mfc-as-part-of-a-dll.md)입니다.

이 기술 노트에서는 Dll의 세 가지 측면을 설명합니다. 마지막 두 개는 고급 사용자:

- [MFC 확장 DLL을 빌드하는 방법을](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC의 DLL 버전을 사용 하는 MFC 응용 프로그램을 빌드하는 방법을](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [구현 된 MFC 동적 연결 라이브러리를 공유 하는 방법](#_mfcnotes_how_the_mfc30.dll_is_implemented)

비 MFC 응용 프로그램 (이 기본 MFC DLL)를 사용 하 여 사용할 수 있는 MFC를 사용 하 여 DLL을 빌드하는 데 관심이 있다면 가리킵니다 [기술 참고 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)합니다.

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL 지원의 개요를 제공 합니다. 용어 및 파일

**기본 MFC DLL**: 기본 MFC DLL를 사용 하 여 MFC 클래스 중 일부를 사용 하 여 독립 실행형 DLL을 빌드할 수 있습니다. 앱/DLL 경계를 넘어 인터페이스 "C" 인터페이스 이며 클라이언트 응용 프로그램이 MFC 응용 프로그램을 사용할 필요가 없습니다.

MFC 1.0에서 지원 되는 DLL 지원의 버전입니다. 설명한 것 [기술 참고 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) 및 MFC 고급 개념 샘플 [DLLScreenCap](../overview/visual-cpp-samples.md)합니다.

> [!NOTE]
> 시각적 개체를 기준으로 C++ 버전 4.0, 용어 **USRDLL** 는 사용 되지 않으며 정적으로 MFC에 링크 된 기본 MFC DLL로 대체 되었습니다. 일반 동적으로 MFC에 링크 MFC DLL을 빌드할 수 있습니다.

MFC 3.0 (이상)는 OLE 및 데이터베이스 클래스를 포함 한 모든 새 기능을 사용 하 여 기본 MFC Dll을 지원 합니다.

**AFXDLL**: 이 MFC 라이브러리의 공유 버전 라고도 합니다. 이 MFC 2.0에 추가 된 새 DLL 지원 합니다. MFC 라이브러리 자체는 여러 Dll (아래 설명 참조) 하 고 클라이언트 응용 프로그램 또는 DLL을 동적으로 필요한 Dll 링크. 응용 프로그램/DLL 경계를 넘어 인터페이스는 C++/MFC 클래스 인터페이스입니다. 클라이언트 응용 프로그램에는 MFC 응용 프로그램 이어야 합니다. MFC 3.0 기능을 모두 지원 (예외: 유니코드 지원 되지 않습니다 데이터베이스 클래스에 대 한).

> [!NOTE]
> 시각적 개체를 기준으로 C++ 버전 4.0이이 유형의 DLL "확장 DLL입니다." 라고

이 포함 하는 MFC DLL 집합 전체를 가리키도록 MFCxx.DLL를 사용 합니다.

- 디버그: MFCxxD.DLL (결합) 및 MFCSxxD.LIB (정적).

- 릴리스: (결합) MFCxx.DLL 및 MFCSxx.LIB (정적).

- 유니코드 디버그: MFCxxUD.DLL (결합) 및 MFCSxxD.LIB (정적).

- 유니코드 릴리스: MFCxxU.DLL (결합) 및 MFCSxxU.LIB (정적).

> [!NOTE]
> MFCSxx [U] [D]입니다. LIB 라이브러리에서 사용 되는 MFC와 함께 공유 Dll입니다. 이러한 라이브러리에 응용 프로그램 또는 DLL에 정적으로 연결 되어 있어야 하는 코드가 있습니다.

해당 하는 응용 프로그램 링크 라이브러리를 가져옵니다.

- 디버그: MFCxxD.LIB

- 릴리스: MFCxx.LIB

- 유니코드 디버그: MFCxxUD.LIB

- 유니코드 릴리스: MFCxxU.LIB

"MFC 확장명 DLL"은 MFCxx.DLL 때 작성 된 DLL (및/또는 기타 MFC Dll을 공유). 여기 MFC 구성 요소 아키텍처를 시작합니다. 다른 MFC 같은 도구 키트를 빌드하거나 유용한 클래스는 MFC 클래스에서 파생 하는 경우에 DLL에 배치할 수 있습니다. 클라이언트 응용 프로그램과 마찬가지로 DLL MFCxx.DLL를 사용 합니다. 이렇게 하면 다시 사용할 수 있는 리프 클래스, 재사용이 가능한 기본 클래스 및 재사용 가능한 문서/보기 클래스입니다.

## <a name="pros-and-cons"></a>장점 및 단점

MFC의 공유 버전을 사용 하는 이유는

- 공유 라이브러리를 사용 하 여 더 작은 응용 프로그램 (대부분의 MFC 라이브러리를 사용 하는 최소한의 응용 프로그램을 보다 작은 10k) 발생할 수 있습니다.

- MFC의 공유 버전 MFC 확장명 Dll 및 기본 MFC Dll을 지원합니다.

- 공유 MFC 라이브러리를 사용 하는 응용 프로그램을 구축 MFC를 직접 링크할 필요가 없기 때문에 정적으로 연결 된 MFC 응용 프로그램을 빌드하는 것 보다 빠릅니다. 특히 그렇습니다 **디버그** 링커가 디버그 정보를 압축 해야 합니다는 빌드-디버그 정보가 이미 들어 있는 DLL에 링크를 여는 응용 프로그램 내에 압축 해야 할 디버그 정보가 줄어듭니다.

이유 해야 사용 하면 MFC의 공유 버전.

- MFCxx.DLL (및 기타)를 제공 하는 필요한 전달 공유 라이브러리를 사용 하는 응용 프로그램을 사용 하 여 라이브러리입니다. MFCxx.DLL 여러 Dll과 같은 재배포할 되었지만 여전히 설치 프로그램에서 DLL를 설치 해야 합니다. 또한 프로그램과 MFC Dll에서 모두 사용 되는 C 런타임 라이브러리를 포함 하는 MSVCRTxx.DLL를 발송 해야 합니다.

##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> MFC 확장 DLL을 작성 하는 방법

MFC 확장명 DLL은 MFC 클래스의 기능을 멋지게 꾸밀에 기록 하는 함수와 클래스를 포함 하는 DLL입니다. MFC 확장명 DLL 응용 프로그램을를 사용 하 여 몇 가지 추가 고려 사항에서와 동일한 방식으로 공유 MFC Dll을 사용 합니다.

- 빌드 프로세스는 몇 가지 추가 컴파일러 및 링커 옵션을 사용 하 여 공유 MFC 라이브러리를 사용 하는 응용 프로그램을 구축 하는 것과 비슷합니다.

- MFC 확장명 DLL 없는 `CWinApp`-클래스를 파생 합니다.

- MFC 확장명 DLL에는 특별 한 제공 해야 합니다 `DllMain`합니다. 응용 프로그램 마법사에서 제공 된 `DllMain` 수정할 수 있는 함수입니다.

- MFC 확장명 DLL 초기화 루틴을 만들려고 하면 일반적으로 `CDynLinkLibrary` MFC 확장명 DLL 하려는 경우 내보내기 `CRuntimeClass`es 또는 응용 프로그램에는 리소스입니다. 파생된 클래스의 `CDynLinkLibrary` MFC 확장 DLL에서 응용 프로그램별 데이터를 유지 해야 하는 경우 사용할 수 있습니다.

이러한 고려 사항은 아래에서 자세히 설명 합니다. MFC 고급 개념 샘플도 참조 해야 [DLLHUSK](../overview/visual-cpp-samples.md) 있으므로 보여 줍니다.

- 공유 라이브러리를 사용 하 여 응용 프로그램을 빌드합니다. (DLLHUSK 합니다. EXE가 동적으로 연결 하는 MFC 라이브러리 뿐 아니라 다른 Dll을 MFC 응용 프로그램입니다.)

- MFC 확장 DLL을 빌드합니다. (특수 플래그와 같은 유의 `_AFXEXT` MFC 확장 DLL 빌드에 사용 되는)

- MFC 확장명 Dll의 두 가지 예입니다. 하나는 제한 된 내보내기 (TESTDLL1)를 사용 하 여 MFC 확장명 DLL 및 다른에 나와 있는 전체 클래스 인터페이스 (TESTDLL2) 내보내기의 기본 구조를 보여줍니다.

클라이언트 응용 프로그램 및 모든 MFC 확장명 Dll MFCxx.DLL의 동일한 버전을 사용 해야 합니다. MFC DLL의 규칙을 따르고 모두 디버그를 제공 해야 하 고 소매 (/release) MFC 확장 DLL의 버전입니다. 이렇게 하면 클라이언트 프로그램을 응용 프로그램의 디버그 및 일반 정품 버전을 빌드하고 모든 Dll의 정품 버전을 적절 한 디버그를 사용 하 여 연결 합니다.

> [!NOTE]
>  때문에 C++ 이름 꾸미기 및 내보내기 문제는 MFC 확장 DLL에서에서 내보내기 목록 다를 수 동일한 DLL의 디버그 버전과 소매 간의 다양 한 플랫폼에 대 한 합니다. 소매 MFCxx.DLL에 약 2000 내보낸 진입점이 있습니다. 디버그 MFCxxD.DLL에 약 3000 내보낸 진입점입니다.

### <a name="quick-note-on-memory-management"></a>메모리 관리에 대 한 빠른 참고

메모리 관리 ","이 기술 노트의 끝 섹션 공유 버전의 MFC 사용 하 여 MFCxx.DLL 구현에 설명 합니다. 방금 DLL 여기에 설명 된 MFC 확장을 구현 하려면 알아야 할 정보입니다.

MFCxx.DLL 및 클라이언트 응용 프로그램의 주소 공간에 로드 된 모든 MFC 확장명 Dll 사용할지 동일한 메모리 할당자, 리소스를 로드 및 기타 MFC "전역" 상태 동일한 응용 프로그램 처럼 합니다. 비 MFC DLL 라이브러리와 MFC에 정적으로 연결 된 기본 MFC Dll 정반대를 수행 하 고 각 DLL이 자체 메모리 풀에서 할당 하도록 하기 때문에 유효 합니다.

MFC 확장 DLL이 메모리를 할당 하는 경우 다른 응용 프로그램에서 할당 된 개체를 사용 하 여 해당 메모리 약간 자유롭게 수 있습니다. 또한 공유 MFC 라이브러리를 사용 하는 응용 프로그램이 충돌할 경우 운영 체제의 보호는 해당 DLL을 공유 하는 다른 MFC 응용 프로그램의 무결성을 유지 합니다.

마찬가지로 다른 "전역" MFC 상태는 리소스를 로드 하려면 현재 실행 파일과 같은 클라이언트 응용 프로그램 및 모든 MFC 확장명 Dll 뿐만 아니라 자체 MFCxx.DLL 간에 공유 됩니다.

### <a name="building-an-mfc-extension-dll"></a>MFC 확장 DLL 빌드

응용 프로그램 마법사를 사용 하 여 MFC 확장명 DLL 프로젝트를 만들려면 하 고 적절 한 컴파일러 및 링커 설정이 자동으로 생성 됩니다. 또한 생성 된를 `DllMain` 수정할 수 있는 함수입니다.

MFC 확장 DLL 기존 프로젝트를 변환 하는 경우 공유 버전의 MFC 사용 하 여 응용 프로그램을 구축 하기 위한 표준 규칙을 사용 하 여 시작한 다음을 수행 합니다.

- 추가 **/D_AFXEXT** 컴파일러 플래그입니다. 프로젝트 속성 대화 상자에서 C를 선택 /C++ 노드. 전처리기 범주를 선택 합니다. 추가 `_AFXEXT` 매크로 정의 필드의 각 항목 세미콜론으로 구분 합니다.

- 제거 된 **/Gy** 컴파일러 스위치입니다. 프로젝트 속성 대화 상자에서 C를 선택 /C++ 노드. 코드 생성 범주를 선택 합니다. "함수 수준 링크 사용" 옵션을 활성화 하지 않았음을 확인 합니다. 이 쉽게 링커 참조 되지 않는 함수를 제거 하지는 않으므로 클래스를 내보냅니다. 원래 프로젝트 일반 빌드에 사용 되는 경우 MFC DLL 정적으로 MFC에 링크 하, 변경 합니다 **[d] /MT** 컴파일러 옵션을 **/MD [d]** 합니다.

- Export 라이브러리를 사용 하 여 빌드를 **/DLL** 링크 하는 옵션입니다. 이 대상 형식으로 Win32 동적 연결 라이브러리를 지정 하는 새 대상을 만들 때 설정 됩니다.

### <a name="changing-your-header-files"></a>헤더 파일 변경

MFC 확장 DLL의 목표는 일반적으로 하나 이상의 응용 프로그램이 해당 기능을 사용할 수 있는 몇 가지 일반적인 기능을 내보내려면 합니다. 이 클래스 및 클라이언트 응용 프로그램에 사용할 수 있는 전역 함수 내보내기에 따라 결정 합니다.

이 작업을 수행 하기 위해 가져오기 또는 내보내기 적절 하 게 표시 되어 멤버 함수의 각 되도록 해야 합니다. 이렇게 하려면 특수 선언: `__declspec(dllexport)` 고 `__declspec(dllimport)`입니다. 클래스는 클라이언트 응용 프로그램에서 사용 되는 경우로 선언할 수 있도록 하려면 `__declspec(dllimport)`합니다. MFC 확장명 DLL 자체를 빌드할 때 이러한로 선언 해야 `__declspec(dllexport)`합니다. 또한 함수는 실제로 내보내야 하며, 클라이언트 프로그램 로드 시에 바인딩할 수 있도록 합니다.

전체 클래스를 내보내려면 `AFX_EXT_CLASS` 클래스 정의에서 합니다. 이 매크로로 프레임 워크에 의해 정의 됩니다 `__declspec(dllexport)` 때 `_AFXDLL` 및 `_AFXEXT` 정의로 정의 되지만 `__declspec(dllimport)` 때 `_AFXEXT` 정의 되어 있지 않습니다. `_AFXEXT` MFC 확장 DLL을 빌드할 때에 위에서 설명한 대로 정의 됩니다. 예를 들어:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않는 경우

경우에 따라 다음 멤버 뿐만 아니라 개별 필요한 클래스를 내보내려면는 것이 좋습니다. 예를 들어 내보내는 경우는 `CDialog`-파생 클래스에서 내보내기 생성자만 필요할 및 `DoModal` 호출 합니다. DLL의를 사용 하 여 이러한 멤버를 내보낼 수 있습니다. DEF 파일을 사용할 수 있습니다도 `AFX_EXT_CLASS` 내보내야 할 개별 멤버에 대해 거의 동일한 방법입니다.

예를 들어:

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

이렇게 하면 클래스의 모든 멤버를 더 이상 내보내지 않으므로 때문에 또 다른 문제는에 직면할 수도 없습니다. MFC 매크로 작동 방식에서에 문제가 있습니다. 다양 한 MFC의 도우미 매크로 실제로 선언 또는 데이터 멤버를 정의 합니다. 따라서 이러한 데이터 멤버 DLL에서 내보낸 해야 합니다.

예를 들어, MFC 확장 DLL을 빌드할 때 DECLARE_DYNAMIC 매크로 다음과 같이 정의 됩니다.

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

시작 하는 줄 "정적 `AFX_DATA`" 클래스 내에서 정적 개체를 선언 하는 합니다. 이 클래스를 올바르게 내보내고 클라이언트에서 런타임 정보에 액세스 합니다. 이 정적 개체를 내보내야 할 EXE를 합니다. 정적 개체는 한정자로 선언 되었으므로 `AFX_DATA`를 정의 해야 `AFX_DATA` 되도록 `__declspec(dllexport)` DLL을 빌드할 때으로 정의 `__declspec(dllimport)` 실행 클라이언트를 빌드할 때입니다.

위에서 설명 했 듯이 `AFX_EXT_CLASS` 이 방식으로 이미 정의 되어 있습니다. 다시 정의 하기만 하면 `AFX_DATA` 동일 하 `AFX_EXT_CLASS` 클래스 정의 해결 합니다.

예를 들어:

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS
class CExampleView : public CView
{
    DECLARE_DYNAMIC()
    // ... class definition ...
};
#undef  AFX_DATA
#define AFX_DATA
```

MFC는 항상 사용 합니다 `AFX_DATA` 이러한 모든 시나리오에 대 한이 기술은 작동 하므로 해당 매크로 내에서 정의 하는 데이터 항목에는 기호입니다. 예를 들어 DECLARE_MESSAGE_MAP에 대 한 작동 합니다.

> [!NOTE]
> 클래스의 선택한 멤버 보다는 전체 클래스를 내보내는 경우 정적 데이터 멤버는 자동으로 내보내집니다.

동일한 기법을 사용 하 여 자동으로 내보내기는 `CArchive` DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로 사용 하는 클래스에 대 한 추출 연산자입니다. 클래스 선언을 괄호를 사용 하 여 보관 연산자를 내보낼 (에 합니다. H 파일)를 다음 코드로:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-afxext"></a>_AFXEXT의 제한 사항

_를 사용할 수 있습니다**AFXEXT** MFC 확장 Dll MFC 확장명 Dll의 여러 계층 않아도 하기만에 전처리기 기호입니다. MFC 확장명 Dll 호출 또는 사용자 고유의 MFC 확장명 Dll MFC 클래스에서 파생 한 후에 클래스에서 파생 되는 경우에 모호성을 피하기 위해 사용자 고유의 전처리기 기호를 사용 해야 합니다.

문제는 해당에서 Win32, 모든 데이터를 명시적으로 선언 해야 `__declspec(dllexport)` DLL에서 내보낸 경우 및 `__declspec(dllimport)` DLL에서 가져와야 하는 경우. 정의 하는 경우 `_AFXEXT`, MFC 헤더 했는지 `AFX_EXT_CLASS` 올바르게 정의 되어 있습니다.

있는 경우 여러 계층, 기호 등 `AFX_EXT_CLASS` MFC 확장 DLL 있습니다 될 새 클래스를 내보낼 뿐만 아니라 다른 MFC 확장명 DLL에서에서 다른 클래스를 가져올 하므로 충분 하지 않습니다. 이 문제를 처리 하기 위해 DLL 자체 DLL을 사용 하 여 작성할 수 있도록 지정 하는 특수 전처리기 기호를 사용 합니다. 예를 들어 두 MFC 확장명 Dll 고 A.DLL, B.DLL 한다고 가정 합니다. 각각는 각각 A.H B.H에 일부 클래스를 내보냅니다. B.DLL은 A.DLL에서 클래스를 사용합니다. 헤더 파일에는 다음과 같이 표시 됩니다.

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

사용 하 여 빌드 A.DLL 빌드되면 **/DA_IMPL** B.DLL를 빌드할 때 사용 하 여 작성 되었습니다 **/DB_IMPL**합니다. 각 DLL에 대 한 별도 기호를 사용해 CExampleB 내보낸이 고 CExampleA B.DLL을 빌드할 때 가져옵니다. CExampleA는 A.DLL을 빌드할 때 내보내고 가져올 B.DLL (또는 다른 클라이언트)에서 사용 하는 경우.

기본 제공을 사용 하는 경우이 유형의 계층을 수행할 수 없습니다 `AFX_EXT_CLASS` 고 `_AFXEXT` 전처리기 기호입니다. 위에서 설명한 기술을 자체 MFC 메커니즘에서는 해당 OLE, 데이터베이스 및 네트워크 MFC 확장명 Dll을 작성할 때 사용 방식으로이 문제를 해결 합니다.

### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않는 경우

마찬가지로 전체 클래스를 내보내지 않는 경우 각별히 주의 해야 합니다. MFC 매크로 만들어 필요한 데이터 항목 내보내집니다 확인 해야 합니다. 다시 정의 하 여 이렇게 `AFX_DATA` 특정 클래스의 매크로를 합니다. 이렇게 해야 언제 든 지 전체 클래스를 내보내지 않습니다.

예를 들어:

```cpp
// A.H
#ifdef A_IMPL
    #define CLASS_DECL_A  _declspec(dllexport)
#else
    #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
    DECLARE_DYNAMIC()
    CLASS_DECL_A int SomeFunction();
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

다음은 MFC 확장 DLL에 대 한 기본 소스 파일에 배치 해야 하는 정확한 코드입니다. 표준 포함 한 후 가져와야 합니다. 응용 프로그램 마법사를 사용 하 여 MFC 확장 DLL에 대 한 시작 파일을 만들 때이 제공을 `DllMain` 있습니다.

```cpp
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      // MFC extension DLL one-time initialization
      if (!AfxInitExtensionModule(
             extensionDLL, hInstance))
         return 0;

      // TODO: perform other initialization tasks here
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      // MFC extension DLL per-process termination
      AfxTermExtensionModule(extensionDLL);

      // TODO: perform other cleanup tasks here
   }
   return 1;   // ok
}
```

에 대 한 호출 `AfxInitExtensionModule` 모듈 런타임 클래스를 캡처합니다 (`CRuntimeClass` 구조)의 개체 팩터리 뿐만 아니라 (`COleObjectFactory` 개체) 사용에 대 한 뒷부분에 나오는 경우를 `CDynLinkLibrary` 개체가 만들어집니다. (선택 사항) 호출 `AfxTermExtensionModule` 허용 MFC 정리 MFC 확장명 DLL 각 프로세스에서 분리 하는 경우 (프로세스가 종료 하거나 DLL의 결과로 언로드되는 때 발생 하는 한 `FreeLibrary` 호출) MFC 확장명 DLL에서에서. 대부분의 MFC 확장명 Dll을 동적으로 로드 되지 않은 이후 (일반적으로 연결 된 해당 가져오기 라이브러리를 통해), 호출 `AfxTermExtensionModule` 일반적으로 필요 하지 않습니다.

응용 프로그램 로드를 동적으로 MFC 확장명 Dll을 해제 하는 경우 호출 해야 `AfxTermExtensionModule` 위와 같이 합니다. 또한 사용 해야 `AfxLoadLibrary` 하 고 `AfxFreeLibrary` (Win32 함수 대신 `LoadLibrary` 및 `FreeLibrary`) 여러 스레드를 사용 하는 응용 프로그램 또는 동적으로 MFC 확장 DLL 로드 하는 경우. 사용 하 여 `AfxLoadLibrary` 고 `AfxFreeLibrary` 하면 MFC 확장명 DLL이 로드 되거나 언로드될 때 실행 되는 시작 및 종료 코드는 전역 MFC 상태가 손상 되지 않습니다.

헤더 파일 AFXDLLX입니다. MFC 확장명 Dll에 대 한 정의 등에서 사용 되는 구조에 대 한 특별 한 정의 포함 하는 H `AFX_EXTENSION_MODULE` 고 `CDynLinkLibrary`입니다.

전역 *extensionDLL* 표시 된 것으로 선언 해야 합니다. 16 비트 버전의 MFC와 달리 메모리를 할당 및 MFCxx.DLL 때 완전히 초기화 되기 때문에이 시간 동안 MFC 함수를 호출할 수 있습니다 프로그램 `DllMain` 라고 합니다.

### <a name="sharing-resources-and-classes"></a>공유 리소스 및 클래스

간단한 MFC 확장명 Dll는 클라이언트 응용 프로그램 및 nothing 자세한 몇 낮은 대역폭 함수를 내보낼만 필요 합니다. 리소스 내보내기 할 집약적인 Dll 자세한 사용자 인터페이스 및 C++ 클라이언트 응용 프로그램에는 클래스입니다.

리소스 내보내기 리소스 목록을 통해 수행 됩니다. 각 응용 프로그램의 단일 연결된 목록을 `CDynLinkLibrary` 개체입니다. 대부분의 리소스를 로드 하는 표준 MFC 구현에서는 먼저 현재 리소스 모듈 확인 리소스를 볼 때 (`AfxGetResourceHandle`) 및 워크 찾을 수 없습니다. 목록을 `CDynLinkLibrary` 요청된 된 리소스를 로드 하려고 하는 개체입니다.

동적 생성 C++ 지정 된 개체는 C++ 클래스 이름 비슷합니다. MFC 개체 deserialization 메커니즘이 모든 해야 합니다 `CRuntimeClass` 개체를 등록 하 여 동적으로 만들어 다시 구성할 수 있습니다 C++ 저장 된 순서에 따라 필요한 형식의 개체입니다.

MFC 확장 DLL의에서 클래스를 사용 하 여 클라이언트 응용 프로그램을 원하는 경우 `DECLARE_SERIAL`, 클라이언트 응용 프로그램에 표시 되도록 클래스를 내보내려면 해야 합니다. 살펴봄으로써도 이렇게는 `CDynLinkLibrary` 목록입니다.

MFC 고급 개념 샘플의 경우 [DLLHUSK](../overview/visual-cpp-samples.md), 목록와 같습니다.

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

MFCxx.DLL은 대개 마지막 리소스 및 클래스 목록에 있습니다. MFCxx.DLL 모든 프롬프트 문자열을 포함 하 여 모든 표준 명령 Id에 대 한 표준 MFC 리소스를 포함 합니다. Dll 및 클라이언트 응용 프로그램 자체에 없는 허용 목록 끝부분에 있는 배치를 자신의 복사본에는 공유의 리소스에 의존 MFCxx.DLL 대신 하지만 표준 MFC 리소스를 합니다.

클라이언트 응용 프로그램의 네임 스페이스에 모든 Dll의 클래스 이름과 리소스를 병합 하는 것에 어떤 Id 주의 해야 하는 단점은 또는 이름을 선택할 수 있습니다. 물론이 기능을 해제 하면이 내보내지 중 하나에서 리소스 또는 `CDynLinkLibrary` 클라이언트 응용 프로그램 개체입니다. 합니다 [DLLHUSK](../overview/visual-cpp-samples.md) 샘플에서는 여러 헤더 파일을 사용 하 여 공유 리소스 네임 스페이스를 관리 합니다. 참조 [기술 참고 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 추가 팁을 공유 리소스 파일을 사용 합니다.

### <a name="initializing-the-dll"></a>DLL 초기화

위에서 설명 했 듯이 일반적으로 만들려는 `CDynLinkLibrary` 클라이언트 응용 프로그램 리소스와 클래스를 내보내려면 개체입니다. DLL을 초기화 하는 내보낸된 진입점을 제공 해야 합니다. 최소한, 인수 사용 하지 않는 한 아무 것도 반환 되는 void 루틴 이지만 원하는 수 있습니다.

DLL을 사용 하려는 각 클라이언트 응용 프로그램이 접근이 방식을 사용 하는 경우이 초기화 루틴을 호출 해야 합니다. 이 할당할 수도 있습니다 `CDynLinkLibrary` 개체에 `DllMain` 호출 후 바로 `AfxInitExtensionModule`합니다.

초기화 루틴을 만들어야 합니다를 `CDynLinkLibrary` 유선에 MFC 확장명 DLL 정보까지 현재 응용 프로그램의 힙에서 개체입니다. 이 다음을 사용 하 여 수행할 수 있습니다.

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

루틴 이름을 *InitXxxDLL* 이 예에서 원하는 대로 지정할 수 있습니다. 사용할 필요가 없습니다 **extern "C"**, 그렇게 더 쉬워진 유지 관리 하는 내보내기 목록 하지만 합니다.

> [!NOTE]
> 일반 MFC DLL에서에서 MFC 확장 DLL을 사용 하는 경우이 초기화 함수를 내보내야 합니다. 이 함수는 리소스 또는 MFC 확장명 DLL 클래스를 사용 하기 전에 일반적인 MFC DLL에서 호출 되어야 합니다.

### <a name="exporting-entries"></a>항목 내보내기

클래스 내보내기 하는 간단한 방법은 사용 하는 것 `__declspec(dllimport)` 고 `__declspec(dllexport)` 각 클래스에 내보내려는 전역 함수입니다. 이 훨씬 쉽게 하지만 기능 내보낸 제어할 적은 후 서 수로 함수를 내보낼 수 없습니다 (아래 설명 참조) 각 진입점을 명명 하는 보다 덜 효율적입니다. TESTDLL1 및 TESTDLL2 해당 항목을 내보내려면이 메서드를 사용 합니다.

보다 효율적인 방법은 (MFCxx.DLL 사용 하는 방법) 이며 각 항목의 이름을 지정 하 여 각 항목을 수동으로 내보낼 합니다. DEF 파일입니다. 선택적 내보냅니다 (즉, 것은 아닙니다) DLL에서을 내보내는 것 이므로 내보내기 하는 특정 인터페이스 결정 해야 합니다. 에 있는 항목의 형태로 링커에 바뀐된 이름을 지정 해야 하므로이 어려운 합니다. DEF 파일입니다. 모든 내보내지 C++ 클래스에 대 한 기호화 된 링크를 실제로 필요 하지 않은 경우.

내보내기 시도 했다면 C++ 클래스를 합니다. DEF 파일을이 목록에 자동으로 생성 하는 도구를 개발 하는 것이 좋습니다. 이렇게 하려면 링크 2 단계 프로세스를 사용 합니다. 내보내기가 없거나 한 번 사용 하 여 DLL에 연결 하 고 생성 하도록 링커에 허용을 합니다. 맵 파일입니다. 합니다. 일부 다시 정렬 사용 하 여이 사용할 수 있도록 내보내기 항목을 생성 하려면 내보내야 하는 함수의 목록을 생성 하려면 맵 파일 수에 합니다. DEF 파일입니다. OLE MFCxx.DLL 및 숫자에서 천 여러 데이터베이스 MFC 확장명 Dll 내보내기 목록 (완전히 자동 아니며 잠시에서 이따금 튜닝 일부 직접 필요) 있지만 해당 프로세스를 사용 하 여 생성 되었습니다.

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs입니다. CDynLinkLibrary

MFC 확장명 DLL 없는 `CWinApp`-파생 개체 자체의; 대신 사용 하 여 작동 해야 합니다는 `CWinApp`-클라이언트 응용 프로그램의 개체를 파생 합니다. 즉, 클라이언트 응용 프로그램 기본 메시지 펌프, 유휴 루프가 등 소유 합니다.

새 클래스를 파생할 수 MFC 확장명 DLL를 각 응용 프로그램에 대 한 추가 데이터를 유지 해야 하는 경우 `CDynLinkLibrary` 루틴 위에서 설명한 InitXxxDLL에 만듭니다. DLL의 현재 응용 프로그램의 목록을 확인할 수 있습니다를 실행할 때 `CDynLinkLibrary` 해당 특정 MFC 확장명 DLL에 대 한 찾을 개체입니다.

### <a name="using-resources-in-your-dll-implementation"></a>DLL 구현에서 리소스를 사용 하 여

기본 리소스 부하의 목록으로 이동은 위에서 설명한 대로 `CDynLinkLibrary` 첫 번째 EXE 또는 DLL 요청 된 리소스가 포함 된 개체입니다. MFC는 모든 Api 뿐만 아니라 내부 코드를 사용 하 여 모든 `AfxFindResourceHandle` 에 있는 수에 관계 없이 모든 리소스를 찾을 리소스 목록으로 이동 합니다.

Api를 사용 하 여만 특정 위치에서 리소스를 로드 하려는 경우 `AfxGetResourceHandle` 고 `AfxSetResourceHandle` 이전 핸들을 저장 하 고 새 핸들을 설정 합니다. 클라이언트 응용 프로그램에 반환 하기 전에 이전 리소스 핸들을 복원 해야 합니다. 샘플 TESTDLL2 메뉴를 명시적으로 로드 하는 것에 대 한이 접근 방식을 사용 합니다.

목록 walking 단점이 있습니다. 조금 저하 되 고 리소스 ID 범위 관리를 필요로 합니다. 여러 MFC 확장 Dll에 연결 하는 클라이언트 응용 프로그램을 DLL 인스턴스 핸들을 지정 하지 않고도 DLL에서 제공 하는 모든 리소스를 사용할 수 있는 이점이 있습니다. `AfxFindResourceHandle` API는 리소스 목록 탐색 하기 위한 지정 된 일치 항목을 검색할 합니다. 리소스의 종류와 이름을 사용 하 고 처음 발견 되는 리소스 핸들 (또는 NULL)를 반환 합니다.

##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> DLL 버전을 사용 하는 응용 프로그램 작성

### <a name="application-requirements"></a>응용 프로그램 요구 사항

MFC의 공유 버전을 사용 하는 응용 프로그램을 몇 가지 간단한 규칙을 따라야 합니다.

- 있어야를 `CWinApp` 개체 및 메시지 펌프에 대 한 표준 규칙을 따릅니다.

- 필요한 컴파일러 플래그 (아래 참조)의 집합을 사용 하 여 컴파일해야 합니다.

- MFCxx 가져오기 라이브러리를 사용 하 여 링크 해야 합니다. 필요한 컴파일러 플래그를 설정 하 여 MFC 헤더 확인 링크 타임에 응용 프로그램은 사용 하 여 연결 해야 하는 라이브러리입니다.

- 실행 파일을 실행 하려면 또는 Windows 시스템 디렉터리 경로에서 MFCxx.DLL 이어야 합니다.

### <a name="building-with-the-development-environment"></a>개발 환경 사용 하 여 빌드

내부 메이크파일 대부분의 표준 기본값을 사용 하는 경우 DLL 버전을 빌드하려면 프로젝트를 쉽게 변경할 수 있습니다.

다음 단계 NAFXCWD 연결 올바르게 작동 MFC 응용 프로그램을 가정 합니다. (디버그)에 대 한 LIB 및 NAFXCW 합니다. (일반 정품)에 대 한 LIB 및 있습니다 MFC 라이브러리의 공유 버전을 사용 하도록 변환 하려고 합니다. 시각적 개체를 실행 하는 C++ 환경의 내부 프로젝트 파일을 고 합니다.

1. **프로젝트** 메뉴에서 **속성**을 클릭합니다. 에 **일반** 페이지의 **프로젝트 기본값**, Microsoft Foundation Classes로 **공유 DLL에서 MFC 사용** (MFCxx(d).dll) 합니다.

### <a name="building-with-nmake"></a>NMAKE를 사용 하 여 빌드

시각적 개체의 외부 메이크파일 기능을 사용 하는 경우 C++, 또는 NMAKE를 사용 하는 사용자의 메이크파일을 컴파일러 및 링커 옵션을 지원 하도록 편집 해야 하는 직접

컴파일러 플래그 필요합니다.

- **/D_AFXDLL /MD**
   **/D_AFXDLL**

표준 MFC 헤더에는이 기호를 정의할 필요 합니다.

- **/MD** C 런타임 라이브러리의 DLL 버전을 사용 해야 하는 응용 프로그램

다른 모든 컴파일러 플래그는 MFC 기본값 (예: 디버그 _DEBUG)를 수행합니다.

라이브러리 링커 목록을 편집 합니다. NAFXCWD 변경 합니다. LIB MFCxxD.LIB을을 선택 하 고 NAFXCW 변경 합니다. LIB MFCxx.LIB 하 합니다. LIBC를 대체 합니다. LIB MSVCRT를 사용 하 여 합니다. LIB 합니다. 다른 MFC 라이브러리를 사용 하 여 MFCxxD.LIB 배치는 중요 한 것 처럼 **하기 전에** 모든 C 런타임 라이브러리입니다.

필요에 따라 추가 **/D_AFXDLL** 에 정품 및 디버그 리소스 컴파일러 옵션 (실제로 사용 하 여 리소스를 컴파일하는 것 **/R**). 이렇게 하면 MFC Dll에 있는 리소스를 공유 하 여 더 작은 최종 실행 파일입니다.

이러한 변경 된 후 전체 다시 빌드가 필요 합니다.

### <a name="building-the-samples"></a>샘플 빌드

시각적 개체에서 대부분의 MFC 샘플 프로그램을 빌드할 수 있습니다 C++ 또는 명령줄에서 NMAKE 호환 메이크파일에 공유 합니다.

변환할 MFCxx.DLL 사용할 이러한 샘플 중 하나를 로드할 수 있습니다 합니다. 시각적 개체로 MAK 파일 C++ 을 위에서 설명한 대로 프로젝트 옵션을 설정 합니다. 사용할 경우 NMAKE 빌드를 지정할 수 있습니다 "AFXDLL = 1" NMAKE에서 명령줄을 사용 하는 예제를 빌드하려면 공유 MFC 라이브러리를 사용 하 여 합니다.

MFC 고급 개념 샘플 [DLLHUSK](../overview/visual-cpp-samples.md) MFC의 DLL 버전을 사용 하 여 빌드됩니다. 이 샘플에는 뿐만 아니라 MFCxx.DLL를 사용 하 여 연결 된 응용 프로그램을 빌드하는 방법을 보여 줍니다 하지만 다른 기능의 MFC 확장 Dll이 기술 노트의 뒷부분에 설명 된 같은 MFC DLL 패키징 옵션을 보여 줍니다.

### <a name="packaging-notes"></a>패키징 정보

일반 정품 버전의 Dll (MFCxx [U]. DLL)은 자유롭게 재배포할 수 있습니다. Dll의 디버그 버전은 자유롭게 재배포할 수 없으며 응용 프로그램의 개발 하는 동안에 사용 해야 합니다.

디버그 Dll 디버깅 정보가 제공 됩니다. 시각적 개체를 사용 하 여 C++ 디버거, DLL 뿐만 아니라 응용 프로그램의 실행을 추적할 수 있습니다. 릴리스 Dll (MFCxx [U]. DLL) 디버깅 정보가 없습니다.

를 사용자 지정 하거나 Dll을 다시 작성 하는 경우 다음 호출 해야 해당 항목 "MFCxx" The MFC SRC 파일 MFCDLL 이외의 합니다. 빌드 옵션을 설명 하 고 DLL 이름 바꾸기에 대 한 논리를 포함 하는 MAK 합니다. 이러한 Dll 많은 MFC 응용 프로그램에서 공유할 가능성이 있으므로 파일 이름 바꾸기 작업은 필요 합니다. 사용자 지정 버전의 MFC Dll replace 사용 하는 것을 시스템에 설치 된 공유 MFC Dll을 사용 하 여 다른 MFC 응용 프로그램을 중단 될 수 있습니다.

MFC Dll을 다시 작성 하는 것은 좋지 않습니다.

##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> MFCxx.DLL 구현 방법

다음 섹션 (MFCxx.DLL 및 MFCxxD.DLL) MFC DLL은 구현 하는 방법을 설명 합니다. 여기에 세부 정보는 또한 하지 이해 모든 수행 하려는 경우는 중요 응용 프로그램을 사용 하 여 MFC DLL을 사용 합니다. 여기에 세부 정보는 MFC 확장 DLL을 작성 하는 방법을 이해 하는 데 필수적이 지 않은 하지만이 구현을 이해 자체 DLL을 작성 하면 도움이 될 수 있습니다.

### <a name="implementation-overview"></a>구현 개요

위에서 설명한 것 처럼 MFC DLL이 실제로 MFC 확장 DLL의 특수 사례입니다. 많은 수의 클래스에 대 한 내보내기의 매우 큰이 많습니다. 일반 MFC 확장명 DLL 보다 훨씬 더 특수 하는 몇 가지 추가 사항 MFC DLL에서 수행 하는 경우

### <a name="win32-does-most-of-the-work"></a>Win32는 대부분의 작업

16 비트 버전의 MFC는 다양 한 앱 별 데이터를 포함 한 스택 세그먼트 80x86 어셈블리 코드가, 프로세스별 예외 컨텍스트 및 다른 방법으로 생성 하는 특별 한 세그먼트 특수 기술이 필요 합니다. Win32 직접 지원 프로세스별 데이터, DLL에는 대부분의 경우 원하는 합니다. 대부분의 MFCxx.DLL는 방금 NAFXCW입니다. LIB DLL로 패키지 됩니다. MFC 소스 코드를 살펴보면 되어야 하는 특수 한 상황이 거의 하므로 거의 #ifdef _AFXDLL을 찾을 수 있습니다. 가지 특히 Windows 3.1 (win32 라고도 함)에 Win32를 사용 하 여 처리 된 특수 사례입니다. Win32는 MFC DLL 스레드 로컬 저장소 (TLS) 프로세스 로컬 데이터를 가져오려면 Win32 Api 사용 해야 하므로 직접 프로세스별 DLL 데이터를 지원 하지 않습니다.

### <a name="impact-on-library-sources-additional-files"></a>원본 라이브러리 추가 파일에 대 한 영향

미치는 합니다 **_AFXDLL** 일반적인 MFC 클래스 라이브러리 소스 및 헤더에서 버전은 비교적 사소한 합니다. 특수 버전 파일이 (AFXV_DLL 합니다. H) 뿐만 아니라 추가 헤더 파일 (AFXDLL_ 합니다. H) 주 AFXWIN으로 포함 됩니다. H 헤더입니다. AFXDLL_ 합니다. H 헤더를 포함 합니다 `CDynLinkLibrary` 클래스 및 기타 구현 세부 정보를 모두 `_AFXDLL` 응용 프로그램 및 MFC 확장명 Dll입니다. AFXDLLX 합니다. MFC 확장명 Dll (자세한 내용은 위 참조)를 빌드하기 위한 H 머리글 제공 됩니다.

MFC 라이브러리에 MFC SRC 일반 원본에는 아래에 있는 몇 가지 추가 조건부 코드를 `_AFXDLL` #ifdef 합니다. 추가 원본 파일 (DLLINIT 합니다. CPP) DLL 초기화 코드를 추가 및 공유 버전의 MFC에 대 한 다른 연결을 포함합니다.

추가 파일은 공유 버전의 MFC 구축 하기 위해 제공 됩니다. (자세한 내용은 아래 참조 DLL을 빌드하는 방법을 설명 합니다.)

- 두 가지입니다. DEF 파일 디버그 (MFCxxD.DEF)에 대 한 MFC DLL 진입점을 내보내는 데 사용 되 고 (MFCxx.DEF) 버전의 DLL 릴리스.

- 합니다. RC 파일 (MFCDLL 합니다. RC) DLL에 대 한 모든 표준 MFC 리소스 및 VERSIONINFO 리소스를 포함합니다.

- 입니다. CLW 파일 (MFCDLL 합니다. CLW) 클래스 마법사를 사용 하 여 클래스는 MFC 검색을 허용 하도록 제공 됩니다. 참고:이 기능은 MFC의 DLL 버전에 특정 아닙니다.

### <a name="memory-management"></a>메모리 관리

MFCxx.DLL를 사용 하 여 응용 프로그램 MSVCRTxx.DLL, 공유 C 런타임 DLL에서 제공 되는 일반적인 메모리 할당자를 사용 합니다. 응용 프로그램, 모든 MFC 확장명 Dll과 MFC Dll이 공유 메모리 할당자를 사용합니다. 메모리 할당에 대 한 공유 DLL을 사용 하면 MFC Dll 응용 프로그램에서 또는 그 반대로 나중에 해제 된 메모리를 할당할 수 있습니다. 재정의 하지 않아야 함 응용 프로그램과 DLL 동일한 할당자를 사용 해야 하므로 C++ 전역 **new 연산자** 하거나 **delete 연산자**합니다. C 런타임 메모리 할당 루틴의 나머지 부분에는 동일한 규칙이 적용 됩니다 (같은 **malloc**를 **realloc**를 **무료**, 등).

### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>서 수 및 클래스 __declspec (dllexport) DLL 이름

사용 하지는 `class` **__declspec (dllexport)** 의 기능을 C++ 컴파일러. 대신, export 목록 클래스 라이브러리 원본 (MFCxx.DEF 및 MFCxxD.DEF) 포함 되어 있습니다. 이러한 진입점 (함수 및 데이터)의 선택 집합만이 내보냅니다. MFC private 구현 함수나 클래스와 같은 기타 기호를 내보내지 않은 내보내기를 모두 상주 또는 비 상주 이름 테이블의 문자열 이름이 없는 서 수로 수행 됩니다.

사용 하 여 `class` **__declspec (dllexport)** 실행 가능한 대안이 작은 Dll을 작성 하지만 메커니즘을 내보내는 기본 MFC와 같은 큰 DLL의 경우에 효율성 및 용량이 수 제한 합니다.

즉, 모든 란 릴리스에서 MFCxx.DLL 로드 속도 훨씬 실행을 손상 하지 않고 약 800 KB만 있는 기능을 많이 패키지화 할 수는 있습니다. MFCxx.DLL 더 큰 100k이이 기술은 되지 사용 합니다. 또한 따라서 끝에 추가 진입점을 추가할 수는 있습니다. 서 수로 내보내기의 속도 및 크기 효율성을 유지 하면서 간단한 버전 관리를 허용 하도록 DEF 파일입니다. MFC 클래스 라이브러리의 주 버전 수정 버전의 라이브러리 이름을 변경 됩니다. 즉, MFC30 합니다. DLL이 MFC 클래스 라이브러리의 버전 3.0를 포함 하는 재배포 가능 DLL입니다. 이 DLL에 대 한 업그레이드를 예를 들어 가상의 MFC 3.1에서는 DLL MFC31 이름이 있습니다. DLL 대신 합니다. 마찬가지로 사용자 지정 버전의 MFC DLL을 생성 하기 위해 MFC 소스 코드를 수정 하는 경우 다른 이름 (및 가급적 이름에 "MFC" 하지 않고 하나)를 사용 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
