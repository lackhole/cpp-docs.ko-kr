---
title: AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: bcfdc94e8db80daec227d77c20ecec6b14d5af11
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821224"
---
# <a name="exporting-and-importing-using-afxextclass"></a>AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기

[MFC 확장명 Dll](extension-dlls-overview.md) 매크로 사용 하 여 **AFX_EXT_CLASS** 내보내려면 클래스; 클래스를 가져오려면 매크로 사용 하는 MFC 확장명 DLL에 연결 된 실행 합니다. 사용 하 여 합니다 **AFX_EXT_CLASS** 매크로, MFC 확장 DLL을 DLL에 연결 하는 실행 파일 수를 작성 하는 데 사용 되는 동일한 헤더 파일에 있습니다.

DLL에 대 한 헤더 파일에 추가 합니다 **AFX_EXT_CLASS** 키워드를 다음과 같이 클래스의 선언 합니다.

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

이 매크로 MFC로 정의한 `__declspec(dllexport)` 때 전처리기 기호 `_AFXDLL` 고 `_AFXEXT` 정의 됩니다. 매크로로 정의 됩니다 `__declspec(dllimport)` 때 `_AFXDLL` 정의 된 및 `_AFXEXT` 정의 되어 있지 않습니다. 전처리기 기호를 정의할 때 `_AFXDLL` 공유 버전의 MFC는 대상 실행 파일 (DLL 또는 응용 프로그램)에서 사용 중인 됨을 나타냅니다. 때 둘 다 `_AFXDLL` 및 `_AFXEXT` 는 대상 실행 파일은 MFC 확장 DLL 임을 나타냅니다 정의 합니다.

때문에 `AFX_EXT_CLASS` 란 `__declspec(dllexport)` MFC 확장 DLL에서에서 내보내기 하는 경우 모든 해당 클래스의 기호에 대 한 데코레이팅된 이름을.def 파일에 배치 하지 않고 전체 클래스를 내보낼 수 있습니다.

이 메서드를 사용 하 여.def 파일 및 클래스에 대 한 트 데코 레이 된 이름의 모든 만들기를 방지 하지만.def 파일을 만드는 하므로 보다 효율적입니다 이름은 서 수로 내보낼 수 있습니다. 내보내는.def 파일 메서드를 사용 하려면 헤더 파일의 시작과 끝에 다음 코드를 추가 합니다.

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
>  인라인 함수를 내보낼 때는 주의 때문일 버전 충돌 가능성을 만들 수 있습니다. 인라인 함수는 응용 프로그램 코드로 확장됩니다. 따라서 나중에 이 함수를 다시 쓰는 경우 해당 응용 프로그램을 다시 컴파일해야만 함수가 업데이트됩니다. 일반적으로 DLL 함수를 사용 하는 응용 프로그램을 다시 작성 하지 않고 업데이트할 수 있습니다.

## <a name="exporting-individual-members-in-a-class"></a>클래스의 개별 멤버 내보내기

클래스의 개별 멤버를 내보내려면 하는 경우가 있습니다. 예를 들어 내보내는 경우는 `CDialog`-파생 클래스에서 내보내기 생성자만 필요할 및 `DoModal` 호출 합니다. 사용할 수 있습니다 `AFX_EXT_CLASS` 개별 멤버를 내보내야 합니다.

예를 들어:

```cpp
class CExampleDialog : public CDialog
{
public:
   AFX_EXT_CLASS CExampleDialog();
   AFX_EXT_CLASS int DoModal();
   ...
   // rest of class definition
   ...
};
```

클래스의 모든 멤버를 더 이상 내보낼 때문에 발생할 수 없습니다 다른 문제는 방식으로 인해 MFC 매크로 작업. 다양 한 MFC의 도우미 매크로 실제로 선언 또는 데이터 멤버를 정의 합니다. 따라서 이러한 데이터 멤버 DLL에서 내보내야 합니다.

예를 들어를 `DECLARE_DYNAMIC` 매크로 MFC 확장 DLL을 빌드할 경우 다음과 같이 정의 됩니다.

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

정적을 사용 하 여 시작 하는 줄 `AFX_DATA` 클래스 내에서 정적 개체를 선언 하는 합니다. 이 클래스를 올바르게 내보내고 클라이언트 실행 파일에서 런타임 정보를 액세스, 정적이 개체를 내보내야 합니다. 정적 개체는 한정자로 선언 되었으므로 `AFX_DATA`를 정의 해야 `AFX_DATA` 되도록 `__declspec(dllexport)` DLL을 빌드할 때으로 정의 `__declspec(dllimport)` 실행 클라이언트를 빌드할 때입니다. 때문에 `AFX_EXT_CLASS` 이미 정의 되어 이렇게에서 하면 다시 정의할 `AFX_DATA` 와 동일 하 `AFX_EXT_CLASS` 클래스 정의 주위 합니다.

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

MFC에서 항상 사용 하기 때문에 `AFX_DATA` 기호 내의 해당 매크로 정의 하는 데이터 항목에 이러한 모든 시나리오에 대 한이 기술은 작동 합니다. 에 대 한 작동 예를 들어 `DECLARE_MESSAGE_MAP`합니다.

> [!NOTE]
>  클래스의 선택한 멤버 보다는 전체 클래스를 내보내는 경우 정적 데이터 멤버는 자동으로 내보내집니다.

### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport)을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [데코레이팅된 이름](reference/decorated-names.md)

- [인라인 함수 가져오기 및 내보내기](importing-and-exporting-inline-functions.md)

- [상호 가져오기](mutual-imports.md)

## <a name="see-also"></a>참고자료

[DLL에서 내보내기](exporting-from-a-dll.md)
