---
title: 'TN026: DDX 및 DDV 루틴'
ms.date: 06/28/2018
f1_keywords:
- DDX
- DDV
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
ms.openlocfilehash: 89916e60d9677240f2d70e37e9a80e6ad7a76fc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305868"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX 및 DDV 루틴

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 대화 상자 데이터 교환 (DDX) 및 대화 상자 데이터 유효성 검사 (DDV) 아키텍처를 설명합니다. 또한 DDX_ 나 DDV_ 프로시저를 작성 하는 방법 및 classwizard 함께 사용 하면 루틴을 사용 하도록 확장 하는 방법을 설명 합니다.

## <a name="overview-of-dialog-data-exchange"></a>대화 상자 데이터 교환 개요

모든 대화 상자 데이터 함수 완료 하는 C++ 코드입니다. 특수 리소스 또는 magic 매크로 없는 합니다. 메커니즘의 핵심은 하는 대화 상자 데이터 교환 모든 대화 상자 클래스에서 재정의 되는 가상 함수 및 유효성 검사. 항상이 폼에서 발견 되었습니다.

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

특별 한 형식 AFX 주석을 ClassWizard를 찾아이 함수 내에서 코드를 편집할 수 있습니다. 특별 한 형식 설명을 외부 클래스 마법사를 사용 하 여 호환 되지 않는 코드를 배치 되어야 합니다.

위의 예에서 \<data_exchange_function_call > 형식:

```cpp
DDX_Custom(pDX, nIDC, field);
```

및 \<data_validation_function_call > 형태로 이며 선택 사항입니다.

```cpp
DDV_Custom(pDX, field, ...);
```

둘 이상의 DDX_/DDV_ 쌍을 각각 포함 될 수 있습니다 `DoDataExchange` 함수입니다.

모든 대화 상자 데이터 교환 루틴 및 MFC를 사용 하 여 제공 하는 대화 상자 데이터 유효성 검사 루틴의 목록은 'afxdd_.h'를 참조 하세요.

대화 상자 데이터 일 뿐:에서 멤버 데이터는 `CMyDialog` 클래스입니다. 구조체 또는 유사한 항목에 저장 되지 않습니다.

## <a name="notes"></a>노트

모든 기능에서 파생 된 클래스에서 사용할 수 있지만이 "대화 상자 데이터"를 호출할 `CWnd` 및 대화 상자만 제한 되지 않습니다.

표준 데이터의 초기 값을 설정 C++ 블록에 일반적으로 생성자 `//{{AFX_DATA_INIT` 하 고 `//}}AFX_DATA_INIT` 주석입니다.

`CWnd::UpdateData` 초기화 및 오류에 대 한 호출 주위 처리를 수행 하는 작업이 `DoDataExchange`합니다.

호출할 수 있습니다 `CWnd::UpdateData` 언제 든 지 데이터 교환 및 유효성 검사를 수행 합니다. 기본적으로 `UpdateData`기본값 (TRUE) 라고 `CDialog::OnOK` 처리기 및 `UpdateData`(FALSE) 기본에서 이라고 `CDialog::OnInitDialog`합니다.

DDV_ 루틴에 대 한 DDX_ 루틴 다음에 나와야 *필드*합니다.

## <a name="how-does-it-work"></a>어떻게 작동 하나요

대화 상자 데이터를 사용 하려면 다음을 이해할 필요가 없습니다. 그러나이 내부적으로 작동 하는 방법을 이해 하면 교환 또는 유효성 검사 프로시저를 직접 작성 있습니다.

`DoDataExchange` 멤버 함수는 매우 유사 합니다 `Serialize` 가져오기 또는 설정 데이터를 외부 양식에서 담당 것이 멤버 함수 (이 경우 대화 상자에서 제어) 간에 클래스의 멤버 데이터에 합니다. *pDX* 매개 변수 데이터 교환을 수행 하기 위한 컨텍스트가 유사 합니다 `CArchive` 매개 변수를 `CObject::Serialize`입니다. 합니다 *pDX* (을 `CDataExchange` 개체)에 플래그와 방향이 `CArchive` 방향 플래그가:

- 경우 `!m_bSaveAndValidate`, 다음 컨트롤에 데이터 상태를 로드 합니다.

- 경우 `m_bSaveAndValidate`, 다음 컨트롤에서 데이터 상태를 설정 합니다.

유효성 검사에만 발생 하면 `m_bSaveAndValidate` 설정 됩니다. 변수의 `m_bSaveAndValidate` BOOL 매개 변수를 따라 `CWnd::UpdateData`합니다.

세 가지 다른 흥미로운 가지 `CDataExchange` 멤버:

- `m_pDlgWnd`: 컨트롤이 들어 있는 창 (일반적으로 대화 상자). 이 방법은를 DDX_ 및 DDV_ 전역 함수의 호출자가 'this' 전달 하는 것과 모든 DDX/DDV 루틴입니다.

- `PrepareCtrl`및 `PrepareEditCtrl`: 데이터 교환에 대 한 대화 상자 컨트롤을 준비합니다. 유효성 검사에 실패할 경우 포커스를 설정 하는 것에 대 한 해당 컨트롤의 핸들을 저장 합니다. `PrepareCtrl` 비 편집 컨트롤에 사용 되 고 `PrepareEditCtrl` 편집 컨트롤에 사용 됩니다.

- `Fail`: 사용자 입력된 오류를 경고 메시지 상자를 표시 한 후 호출 됩니다. 이 루틴 마지막 컨트롤에 포커스를 복원 됩니다 (마지막 호출 `PrepareCtrl` 또는 `PrepareEditCtrl`) 예외를 throw 합니다. DDX_와 DDV_ 루틴에서이 멤버 함수를 호출할 수 있습니다.

## <a name="user-extensions"></a>사용자 확장

기본에서 DDX/DDV 메커니즘을 확장 하는 방법은 여러 가지가 있습니다. 다음과 같은 작업을 수행할 수 있습니다.

- 새 데이터 형식을 추가 합니다.

    ```cpp
    CTime
    ```

- 새 exchange 프로시저 (DDX_)를 추가 합니다.

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- 새 유효성 검사 프로시저 (DDV_)를 추가 합니다.

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- 임의의 식 유효성 검사 프로시저에 전달 합니다.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > 이러한 임의의 식 classwizard 함께 사용 하 여 편집할 수 없습니다 및 따라서 특별 한 형식 설명을 외부로 이동 하도록 해야 합니다 (/ / {{AFX_DATA_MAP(CMyClass)) 합니다.

가 합니다 `DoDialogExchange` 멤버 함수는 조건 또는 모든 기타 유효한 포함 C++ 문을 intermixed 교환 및 유효성 검사를 사용 하 여 함수 호출.

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> 위에 표시 된 것과 같이 이러한 코드는 classwizard 함께 사용 하 여 편집할 수 없습니다 하 고 특별 한 형식 설명 외에 사용 해야 합니다.

## <a name="classwizard-support"></a>클래스 마법사 지원

클래스 마법사 클래스 마법사 사용자 인터페이스를 사용자 고유의 DDX_ 및 DDV_ 루틴에 통합할 수 있도록 하 여 DDX/DDV 사용자 지정의 하위 집합을 지원 합니다. 이 비용은 유용한 여러 프로젝트 또는 프로젝트에서 특정 DDX 및 DDV 루틴을 다시 사용 하려는 경우입니다.

이렇게 하려면 특수 한 항목은 DDX에서 이루어집니다. CLW (시각적 개체의 이전 버전 C++ APSTUDIO에이 정보를 저장 합니다. INI) 또는 프로젝트의 합니다. CLW 파일입니다. 특별 한 항목 수의 프로젝트의 [일반 정보] 섹션에서 입력 합니다. CLW 파일 또는 DDX의 [ExtraDDX] 섹션에 있습니다. Visual Studio\Visual \Program Files\Microsoft에서 CLW 파일 C++\bin 디렉터리에 있습니다. DDX를 만들려고 해야 합니다. 이미 존재 하지 않는 경우 CLW 파일입니다. 특정 프로젝트에만 사용자 지정 DDX_/DDV_ 루틴을 사용 하려는 경우 프로젝트의 [일반 정보] 섹션에 항목을 추가 합니다. CLW 파일을 대신 합니다. 여러 프로젝트에서 루틴을 사용 하려는 경우 DDX의 [ExtraDDX] 섹션에 항목을 추가 합니다. CLW 합니다.

이러한 특수 한 항목의 일반 형식은 다음과 같습니다.

> ExtraDDXCount=*n*

여기서 *n* ExtraDDX 수가? 형식에 따라 줄

> ExtraDDX?=*keys*; *vb-keys*; *prompt*; *type*; *initValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

여기서? 1-숫자인 *n* 정의 되는 목록에서 DDX 형식을 나타내는입니다.

각 필드는 ';' 문자로 구분 됩니다. 필드 및 해당 용도 다음과 같습니다.

- *keys*

  목록이 변수 형식을 사용할 수 있는 대화 상자 컨트롤에 대 한을 나타내는 단일 문자입니다.

  |문자|허용 되는 컨트롤|
  |-|-|
  E | 편집
  C | 두 가지 상태 확인란
  c | 3 상 확인란
  R | 그룹의 첫 번째 라디오 단추
  L | 것이 더 효율적일된 목록 상자
  l | 정렬 된 목록 상자
  M | (편집 항목과) 콤보 상자
  N | 것이 더 효율적일된 드롭 목록
  n | 정렬 된 드롭다운 목록
  1 | DDX 삽입 목록 헤드에 추가 해야 하는 경우 (기본값은 비상 추가)이 일반적으로 'Control' 속성을 전송 하는 DDX 루틴에 대 한 합니다.

- *vb-keys*

  이 필드는 VBX 컨트롤 (VBX 컨트롤은 32 비트 제품에서 지원 되지 않음)에 대 한 16 비트 제품에만 사용

- *prompt*

  속성 콤보 상자 (따옴표 제외)에 배치 하는 문자열

- *type*

  헤더 파일에 내보낼 형식에 대 한 단일 식별자입니다. DDX_Time 사용 하 여 위의 예제에서는이 CTime를 설정할 수 됩니다.

- *vb-keys*

  이 버전에서는 사용 되지 않으며 항상 비어 있어야 합니다

- *initValue*

  초기 값-0 또는 비어 있습니다. 비어 있는 경우 초기화 선이 없습니다 구현 파일의 //{{AFX_DATA_INIT 섹션에 기록 됩니다. 빈 항목을 사용 해야 C++ 개체 (같은 `CString`, `CTime`등)는 올바른 초기화를 보장 하는 생성자가 있는 합니다.

- *DDX_Proc*

  DDX_ 프로시저에 대 한 단일 식별자입니다. C++ 함수 이름을 "DDX_,"로 시작 해야 하지만 "DDX_"에 포함 하지 마세요 합니다 \<DDX_Proc > 식별자입니다. 위의 예제는 \<DDX_Proc > 식별자 시간 됩니다. 클래스 마법사는 구현 파일에서 함수 호출을 기록 하는 경우는 {{AFX_DATA_MAP 섹션인 것이 이름에 추가 DDX_, 따라서 DDX_Time 도착 합니다.

- *comment*

  이 DDX 사용 하 여 변수 대화 상자에 표시할 설명입니다. DDX/DDV 쌍으로 수행 된 작업을 설명 하는 여기서 고 일반적으로 항목을 제공 하려는 텍스트를 배치 합니다.

- *DDV_Proc*

  항목의 DDV 부분은 선택 사항입니다. 일부 DDX 루틴 경우 해당 DDV 루틴 전송의 필수적인 부분으로 유효성 검사 단계를 포함 하는 편리한 하는 경우가 많습니다. 이 종종 같은 경우 사용자 DDV 루틴 매개 변수가 필요 하지 않습니다 ClassWizard 매개 변수 없이 DDV 루틴을 지원 하지 않기 때문입니다.

- *arg*

  DDV_ 프로시저에 대 한 단일 식별자입니다. C++ 함수 이름을 "DDV_"로 시작 해야 하지만 "DDX_"에 포함 하지 마십시오는 \<DDX_Proc > 식별자입니다.

  *arg* 뒤에 1 또는 2 DDV 인수:

   - *promptN*

      항목 편집 (사용 하 여 & 가속기에 대 한) 위에 배치 하는 문자열입니다.

   - *fmtN*

      Arg 형식 중 하나에 대 한 형식 문자.

      |문자|형식|
      |-|-|
      |일 | int|
      |u | unsigned int|
      |D | (즉, long) int를 긴|
      |U | 부호 없는 long (즉, DWORD)|
      |f | float|
      |F | double|
      |초 | string|

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
