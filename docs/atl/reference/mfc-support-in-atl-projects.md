---
title: ATL 프로젝트의 MFC 지원입니다.
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 0aece6805f1de987b0164f405e50b99fd706fef4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275427"
---
# <a name="mfc-support-in-atl-projects"></a>ATL 프로젝트의 MFC 지원입니다.

선택 하는 경우 **MFC 지원** ATL 프로젝트 마법사에서 프로젝트는 응용 프로그램을 MFC 응용 프로그램 개체 (클래스)로 선언 합니다. 프로젝트가 MFC 라이브러리를 초기화 하 고 클래스를 인스턴스화합니다 (클래스 *ProjName*)에서 파생 된 [CWinApp](../../mfc/reference/cwinapp-class.md)합니다.

이 옵션은 하지 않는 ATL DLL 프로젝트에만 사용할 수 있습니다.

```
class CProjNameApp : public CWinApp
{
public:

// Overrides
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)
END_MESSAGE_MAP()

CProjNameApp theApp;

BOOL CProjNameApp::InitInstance()
{
    return CWinApp::InitInstance();

}

int CProjNameApp::ExitInstance()
{
    return CWinApp::ExitInstance();

}
```

응용 프로그램 개체 클래스를 볼 수 있습니다 및 해당 `InitInstance` 고 `ExitInstance` 클래스 뷰에서 함수입니다.

## <a name="see-also"></a>참고자료

[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)<br/>
[기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)
